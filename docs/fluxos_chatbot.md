# Fluxos de Chatbot (Telegram & WhatsApp)

## 1) Intenção: Iniciar Solicitação de Visto
```mermaid
sequenceDiagram
    participant U as Usuário
    participant TG as Telegram/WhatsApp
    participant GW as Gateway Omnicanal
    participant NLP as Motor NLP
    participant R as Regras/Roteamento
    participant V as Visão (OCR/MRZ)
    participant A as RPA
    participant H as Humano (Desk)

    U->>TG: /start ou "Quero solicitar visto"
    TG->>GW: Mensagem
    GW->>NLP: Texto (detectar intenção+entidades)
    NLP-->>GW: intent=solicitar_visto, país=EUA?
    GW->>R: Contexto + intent
    R-->>U: Checklist e consentimento LGPD
    U->>TG: Aceito
    R-->>U: Solicitar upload de passaporte/selfie
    U->>TG: Upload (passaporte + selfie)
    R->>V: OCR/MRZ + selfie match
    V-->>R: OK / suspeita?
    alt Suspeita
        R-->>H: Handoff humano (fila Prioridade)
        H-->>U: Atendimento humano contínuo
    else OK
        R->>A: Criar processo no backoffice
        A-->>R: Protocolo
        R-->>U: Protocolo + próximos passos
    end
```

## 2) Falha de entendimento (Fallback)
- 1ª vez: reformular + sugestões de intenções.
- 2ª vez: oferecer **encaminhamento humano**.
- Sempre manter **token de continuidade** entre canais.
