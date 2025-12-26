# Risk Register — Template (GRC)

Template de **Registro de Riscos** para Gestão de Riscos de Segurança da Informação, com foco em rastreabilidade, decisões e governança.

> Recomendação: use este template como base para uma planilha (Excel/Sheets) ou ferramenta (GRC/Jira).  
> Campos mínimos: dono do risco, criticidade, plano de tratamento e data de revisão.

---

## 1) Metadados

- **Nome do documento:** Risk Register
- **Escopo:** (ex.: Organização inteira / unidade / sistema / produto) ______________________
- **Owner do documento:** ______________________
- **Versão:** ______
- **Data:** ____/____/____
- **Periodicidade de revisão:** (mensal/trimestral) ________

---

## 2) Dicionário de campos (como preencher)

### Identificação e contexto
- **ID do risco:** RR-0001 (único)
- **Domínio:** (Identidade, Endpoints, Cloud, Apps, Dados, Terceiros, Resiliência, etc.)
- **Ativo/Serviço:** o que está em risco
- **Descrição do risco:** “Se X acontecer, então Y pode ocorrer, resultando em Z”
- **Causa:** por que pode acontecer (ex.: controle ausente, processo falho)
- **Consequência:** impacto principal (C/I/A, compliance, financeiro)

### Avaliação
- **Probabilidade (P):** 1–5 (conforme metodologia)
- **Impacto (I):** 1–5 (conforme metodologia)
- **Nível de Risco (P x I):** matriz (ex.: 1–25)
- **Criticidade:** (Baixo/Médio/Alto/Crítico) conforme faixas

### Tratamento e governança
- **Estratégia:** Mitigar / Transferir / Evitar / Aceitar
- **Controles existentes:** o que já reduz risco hoje
- **Plano de ação:** ações para reduzir risco (com prazos e responsáveis)
- **Dono do risco (Risk Owner):** responsável final pelo risco
- **Owner técnico:** time responsável pela execução do tratamento
- **Prazo alvo:** data para conclusão do plano
- **Status:** Aberto / Em andamento / Mitigado / Aceito / Encerrado
- **Risco residual:** nível após tratamento (quando aplicável)
- **Aceite de risco:** (Sim/Não) + referência/justificativa + expiração

---

## 3) Tabela principal (para planilha)

> Dica: copie esta tabela para um arquivo `.md` ou para uma planilha.  
> Se quiser, depois criamos a versão em CSV/Sheets para dashboard.

| ID | Domínio | Ativo/Serviço | Descrição do risco | Causa | Consequência | Controles existentes | P (1-5) | I (1-5) | Nível (PxI) | Criticidade | Estratégia | Plano de ação | Risk Owner | Owner técnico | Prazo alvo | Status | Risco residual | Aceite? | Expira em | Evidências/Links |
|---|---|---|---|---|---|---|---:|---:|---:|---|---|---|---|---|---:|---|---|---|---:|---|
| RR-0001 |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |

---

## 4) Regras de operação (simples e eficaz)

- Todo risco deve ter **Risk Owner** definido.
- Risco “Mitigado/Encerrado” exige evidência (ex.: mudança implementada, controle ativo).
- Riscos “Aceitos” devem ter **prazo de expiração** e revisão.
- Revisar riscos **Altos/Críticos** em cadência mais curta (semanal/quinzenal), conforme maturidade.

---
