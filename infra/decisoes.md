# Decisões de Arquitetura (ADR – resumo)

- **ADR-001 – Mensageria**: usar Pub/Sub/SQS para desacoplar canais do core.
- **ADR-002 – NLP**: começar com NLU open-source + dicionário de entidades; abrir porta para provedor gerenciado.
- **ADR-003 – Handoff**: usar plataforma de agent desk (Chatwoot/Zendesk) com API de conversas.
- **ADR-004 – Vision**: OCR gerenciado + biblioteca MRZ; thresholds e revisão humana para casos fronteira.
- **ADR-005 – Dados**: Data Lake bruto + DW para relatórios/KPIs; PII segregada e criptografada.
