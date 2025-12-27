# Risk Matrix 5x5 — Matriz de Risco (P x I)

Esta matriz apoia a classificação do **Nível de Risco** usando a metodologia definida em `risk-methodology.md`:

- **Probabilidade (P):** 1–5  
- **Impacto (I):** 1–5  
- **Pontuação:** P x I (1–25)  
- **Criticidade (faixas sugeridas):**
  - 1–4: **Baixo**
  - 5–9: **Médio**
  - 10–14: **Alto**
  - 15–25: **Crítico**

---

## 1) Matriz (tabela)

> Linhas = **Probabilidade (P)**  
> Colunas = **Impacto (I)**

| P \ I | 1 | 2 | 3 | 4 | 5 |
|---:|---:|---:|---:|---:|---:|
| **5** | 5 | 10 | 15 | 20 | 25 |
| **4** | 4 | 8 | 12 | 16 | 20 |
| **3** | 3 | 6 | 9 | 12 | 15 |
| **2** | 2 | 4 | 6 | 8 | 10 |
| **1** | 1 | 2 | 3 | 4 | 5 |

---

## 2) Interpretação por criticidade (guia rápido)

- **Baixo (1–4):** risco tolerável; monitorar e revisar conforme cadência
- **Médio (5–9):** plano de melhoria recomendado; priorização por contexto
- **Alto (10–14):** requer plano de ação com owner e prazo; acompanhamento
- **Crítico (15–25):** atenção executiva; contenção/mitigação prioritária e governança formal (aceite com expiração, se aplicável)

---

## 3) Exemplos de classificação

- P=4, I=4 → 16 (**Crítico**)  
- P=3, I=3 → 9 (**Médio**)  
- P=2, I=5 → 10 (**Alto**)  
- P=1, I=4 → 4 (**Baixo**)

---

## 4) Boas práticas de uso

- Sempre registrar a justificativa de P e I (especialmente em riscos Altos/Críticos).
- Reavaliar quando houver mudança significativa (incidente, mudança de arquitetura, novo fornecedor).
- Usar **risco residual** para medir evolução do programa (antes vs depois do tratamento).

---
