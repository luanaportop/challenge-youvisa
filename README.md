# YOUVISA – Plataforma Inteligente de Atendimento Multicanal (Sprint 1)

> Período: **09/10/2025 → 05/11/2025** · Turma **2TIAOR** · Repositório **PRIVADO** (compartilhar com *leoruiz197*)

## 1) Visão Geral
Este repositório contém a **proposta técnica inicial** da plataforma YOUVISA para um **atendimento cognitivo multicanal** (WhatsApp, Telegram, Web) com **NLP**, **RPA**, **visão computacional** para validação documental e **arquitetura cloud** escalável. Esta entrega foca em **escopo, arquitetura, fluxos e governança** — sem necessidade de código funcional.

## 2) Problema & Solução (Resumo Executivo)
**Problema**: organizações enfrentam alto volume de solicitações de vistos/consulares, com etapas repetitivas de triagem, coleta de documentos e verificação, gerando **custos** e **atrasos**.
**Solução**: plataforma multicanal com **chatbot cognitivo** + **automação de processos (RPA)** + **validação de documentos via visão computacional**. O atendimento mantém **continuidade entre canais**, garantindo **segurança (LGPD)** e **encaminhamento para humano** quando necessário.

## 3) Objetivos da Sprint 1
- Definir **arquitetura técnica** (cloud, APIs, serviços NLP) e **pipeline de dados**.
- Desenhar **fluxos do chatbot** (Telegram como diferencial; integração desejável WhatsApp).
- Especificar **coleta/tratamento de dados** (simulada) e **estratégia de segurança LGPD**.
- Definir **encaminhamento para humano** e **métricas/KPIs**.
- Organizar **plano de desenvolvimento** e **RACI**.

## 4) Arquitetura (alta visão)
Ver `docs/arquitetura.md` (com diagramas Mermaid e descrição para exportar no diagrams.net).

## 5) NLP & Fluxos de Conversa
- Intenções, entidades e exemplos em `nlp/intents.md`.
- Fluxos do Telegram e WhatsApp em `docs/fluxos_chatbot.md` (com handoff humano).
- Amostras de payloads (`data/schemas/*.json`).

## 6) Validação de Documentos (Visão Computacional)
- Estratégia de OCR (Textract/Vision), leitura de **MRZ** de passaportes, e checagens antifraude. Ver `docs/visao_computacional.md`.

## 7) Segurança e LGPD
- Princípios, dados pessoais sensíveis, base legal e retenção. Ver `SECURITY.md`.
- Variáveis de ambiente em `.env.example` (NUNCA commitar `.env`).

## 8) Plano & RACI
- Cronograma detalhado: `docs/timeline.md`.
- RACI (papéis e responsabilidades): `docs/raci.csv`.

## 9) Como colaborar
Ver `CONTRIBUTING.md`. Abrir issues por entregável. Commits pequenos e descritivos.

## 10) Como apresentar
Use `docs/pitch.md` com roteiro de 5–7 minutos (problema, solução, arquitetura, demo de fluxos e próximos passos).

---

### Compartilhar acesso (GitHub → Settings → Collaborators)
Adicionar **leoruiz197** (convite expira em 7 dias).

### Estrutura do repositório
```
docs/                # Arquitetura, fluxos, segurança, timeline, pitch
nlp/                 # Intents, entidades e exemplos
data/schemas/        # JSON Schemas para registros e eventos
infra/               # IaC esqueleto e decisões
scripts/             # Utilitários (mock/seed)
```

### Licença
Uso acadêmico — ver `LICENSE`.
