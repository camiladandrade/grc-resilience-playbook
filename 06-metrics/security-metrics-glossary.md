# Glossário de Métricas — Segurança da Informação (GRC, VM, IR, Resiliência)

Este glossário padroniza termos e definições para evitar ambiguidade em relatórios e dashboards.

> Objetivo: garantir que “o número” signifique a mesma coisa para Segurança, TI e Liderança.

---

## 1) Conceitos de risco (GRC)

### Risco
Probabilidade de um evento ocorrer e causar impacto nos objetivos do negócio (C/I/A, financeiro, compliance, reputação).

### Risco inerente
Risco **antes** de considerar controles existentes e ações de tratamento.

### Risco residual
Risco **após** considerar controles existentes e ações de tratamento (o risco que “sobra”).

### Criticidade do risco
Classificação (Baixo/Médio/Alto/Crítico) a partir da pontuação **P x I** e das faixas definidas em `risk-methodology.md`.

### Aceite de risco
Decisão formal de **não tratar** (ou postergar tratamento) de um risco, com justificativa, aprovação e **data de expiração**.

### Plano de tratamento de risco
Conjunto de ações para reduzir probabilidade e/ou impacto, com owner, prazo e evidências.

---

## 2) Métricas de vulnerabilidades (VM)

### Vulnerabilidade
Falha ou fraqueza que pode ser explorada para comprometer a confidencialidade, integridade ou disponibilidade.

### Severidade (Crítica/Alta/Média/Baixa)
Classificação baseada em score técnico (ex.: CVSS) e/ou critérios internos.

### SLA de correção (compliance)
Percentual de vulnerabilidades corrigidas **dentro do prazo** definido por severidade.

**Exemplo de definição:**  
SLA Críticas = (Críticas corrigidas dentro do SLA / total de Críticas vencidas no período) × 100

### MTTR (Mean Time To Remediate) — Vulnerabilidades
Tempo médio entre a **detecção** da vulnerabilidade e sua **correção/mitigação validada**.

### Backlog de vulnerabilidades
Quantidade de vulnerabilidades **abertas** (pode ser segmentado por severidade e por aging).

### Aging (envelhecimento)
Tempo que um item permanece aberto. Ex.: “Críticas com aging > 30 dias”.

### Exceção de vulnerabilidade
Autorização formal para **não corrigir** dentro do SLA por justificativa (ex.: limitação técnica), com mitigação compensatória e expiração.

---

## 3) Métricas de incidentes (IR)

### Evento de segurança
Ocorrência relevante (alerta/log) que pode ou não se tornar um incidente.

### Incidente de segurança
Evento confirmado que compromete (ou tem potencial de comprometer) C/I/A ou requisitos regulatórios/contratuais.

### MTTD (Mean Time To Detect)
Tempo médio entre o **início estimado** do incidente e sua **detecção**.

> Depende de estimativa do “início”, então é comum usar “primeiro sinal disponível” como referência quando necessário.

### MTTA (Mean Time To Acknowledge)
Tempo médio entre a detecção e o **reconhecimento/acionamento** (ex.: abrir o ticket e mobilizar time).

### MTTC (Mean Time To Contain)
Tempo médio entre a detecção e a **contenção** (interromper propagação/abuso).

### MTTR (Mean Time To Recover) — Incidentes
Tempo médio entre a detecção e a **recuperação** (restabelecer operação/serviço com estabilidade).

> Em algumas organizações, MTTR é “Recover”. Para evitar confusão com VM, deixe explícito no relatório.

### PIR (Post-Incident Review) — Relatório Pós-Incidente
Revisão formal pós-incidente: timeline, causa raiz, lições aprendidas e plano de ações corretivas.

### Taxa de PIR no prazo
% de incidentes que exigem PIR e tiveram PIR concluído dentro do prazo definido (ex.: 5 ou 10 dias úteis).

---

## 4) Métricas de resiliência (BIA/BCP/DR)

### BIA (Business Impact Analysis)
Análise que identifica criticidade, impactos por tempo e dependências, resultando em MTPD, RTO e RPO.

### MTPD (Maximum Tolerable Period of Disruption)
Tempo máximo tolerável de interrupção pelo negócio.

### RTO (Recovery Time Objective)
Tempo-alvo para restaurar o serviço após interrupção.

### RPO (Recovery Point Objective)
Ponto máximo aceitável de perda de dados (em tempo).

### Restore Drill (Teste de restauração)
Teste prático de restauração a partir de backups (valida integridade e tempo).

### DR Test (Teste de Disaster Recovery)
Teste de failover/fallback para ambiente secundário, validando recuperação em cenário de desastre.

### % de testes que atingiram RTO/RPO
Percentual de testes em que o tempo real (medido) ficou dentro do objetivo definido.

---

## 5) Métricas de auditoria e conformidade (ISO 27001)

### NC (Não Conformidade)
Requisito não atendido (ISO 27001, SoA, política interna, requisito legal/contratual).

### OM (Oportunidade de Melhoria)
Melhoria recomendada, sem caracterizar NC, mas com ganho de maturidade/efetividade.

### CAPA (Ação corretiva e preventiva)
Plano de ação para corrigir causa raiz de uma NC e prevenir recorrência (com owner, prazo, evidência).

### Taxa de CAPAs no prazo
% de ações corretivas concluídas dentro do prazo acordado.

### SoA (Declaração de Aplicabilidade)
Documento que lista controles do Anexo A, marcando aplicabilidade, justificativas, e como/onde são implementados.

---

## 6) Boas práticas para relatórios e dashboards

- Sempre informar: **definição**, **período**, **fonte**, **escopo** e **limitações**.
- Separar MTTR de VM vs MTTR de IR (ou usar nomes explícitos: MTTR-VM / MTTR-IR).
- Preferir **tendências** (3–6 meses) a “número do mês” isolado.
- Segmentar quando útil: por área, serviço, severidade, Tier e fornecedor.

---
