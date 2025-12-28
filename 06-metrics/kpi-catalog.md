# Catálogo de KPIs — Segurança da Informação (GRC & Resiliência)

Este catálogo reúne KPIs para **liderança de Segurança**, cobrindo Governança, Riscos, Resiliência, Vulnerabilidades e Incidentes.

> Objetivo: medir maturidade, orientar decisões e comunicar progresso de forma executiva.

---

## 1) Padrão de definição de KPI (como usar)

Para cada KPI, definir:
- **Nome**
- **Objetivo**
- **Fórmula/Definição**
- **Fonte de dados**
- **Periodicidade**
- **Owner**
- **Meta/Threshold**
- **Notas** (limitações, segmentações)

**Legenda de status (sugestão):**
- 🟢 Dentro da meta
- 🟡 Atenção
- 🔴 Fora da meta

---

## 2) KPIs por domínio

### 2.1 Governança do SGSI
**KPI G1 — % de políticas revisadas no prazo**
- Objetivo: garantir governança atualizada
- Definição: (políticas revisadas no prazo / total de políticas) x 100
- Fonte: repositório documental / lista mestra
- Periodicidade: mensal
- Owner: GRC
- Meta: ≥ 90%

**KPI G2 — % de ações corretivas (CAPA) concluídas no prazo**
- Definição: (CAPAs concluídas no prazo / total de CAPAs) x 100
- Fonte: tracker de auditoria / tickets
- Periodicidade: mensal
- Owner: GRC / Donos das ações
- Meta: ≥ 85%

**KPI G3 — Tempo médio para fechamento de Não Conformidades (NC)**
- Definição: média de dias entre abertura e fechamento de NC
- Periodicidade: mensal/trimestral
- Owner: GRC
- Meta: depende do apetite (ex.: ≤ 60 dias)

---

### 2.2 Gestão de Riscos
**KPI R1 — % de riscos Altos/Críticos com plano de tratamento ativo**
- Definição: (riscos altos/críticos com plano / total de riscos altos/críticos) x 100
- Fonte: Risk Register
- Periodicidade: mensal
- Owner: GRC + Risk Owners
- Meta: 100%

**KPI R2 — Envelhecimento (aging) de riscos Altos/Críticos**
- Definição: nº de riscos altos/críticos sem revisão há > X dias
- Fonte: Risk Register (data da última revisão)
- Periodicidade: mensal
- Owner: GRC
- Meta: 0

**KPI R3 — % de riscos aceitos dentro do prazo de expiração**
- Definição: (aceites vigentes / total de aceites) x 100
- Fonte: Risk Register (aceite + expiração)
- Periodicidade: mensal
- Owner: GRC
- Meta: 100%

---

### 2.3 Resiliência (BIA/BCP/DR)
**KPI B1 — % de serviços Tier-0/Tier-1 com BIA atualizado**
- Definição: (serviços Tier-0/1 com BIA < 12 meses / total Tier-0/1) x 100
- Fonte: inventário + BIA
- Periodicidade: mensal
- Owner: Resiliência/GRC + Service Owners
- Meta: ≥ 90%

**KPI B2 — % de serviços Tier-0/Tier-1 com BCP e DRP atualizados**
- Definição: (serviços com BCP+DRP atualizados / total Tier-0/1) x 100
- Periodicidade: mensal
- Owner: Resiliência + TI
- Meta: ≥ 85%

**KPI B3 — Taxa de execução do plano de testes de resiliência**
- Definição: (testes realizados / testes planejados) x 100
- Periodicidade: trimestral
- Owner: Resiliência
- Meta: ≥ 90%

**KPI B4 — % de testes que atingiram RTO**
- Definição: (testes com RTO atingido / total de testes) x 100
- Periodicidade: trimestral
- Owner: TI/Resiliência
- Meta: ≥ 85%

**KPI B5 — % de testes que atingiram RPO**
- Definição: (testes com RPO atingido / total de testes) x 100
- Periodicidade: trimestral
- Owner: TI/Resiliência
- Meta: ≥ 85%

---

### 2.4 Gestão de Vulnerabilidades (alto nível)
**KPI V1 — SLA de correção por criticidade (compliance)**
- Definição: % de vulnerabilidades corrigidas dentro do SLA, por severidade (Crítica/Alta/Média)
- Fonte: scanner + sistema de tickets
- Periodicidade: semanal/mensal
- Owner: VM
- Meta: Críticas ≥ 95% dentro do SLA

**KPI V2 — Tempo médio de correção (MTTR) por severidade**
- Definição: média de dias entre detecção e correção
- Periodicidade: mensal
- Owner: VM
- Meta: reduzir tendência

**KPI V3 — Backlog de vulnerabilidades críticas (abertas)**
- Definição: total de críticas abertas (e aging > X dias)
- Periodicidade: semanal
- Owner: VM
- Meta: 0 (ou o mínimo possível)

---

### 2.5 Incidentes (IR)
**KPI I1 — MTTD (Tempo médio para detectar)**
- Definição: média do tempo entre início estimado e detecção
- Periodicidade: mensal/trimestral
- Owner: SOC/IR
- Meta: reduzir tendência

**KPI I2 — MTTR (Tempo médio para conter/recuperar)**
- Definição: média do tempo entre detecção e contenção/recuperação
- Periodicidade: mensal/trimestral
- Owner: IR + TI
- Meta: reduzir tendência

**KPI I3 — % de incidentes com PIR concluído no prazo**
- Definição: (PIRs no prazo / incidentes que exigem PIR) x 100
- Periodicidade: mensal
- Owner: IR Lead/GRC
- Meta: ≥ 90%

---

## 3) Observações e boas práticas

- Separe métricas **operacionais** (semanal) de métricas **executivas** (mensal/trimestral).
- Padronize definição e fonte para evitar “disputa de número”.
- Prefira tendências (3–6 meses) a números isolados.
- Use metas realistas (baseline primeiro, meta depois).

---
