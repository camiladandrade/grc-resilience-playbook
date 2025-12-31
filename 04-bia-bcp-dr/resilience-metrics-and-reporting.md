# Métricas e Reporting — Resiliência (BIA/BCP/DR)

Este documento propõe KPIs para resiliência e um modelo simples de reporting, alinhado a governança e auditoria.

> Objetivo: evidenciar se a organização está preparada para interrupções e se os planos são testados de verdade.

---

## 1) KPIs recomendados (catálogo)

### 1.1 Cobertura e maturidade
- **% de processos críticos com BIA atualizada**
- **% de serviços Tier-0/Tier-1 com BCP/DRP atualizados**
- **% de planos revisados no prazo**

### 1.2 Testes e evidências
- **% de testes executados vs planejados (calendário anual)**
- **% de testes com evidências completas**
- **# de ações corretivas abertas vs concluídas (CAPA)**

### 1.3 Performance (quando aplicável)
- **Tempo de restauração real vs RTO**
- **Perda de dados real vs RPO**
- **Taxa de sucesso de restore drills (%)**

### 1.4 Terceiros (quando aplicável)
- **% de fornecedores críticos com evidência de testes/DR**
- **SLA de recuperação de fornecedores (quando medido)**

---

## 2) Modelo de painel mensal (resumo)

| KPI | Atual | Meta | Tendência | Comentário |
|---|---:|---:|:---:|---|
| % BIA atualizada (críticos) |  |  | ↑/→/↓ |  |
| % testes executados vs planejados |  |  | ↑/→/↓ |  |
| Restore drills: sucesso (%) |  |  | ↑/→/↓ |  |
| Ações corretivas (abertas) |  |  | ↑/→/↓ |  |

---

## 3) Narrativa executiva (1 parágrafo)

Exemplo de estrutura:
- “No período, executamos X de Y testes planejados (Z%). Identificamos N gaps, com M já concluídos. O principal risco atual é _____. A ação prioritária é _____ até ____.”

---

## 4) Conexões com este repositório

- Calendário anual: `annual-testing-calendar.md`
- Tabletop template: `tabletop-exercise-template.md`

---
