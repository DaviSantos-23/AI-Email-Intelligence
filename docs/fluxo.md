🔄 Fluxo do Sistema

## Visão Geral

O sistema possui dois fluxos principais.

O primeiro realiza a triagem e classificação dos e-mails recebidos.

O segundo utiliza os dados armazenados para gerar um relatório periódico para o gestor.

---

# Workflow 1 — Triagem Inteligente

## 1. Recebimento do E-mail

O sistema identifica a chegada de um novo e-mail.


📩 Novo e-mail
      ↓
     n8n
     
---

📩 E-mail recebido
        ↓
      n8n
        ↓
      LLM
        ↓
┌───────┼────────┐
↓       ↓        ↓
Classe Urgência Sentimento
└───────┼────────┘
        ↓
     Roteamento
        ↓
      Slack
        ↓
 Google Sheets
        ↓
 Workflow agendado
        ↓
 Consolidação
        ↓
 Relatório
        ↓
     Gestor