# Visão Computacional – Validação Documental

## Alvos
- **Passaporte** (MRZ), **RG**, **CNH**, **comprovante de residência**.
- Selfie para **prova de vida** e **match** com documento.

## Pipeline
1. Receber imagem/pdf → normalizar (deskew, denoise, crop MRZ).
2. OCR (Textract/Vision) → extrair campos + MRZ (passaporte).
3. Regras de consistência (datas, país, dígitos verificadores MRZ).
4. Detecção de fraude (artefatos, cortes, glare, múltiplas compressões).
5. Face match (1:1) entre selfie e foto do documento (limiar calibrado).
6. Sinalizar risco → **fila humana**.

## Saídas (exemplo)
- `doc_validacao.json`: status, score_risco, campos extraídos, evidências hash.
- Persistir apenas o necessário, com **criptografia em repouso** e **expurgo** por política de retenção.
