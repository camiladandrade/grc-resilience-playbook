# RTO/RPO Guidelines — Diretrizes para definição de RTO e RPO

Este guia padroniza como definir **RTO** e **RPO** de forma consistente, baseada em impacto de negócio e capacidade técnica, usando como insumo o `bia-template.md`.

> Objetivo: evitar RTO/RPO “chutados”, alinhar expectativas com negócio e viabilizar planos de continuidade (BCP) e recuperação (DR).

---

## 1) Conceitos (alinhamento rápido)

- **RTO (Recovery Time Objective):** tempo-alvo para restaurar o serviço após interrupção.
- **RPO (Recovery Point Objective):** ponto máximo aceitável de perda de dados (tempo entre o último backup/replicação e a falha).
- **MTPD (Maximum Tolerable Period of Disruption):** tempo máximo tolerável de interrupção pelo negócio.

> Regra: **RTO deve ser ≤ MTPD**.

---

## 2) Como definir RTO (passo a passo)

### 2.1 Comece pelo impacto do BIA
No `bia-template.md`, observe em que janela o impacto vira **Alto/Crítico**.  
O RTO deve ser **menor** do que o ponto em que a operação/negócio se torna inaceitável.

### 2.2 Considere criticidade e dependências
Serviços que suportam outros serviços (ex.: identidade, DNS, rede, banco de dados) tendem a ter RTO mais agressivo.

### 2.3 Valide viabilidade técnica
Um RTO agressivo exige capacidade compatível:
- automação de restore
- failover/fallback
- equipe e suporte 24x7 quando necessário
- monitoramento e runbooks

> Se não for viável hoje, registre o gap e crie plano de evolução (maturidade).

---

## 3) Como definir RPO (passo a passo)

### 3.1 Determine o “quanto de dado pode perder”
Baseado em:
- tolerância do negócio a reprocessamento
- volume/transações por hora
- risco regulatório/contratual (ex.: dados financeiros, PII)

### 3.2 Conecte RPO a mecanismos reais
RPO baixo requer:
- replicação (quase em tempo real) **ou**
- backups muito frequentes **ou**
- arquitetura que reduz perda (journaling, logs transacionais)

> Se o sistema só faz backup diário, **não existe RPO de 1h** na prática.

---

## 4) Faixas recomendadas (para padronizar)

Use faixas como “menus” para evitar escolhas arbitrárias.

### 4.1 Faixas de RTO (sugestão)
- **RTO 1 — Muito baixo:** 0–2h
- **RTO 2 — Baixo:** 2–8h
- **RTO 3 — Moderado:** 8–24h
- **RTO 4 — Alto:** 1–3 dias
- **RTO 5 — Muito alto:** 3–7 dias

### 4.2 Faixas de RPO (sugestão)
- **RPO 1 — Muito baixo:** 0–15 min
- **RPO 2 — Baixo:** 15 min–1h
- **RPO 3 — Moderado:** 1–8h
- **RPO 4 — Alto:** 8–24h
- **RPO 5 — Muito alto:** 1–3 dias

---

## 5) Mapeamento por criticidade (exemplo)

> Ajuste conforme a realidade da organização. Isso é um ponto de partida.

- **Tier-0 (crítico):**
  - RTO: RTO 1–2 (0–8h)
  - RPO: RPO 1–2 (0–1h)
- **Tier-1 (alto):**
  - RTO: RTO 2–3 (2–24h)
  - RPO: RPO 2–3 (15 min–8h)
- **Tier-2 (moderado):**
  - RTO: RTO 3–5 (8h–7d)
  - RPO: RPO 3–5 (1h–3d)

> Observação: sistemas que suportam identidade/autenticação (IdP/AD/DNS) frequentemente são Tier-0.

---

## 6) Regras e anti-padrões (o que evitar)

### 6.1 Anti-padrões
- Definir RTO/RPO sem BIA (“porque sim”)
- RPO irreal (ex.: 15 min com backup diário)
- RTO agressivo sem equipe, automação ou runbook
- Não considerar dependências (o sistema “depende” de outro com RTO pior)

### 6.2 Regras práticas
- RTO/RPO devem ser aprovados por **Business Owner** e **IT Owner**
- Se o gap for grande entre desejado e viável:
  - registrar como risco (Risk Register)
  - criar roadmap (melhoria de resiliência)

---

## 7) Como registrar (padrão no BIA)

No `bia-template.md`, registrar:
- MTPD, RTO e RPO
- Justificativa (impacto e tolerância)
- Capacidade atual (backup/replicação/restore)
- Gaps e plano de evolução (se aplicável)

---

## 8) Validação por testes (obrigatório para maturidade)

Definições só se tornam confiáveis quando testadas:
- **Tabletop:** simulação de interrupção (fluxo e decisões)
- **Restore Drill:** teste real de restauração
- **DR Test:** failover/fallback (quando aplicável)

> Recomenda-se no mínimo **1 teste por semestre** para serviços Tier-0/Tier-1.

---
