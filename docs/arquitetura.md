# Arquitetura da Solução (Alta Visão)

A solução é **event-driven** (orientada a eventos) e **multicanal**:

```mermaid
flowchart LR
    subgraph Canais
      W[WhatsApp (Cloud API)] --> G
      T[Telegram Bot API] --> G
      Wb[Web Chat (Widget)] --> G
    end

    G[Gateway Omnicanal / Orquestrador] --> N[NLP Engine (Intent/Entity)]
    N --> P[Policy/Context Manager]
    P --> R[Regras & Roteamento]
    R -->|Docs| V[Visão Computacional (OCR/MRZ/Antifraude)]
    R -->|RPA| A[Orquestrador RPA]
    R --> S[Serviços Internos (Microserviços)]
    S --> D[(Data Lake + DW)]
    S --> Q[(Fila/Mensageria)]
    V --> D
    A --> S
    N --> D

    subgraph Cloud
      G
      N
      P
      R
      V
      A
      S
      D
      Q
    end

    R --> H[Handoff Humano (Agent Desk)]
```

**Tecnologias sugeridas (exemplos, intercambiáveis):**
- **Canais**: Telegram Bot API; WhatsApp Cloud API; Web Widget (ex.: Chatwoot/Omnichannel).
- **NLP**: spaCy/Rasa/NLU open-source ou provedor gerenciado (respeitando LGPD).
- **RPA**: Camunda/Zeebe, n8n, Airflow para orquestração de tarefas.
- **Visão**: AWS Textract/Google Vision + lib MRZ (passaporte) + validações.
- **Dados**: Data Lake (S3/GCS) + DW (BigQuery/Redshift) + mensageria (Pub/Sub/SQS).
- **Segurança**: KMS, Secrets Manager, OAuth2/OIDC, audit logs.

Ver também `infra/decisoes.md` para trade-offs.
