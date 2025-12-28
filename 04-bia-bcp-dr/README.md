# Resiliência — BIA • BCP • DR (Índice)

Esta pasta reúne os artefatos de **Resiliência/Continuidade**: análise de impacto, objetivos de recuperação, planos de continuidade e recuperação técnica, e o plano de testes para validar na prática.

> Fluxo recomendado: **BIA → RTO/RPO → BCP → DRP → Testes**

---

## 📌 Índice

### 1) BIA (Business Impact Analysis)
- **Template de BIA**  
  `bia-template.md`  
  Identifica processos/serviços críticos, dependências e impactos por tempo.

---

### 2) Diretrizes de RTO/RPO
- **Guia para definição de RTO/RPO**  
  `rto-rpo-guidelines.md`  
  Padroniza como escolher RTO/RPO com base no BIA e viabilidade técnica.

---

### 3) Plano de Continuidade (BCP)
- **Template de BCP (Continuidade do Negócio)**  
  `bcp-template.md`  
  Define como operar em **modo degradado**, com comunicação, papéis e checklists.

---

### 4) Plano de Recuperação (DRP)
- **Template de DRP (Recuperação Técnica / DR)**  
  `drp-template.md`  
  Define como recuperar serviços/sistemas com ordem de dependências, validação e evidências, alinhado a RTO/RPO.

---

### 5) Plano de Testes
- **Plano de Testes de Resiliência (BCP/DR)**  
  `testing-plan.md`  
  Calendário e padrões de teste (tabletop, restore drill, DR test), evidências e KPIs.

---

## ✅ Como usar (passo a passo)

1. **Concluir o BIA** (`bia-template.md`)
   - definir criticidade (Tier)
   - mapear dependências
   - quantificar impactos por tempo

2. **Definir RTO/RPO** (`rto-rpo-guidelines.md`)
   - validar consistência com capacidade técnica
   - registrar gaps como riscos (se necessário)

3. **Escrever o BCP** (`bcp-template.md`)
   - modo degradado e workarounds
   - cadência e mensagens de comunicação

4. **Escrever o DRP** (`drp-template.md`)
   - ordem de recuperação e estratégia (restore/failover/rebuild)
   - validação técnica e de negócio

5. **Testar e melhorar** (`testing-plan.md`)
   - medir RTO/RPO reais
   - gerar evidências
   - atualizar planos com lições aprendidas

---

## 📎 Boas práticas

- Planos devem ter **owner**, **versão**, **revisão periódica** e **aprovações**.
- Testes devem gerar **evidências** (logs/prints/IDs) e **plano de ação** (owner + prazo).
- RTO/RPO desejados e inviáveis devem virar **roadmap** (maturidade) ou **revisão do BIA** (decisão do negócio).

---
