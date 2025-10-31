# SECURITY (LGPD & Boas Práticas)

- **Base legal**: execução de contrato e consentimento explícito para dados sensíveis.
- **Minimização**: coletar apenas o essencial; mascarar onde possível.
- **Criptografia**: TLS em trânsito; KMS/CMK em repouso; rotação de chaves.
- **Segredos**: usar Secrets Manager; nunca commitar tokens.
- **Identidade**: OAuth2/OIDC; escopos mínimos; MFA para agentes.
- **Auditoria**: trilhas de auditoria imutáveis e alertas de anomalia.
- **Retenção/Expurgo**: políticas por tipo de dado; direito ao esquecimento.
- **Continuidade entre canais**: usar **session/continuity token** assinado (JWT curta duração).
