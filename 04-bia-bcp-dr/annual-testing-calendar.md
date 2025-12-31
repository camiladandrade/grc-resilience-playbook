# Calendário Anual de Testes — Resiliência (BCP/DR)

Este documento define um calendário anual (modelo) para testes de continuidade e recuperação, garantindo:
- previsibilidade
- evidências para auditoria
- melhoria contínua

> Objetivo: sair do “testa quando dá” e criar rotina de validação.

---

## 1) Tipos de teste (referência rápida)

- **Tabletop (TTX):** simulação de decisões e processos (sem técnica)
- **Walkthrough:** revisão guiada do plano (passo a passo)
- **Restore Drill:** teste de restauração (backup/recuperação)
- **Failover Test:** teste de failover (quando aplicável)
- **Comunicação:** teste de contatos e cadência de comunicação

---

## 2) Calendário (modelo)

> Ajuste por criticidade (Tier-0/Tier-1 têm cadência maior).

| Mês | Teste | Escopo | Evidência esperada | Owner | Status |
|---|---|---|---|---|---|
| Jan | Tabletop (TTX) | Serviço/Processo crítico | Ata + ações (CAPA) |  | Planejado |
| Fev | Restore Drill | Backup de sistema X | Evidência de restore + tempo |  |  |
| Mar | Walkthrough BCP | Processo Y | Ata + ajustes no plano |  |  |
| Abr | Teste de comunicação | Lista de contatos | Resultado + gaps |  |  |
| Mai | Restore Drill | Sistema Z | Evidência + validação |  |  |
| Jun | Tabletop (TTX) | Cenário alternativo | Ata + ações |  |  |
| Jul | Walkthrough DRP | DRP crítico | Ajustes + evidências |  |  |
| Ago | Restore Drill | Dados/serviço crítico | Evidência + tempo |  |  |
| Set | Teste de terceiros | Fornecedor crítico | Evidência + SLA |  |  |
| Out | Tabletop (TTX) | Crise/indisponibilidade | Ata + ações |  |  |
| Nov | Restore Drill | Backup + validação | Evidência + tempo |  |  |
| Dez | Revisão anual | BIA/BCP/DR | Relatório anual |  |  |

---

## 3) Evidências mínimas por teste

- objetivo e escopo
- participantes
- resultados (tempo/decisões)
- gaps e ações (CAPA)
- evidência anexada/linkada

---

## 4) Próximo passo sugerido

Definir KPIs de resiliência e modelo de reporting:
- `resilience-metrics-and-reporting.md`

---
