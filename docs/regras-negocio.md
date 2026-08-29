# 📋 Regras de Negócio

Este documento descreve as regras utilizadas pelo sistema para processar, classificar, armazenar e encaminhar os e-mails recebidos.

---

## RN-01 — Recebimento

Todo novo e-mail recebido pelo canal monitorado deve iniciar o workflow de triagem.

---

## RN-02 — Análise do Conteúdo

O conteúdo da mensagem deve ser analisado por um modelo de linguagem antes do roteamento.

---

## RN-03 — Classificação da Solicitação

Cada solicitação deve ser classificada em uma categoria.

Categorias disponíveis:

- Bug
- Elogio
- Reclamação
- Sugestão

---

## RN-04 — Análise de Sentimento

Cada mensagem deve receber uma classificação de sentimento.

Valores permitidos:

- Positivo
- Neutro
- Negativo

---

## RN-05 — Análise de Urgência

Cada solicitação deve possuir uma classificação de urgência.

A classificação deve representar a prioridade identificada na mensagem.

---

## RN-06 — Roteamento

Após a classificação, o atendimento deve ser direcionado ao canal correspondente no Slack.

Bug
→ Canal de Bugs

Elogio
→ Canal de Elogios

Reclamação
→ Canal de Reclamações

Sugestão
→ Canal de Sugestões