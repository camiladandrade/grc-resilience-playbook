# 🗺️ ROADMAP — GRC & Resilience Playbook (ISO 27001 • NIST • LGPD)

Este roadmap organiza as entregas do repositório em **milestones** para construir um playbook de **GRC e Resiliência** com foco em **liderança**, **governança operável**, **audit readiness** e **decisão executiva**.

📌 Objetivo do repositório:
Entregar artefatos “com cara de empresa” para estruturar e operar:
- Gestão de Riscos (metodologia, matriz, Risk Register, exceções e aceite)
- Resiliência (BIA/BCP/DR + testes e programa anual)
- Auditoria interna ISO 27001 (evidence pack + CAPA)
- Métricas executivas (KPI/KRI + relatório decisão-orientada)

---

## ✅ Definição de pronto (Definition of Done)

Uma entrega está “pronta” quando:
- Está em **PT-BR**, clara e aplicável.
- Tem **objetivo + quando usar + inputs/outputs** no topo.
- Indica **owner/responsável** quando aplicável.
- Possui **exemplo fictício** (mínimo: template preenchido OU dataset/ata simulada).
- Está **linkada** no README raiz e no README da pasta correspondente.
- Evita “parecer academia”: é curta, auditável e operacional.

---

## 🧱 M0 — Repo Product Ready (higiene + navegação)
**Por quê (liderança):** repos bem estruturados passam maturidade e facilitam “leitura de recrutador”.

### Entregas
- [ ] `ROADMAP.md` (este arquivo)
- [ ] `CHANGELOG.md`
- [ ] `LICENSE` (MIT ou CC BY 4.0)
- [ ] `DISCLAIMERS.md`
- [ ] README raiz: Quick Start com links válidos
- [ ] Padronizar READMEs de cada pasta (mesmo template)

### Pacote de commits sugerido
- `chore: add roadmap, changelog, license and disclaimers`
- `docs: update root README quickstart + repo map`
- `docs: standardize folder READMEs`

---

## 🧭 M1 — Operating Model de GRC (a peça que mais vende liderança)
**Skills-alvo:** Security Operating Model; comitê/ritual de risco; storytelling executivo; alinhamento cross-functional.

### Entregas (criar `00-operating-model/`)
- [ ] `00-operating-model/README.md`
- [ ] `00-operating-model/grc-operating-model-1pager.md`
- [ ] `00-operating-model/governance-cadence.md` (rituais + pautas + outputs)
- [ ] `00-operating-model/raci-and-ownership.md`
- [ ] `00-operating-model/decision-log-template.md`
- [ ] `00-operating-model/exception-waiver-governance.md` (transversal)

### Pacote de commits sugerido
- `docs: add GRC operating model 1-pager`
- `docs: add governance cadence + RACI + decision log`
- `docs: add exception/waiver governance (cross-domain)`

---

## 📜 M2 — Policies & Standards (pirâmide + aplicabilidade)
**Skills-alvo:** Framework design (policies/standards/guidelines); política viável + critérios de exceção; comunicação interna do framework.

### Entregas
`01-policies/`
- [ ] `policy-information-security.md` (macro, curto)
- [ ] `policy-risk-management.md`
- [ ] `policy-third-party-risk.md` (forte para liderança)
- [ ] `policy-incident-management.md` (alto nível, link para repo IR)

`02-standards/`
- [ ] `standard-risk-assessment.md`
- [ ] `standard-evidence-management.md` (naming/retention/traceability)
- [ ] `standard-policy-deployment-governance.md` (adoção + exceções controladas)
- [ ] `standard-vulnerability-management.md` (integração com VM lab)

### Pacote de commits sugerido
- `docs: add baseline policies (short, executive)`
- `docs: add operational standards (how-to)`
- `docs: add policy deployment governance standard`

---

## 🧩 M3 — Risk Management “auditável e executável”
**Skills-alvo:** matriz consistente; risk register governance (owners/aging/cadência); risk acceptance; governança de exceções lifecycle; melhoria de decisões.

