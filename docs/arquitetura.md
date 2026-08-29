# 🏗️ Arquitetura do Sistema

## Visão Geral

O AI Email Intelligence & Routing utiliza uma arquitetura baseada em workflows automatizados no **n8n**, integrando e-mail, modelos de linguagem, Slack e Google Sheets.

O sistema é dividido em dois workflows principais:

1. **Workflow de Triagem Inteligente**
2. **Workflow de Relatório Gerencial**

O primeiro é responsável por processar individualmente cada e-mail recebido.

O segundo consolida os dados armazenados e gera um relatório periódico para o gestor.

---

## Arquitetura Geral


                         ┌──────────────┐
                         │    Gmail     │
                         │ Email recebido│
                         └──────┬───────┘
                                │
                                ▼
                         ┌──────────────┐
                         │     n8n      │
                         │   Workflow   │
                         └──────┬───────┘
                                │
                                ▼
                         ┌──────────────┐
                         │     LLM      │
                         │    Análise   │
                         └──────┬───────┘
                                │
                  ┌─────────────┼─────────────┐
                  │             │             │
                  ▼             ▼             ▼
             Categoria       Urgência     Sentimento
                  │             │             │
                  └─────────────┼─────────────┘
                                │
                                ▼
                         ┌──────────────┐
                         │  Roteamento  │
                         └──────┬───────┘
                                │
                                ▼
                         ┌──────────────┐
                         │    Slack     │
                         └──────┬───────┘
                                │
                                ▼
                       ┌─────────────────┐
                       │  Google Sheets  │
                       │ Dados tratados  │
                       └────────┬────────┘
                                │
                                ▼
                       ┌─────────────────┐
                       │ Workflow        │
                       │ Agendado        │
                       └────────┬────────┘
                                │
                                ▼
                       ┌─────────────────┐
                       │ Relatório       │
                       │ Gerencial       │
                       └────────┬────────┘
                                │
                                ▼
                            Gestor