# Auditoria — ISO 27001 (Índice)

Esta pasta reúne artefatos para **auditoria interna** e preparação para auditorias externas do SGSI, com foco em rastreabilidade, evidências e plano de ação (NC/CAPA).

> Fluxo recomendado: **Plano de Auditoria → Coleta/Organização de Evidências → Checklist de Controles → Achados e Ações Corretivas**

---

## 📌 Índice

### 1) Planejamento de auditoria
- **Plano de Auditoria Interna (template)**  
  `internal-audit-plan-template.md`  
  Define escopo, critérios, agenda, metodologia, amostragem, papéis e entregáveis.

### 2) Evidências (Evidence Pack)
- **Estrutura do Pacote de Evidências (template)**  
  `evidence-pack-structure.md`  
  Define como organizar evidências para auditoria (pastas, nomenclatura, índice mestre e qualidade).

### 3) Checklist de controles (Anexo A)
- **Checklist de Controles — ISO 27001 (Anexo A)**  
  `iso27001-controls-checklist.md`  
  Checklist prático para marcar aplicabilidade, status, evidências, owners e achados.

---

## ✅ Como usar (passo a passo)

1. **Preparar o plano**
   - preencher `internal-audit-plan-template.md`
   - confirmar escopo do SGSI e critérios (ISO 27001, SoA, políticas internas)

2. **Organizar evidências**
   - criar estrutura do Evidence Pack com `evidence-pack-structure.md`
   - (recomendado) manter um índice mestre de evidências (planilha)

3. **Executar auditoria (amostragem + entrevistas)**
   - usar `iso27001-controls-checklist.md`
   - coletar evidências por período e por controle/processo

4. **Registrar achados e acompanhar ações**
   - classificar: NC / Observação / Oportunidade de Melhoria
   - criar ações corretivas (CAPA) com owner, prazo e evidência de encerramento

---

## 📎 Boas práticas

- “Documento existe” não basta: sempre buscar evidência de **execução e efetividade**.
- Controles recorrentes (VM, backup, logs, IR) exigem **amostras** do período auditado.
- Achados relevantes devem alimentar o **Risk Register** quando aplicável.
- Sanitizar evidências (sem credenciais, PII ou dados sensíveis).

---
