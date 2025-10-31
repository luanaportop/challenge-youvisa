# FIAP - Faculdade de Informática e Administração Paulista

<p align="center">
<a href="https://www.fiap.com.br/"><img src="assets/logo-fiap.png" alt="FIAP - Faculdade de Informática e Administração Paulista" border="0" width=40% height=40%></a>
</p>

<br>

# YOUVISA – Plataforma Inteligente de Atendimento Multicanal (Sprint 1)
## Beginner Coders
## 👨‍🎓 Integrantes:
- <a href="https://www.linkedin.com/in/luana-porto-pereira-gomes/">Luana Porto Pereira Gomes</a>
- <a href="https://www.linkedin.com/in/luma-x">Luma Oliveira</a>
- <a href="https://www.linkedin.com/in/priscilla-oliveira-023007333/">Priscilla Oliveira </a>
- <a href="https://www.linkedin.com/in/paulobernardesqs?utm_source=share&utm_campaign=share_via&utm_content=profile&utm_medium=ios_app">Paulo Bernardes</a>

## 👩‍🏫 Professores:
### Tutor(a)
- <a href="https://www.linkedin.com/in/leonardoorabona/">Leonardo Ruiz</a>
### Coordenador(a)
- <a href="https://www.linkedin.com/in/profandregodoi/">André Godoi</a>
## 📜 Descrição do Projeto
Este repositório contém a **proposta técnica inicial** da plataforma **YOUVISA** para um **atendimento cognitivo multicanal** (WhatsApp, Telegram, Web) com **NLP**, **RPA**, **visão computacional** para validação documental e **arquitetura cloud** escalável.  
Esta entrega foca em **escopo, arquitetura, fluxos e governança**.
## 🎯 Objetivos da Sprint 1
- Definir **arquitetura técnica** (cloud, APIs, serviços de NLP/RPA) e **pipeline de dados**.  
- Desenhar **fluxos do chatbot** (Telegram como diferencial; integração desejável com WhatsApp).  
- Especificar **coleta/tratamento de dados** (simulada) e **estratégia de segurança LGPD**.  
- Definir **encaminhamento para humano** e **métricas/KPIs**.  
- Organizar **plano de desenvolvimento** e **RACI**.
## 💡 Problema & Solução (Resumo Executivo)
**Problema:** organizações lidam com alto volume de solicitações de vistos/consulares, triagens repetitivas e verificações documentais que geram **custos** e **atrasos**.  
**Solução:** plataforma multicanal com **chatbot cognitivo** + **automação de processos (RPA)** + **validação de documentos via visão computacional**. O atendimento mantém **continuidade entre canais**, garante **segurança (LGPD)** e **handoff para humano** quando necessário.
## 🧠 Arquitetura (alta visão)
A arquitetura contempla:
<p align="center">
<a href=""><img src="assets/Arquitetura_YouVisa.png" alt="Arquitetura" border="0" width=40% height=40%></a>
</p>
- **Canais**: WhatsApp, Telegram, Web Chat.  
- **NLP/Chatbot**: Dialogflow / Rasa / spaCy / Hugging Face.  
- **Backend/API**: Node.js / Python (FastAPI/Flask) / Java (Spring).  
- **Visão Computacional**: OCR (Tesseract/AWS Textract/GCP Vision), leitura de **MRZ** e checagens antifraude.  
- **Dados**: PostgreSQL/MongoDB + Data Lake/Blob para anexos.  
- **Cloud**: AWS / GCP / Azure (Auth, Storage, Queue, Observability).  
- **Atendimento Humano**: painel web + fila de tickets (API REST).
📄 **Detalhes e diagramas**: ver `docs/arquitetura.md` (diagramas Mermaid e instruções para exportar no diagrams.net).
## 💬 NLP & Fluxos de Conversa
- **Intenções/Entidades** e exemplos: `nlp/intents.md`.  
- **Fluxos (Telegram/WhatsApp)** com **handoff humano**: `docs/fluxos_chatbot.md`.  
- **Amostras de payloads** e **schemas**: `data/schemas/*.json`.
## 👁️ Validação de Documentos (Visão Computacional)
Estratégia de **OCR**, leitura de **MRZ** de passaportes e **checagens antifraude** (consistência de campos, datas, país emissor).  
Detalhes: `docs/visao_computacional.md`.
## 🔐 Segurança e LGPD
- Princípios de **privacidade por design**, classificação de dados, base legal, retenção e descarte.  
- Criptografia em trânsito e em repouso, **controle de acesso**, auditoria e gestão de segredos.  
- Variáveis de ambiente: `.env.example` (**NUNCA** commitar `.env` real).  
Documento completo: `SECURITY.md`.
## 📈 Métricas & KPIs (inicial)
- **Tempo médio de primeira resposta (FRT)**  
- **Taxa de resolução sem humano (Self-service rate)**  
- **Taxa de handoff** e **SLA** de atendimento humano  
- **Precisão de OCR/NLP** e **taxa de falsos positivos** na validação
 ## 🗂️ Plano & RACI
- **Cronograma detalhado** por semana/entregável: `docs/timeline.md`.  
- **RACI** (papéis e responsabilidades): `docs/raci.csv`.
## 🖥️ Como apresentar
Use `docs/pitch.md` com roteiro de **5–7 minutos**:  
1) Problema → 2) Solução → 3) Arquitetura → 4) Fluxos (demo/diagramas) → 5) Próximos passos.
## 🔧 Estrutura do repositório
```
assets               # Imagens.
docs/                # Arquitetura, fluxos, segurança, timeline, pitch
nlp/                 # Intents, entidades e exemplos
data/schemas/        # JSON Schemas para registros e eventos
infra/               # IaC esqueleto e decisões
scripts/             # Utilitários (mock/seed)
```