### Entregas (evoluir `03-risk-management/`)
- [ ] `risk-treatment-plan-template.md`
- [ ] `risk-register-example-filled.md` (fictício)
- [ ] `risk-appetite-and-thresholds.md` (limiares práticos)
- [ ] `risk-committee-charter.md` (cadência + pauta + decisões)
- [ ] `kri-pack-risk.md` (KRIs básicos de risco)
- [ ] Revisar os existentes para “audit-ready” (metodologia, matriz, evidências)

### Pacote de commits sugerido
- `docs: add risk treatment plan + filled risk register example`
- `docs: add risk appetite thresholds + risk committee charter`
- `docs: add risk KRI pack + strengthen traceability`

---

## 🛡️ M4 — Resiliência (programa anual BIA/BCP/DR)
**Skills-alvo:** tabletop; programa de testes; métricas de resiliência; crise/cyber readiness (quando aplicável).

### Entregas (evoluir `04-bia-bcp-dr/`)
- [ ] `resilience-program-1pager.md`
- [ ] `critical-services-inventory-template.md`
- [ ] `dependency-mapping-template.md`
- [ ] `test-report-template.md`
- [ ] `lessons-learned-and-improvement-log.md`
- [ ] (opcional) `executive-tabletop-guide.md` (roteiro COMEX)

### Pacote de commits sugerido
- `docs: add resilience program 1-pager`
- `templates: add critical services + dependency mapping`
- `templates: add test report + improvement log`
- `docs: add executive tabletop guide (optional)`

---

## 🧾 M5 — Auditoria ISO 27001 (evidence pack “usable” + CAPA)
**Skills-alvo:** audit evidence pack skeleton; prontidão para auditoria; CAPA sem recorrência; gestão de findings.

### Entregas (evoluir `05-audit-iso27001/`)
- [ ] `audit-workpapers-template.md`
- [ ] `capa-playbook.md` (como tratar achados e fechar sem recorrência)
- [ ] `sample-evidence-pack/` (fictício)
  - [ ] `index.md`
  - [ ] `sample-policy-approval.md`
  - [ ] `sample-risk-review-minutes.md`
  - [ ] `sample-control-testing-notes.md`

### Pacote de commits sugerido
- `docs: add audit workpapers + CAPA playbook`
- `docs: add sample evidence pack (fictional, usable)`

---

## 📊 M6 — Métricas executivas (KPI/KRI + decisão)
**Skills-alvo:** KPI pack enxuto e acionável; KPI de governança; KRIs básicos; executive storytelling.

### Entregas (evoluir `06-metrics/`)
- [ ] `kpi-kri-thresholds.md` (limiares + gatilhos)
- [ ] `metrics-governance.md` (frequência, dono, qualidade do dado)
- [ ] `monthly-exec-report-example-filled.md` (fictício)
- [ ] Revisar o relatório executivo para formato decisão-orientada (menos métricas, mais decisão)

### Pacote de commits sugerido
- `docs: add KPI/KRI thresholds + metrics governance`
- `docs: add filled executive report example (fictional)`
- `docs: upgrade executive report to decision-driven format`

---

## 🗂️ M7 — Case Studies (3 casos “pasta de entrevista”)
**Skills-alvo:** storytelling executivo; audit readiness; risk governance; resiliência.

### Entregas (criar `08-case-studies/`)
- [ ] `08-case-studies/README.md`
- [ ] `case-01-risk-acceptance-and-compensating-controls/`
- [ ] `case-02-bia-to-bcp-program/`
- [ ] `case-03-iso27001-internal-audit-and-capa/`

**Formato padrão de cada case**
- `contexto.md` • `artefatos.md` • `decisoes.md` • `evidencias.md` • `resultado.md`

### Pacote de commits sugerido
- `cases: add case study structure + template`
- `cases: add case 01 (risk acceptance)`
- `cases: add case 02 (BIA -> BCP program)`
- `cases: add case 03 (internal audit -> CAPA)`
