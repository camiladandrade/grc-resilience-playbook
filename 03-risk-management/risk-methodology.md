# Risk Methodology — Metodologia de Avaliação de Riscos (GRC)

Este documento define a metodologia padrão para **identificação, avaliação, tratamento e monitoramento** de riscos de Segurança da Informação, para uso no `03-risk-management/risk-register-template.md`.

> Objetivo: padronizar critérios (probabilidade/impacto), faixas de criticidade, risco residual e regras de aceite.

---

## 1) Escopo e princípios

### 1.1 Escopo
Aplicável a riscos relacionados a:
- Segurança da Informação (C/I/A)
- Privacidade (LGPD)
- Continuidade/Resiliência (BIA, DR, indisponibilidade)
- Terceiros e cadeia de suprimentos
- Pessoas, processos e tecnologia

### 1.2 Princípios
- **Consistência:** mesmos critérios para toda a organização
- **Rastreabilidade:** risco sempre com owner, evidência e revisão
- **Contexto importa:** “CVSS/tecnicalidade” não substitui impacto de negócio
- **Decisão explícita:** aceitar risco é uma decisão formal (com expiração)

---

## 2) Processo de Gestão de Riscos (macro)

1. **Identificar** o risco (evento, causa, consequência)
2. **Avaliar** risco inerente (antes de controles) — P x I
3. **Analisar controles existentes** (o que já reduz risco)
4. **Definir tratamento** (mitigar/transferir/evitar/aceitar)
5. **Reavaliar** risco residual (após ações/controles)
6. **Monitorar** (revisão periódica + gatilhos de reavaliação)

---

## 3) Escala de Probabilidade (P) — 1 a 5

Avalie a chance de o evento ocorrer, considerando:
- histórico (interno/externo)
- exposição (internet-facing, superfície de ataque)
- maturidade de controles
- atratividade para ameaças

| P | Nível | Descrição (guia) |
|---:|---|---|
| 1 | Raro | não há histórico, controles fortes, exposição baixa |
| 2 | Improvável | pode ocorrer, mas exigiria condições específicas |
| 3 | Possível | pode ocorrer em condições comuns; já visto em mercado |
| 4 | Provável | ocorre com certa frequência; controles têm lacunas |
| 5 | Quase certo | ocorrência recorrente/ativa; controle ausente ou falho |

---

## 4) Escala de Impacto (I) — 1 a 5

Avalie o impacto **máximo plausível**, considerando:
- indisponibilidade (RTO/RPO, downtime)
- vazamento de dados (PII, segredos, propriedade intelectual)
- fraude/perdas financeiras
- compliance (LGPD/contratos)
- reputação e operação

| I | Nível | Descrição (guia) |
|---:|---|---|
| 1 | Insignificante | impacto mínimo, sem afetar operações ou compliance |
| 2 | Baixo | impacto limitado/local, recuperação rápida |
| 3 | Moderado | impacto relevante, afeta times/processos; possível exposição limitada |
| 4 | Alto | afeta serviços críticos, perdas financeiras relevantes ou exposição significativa |
| 5 | Crítico | paralisação ampla, grande vazamento/fraude, risco regulatório alto |

> Dica: quando houver dúvida entre dois níveis, use o mais alto (conservador) e registre a justificativa.

---

## 5) Cálculo do Nível de Risco (P x I)

### 5.1 Fórmula
- **Risco = P x I** → faixa de 1 a 25

### 5.2 Faixas de criticidade (sugestão)
| Pontuação | Criticidade |
|---:|---|
| 1–4 | Baixo |
| 5–9 | Médio |
| 10–14 | Alto |
| 15–25 | Crítico |

---

## 6) Matriz 5x5 (referência)

> Use como referência visual na avaliação.

- **Eixo X:** Impacto (1–5)  
- **Eixo Y:** Probabilidade (1–5)

Exemplos de leitura:
- P=5, I=5 → 25 (Crítico)
- P=4, I=3 → 12 (Alto)
- P=2, I=2 → 4 (Baixo)

---

## 7) Risco inerente vs risco residual

### 7.1 Definições
- **Risco inerente:** risco antes de controles/ações (baseline)
- **Risco residual:** risco após controles/ações de mitigação

### 7.2 Regras
- Sempre registrar **controles existentes** e como eles reduzem P e/ou I
- Recalcular P e I após o plano de ação para estimar o residual
- Risco residual “Alto/Crítico” exige decisão e acompanhamento formal

---

## 8) Estratégias de tratamento

| Estratégia | Quando usar | Exemplos |
|---|---|---|
| Mitigar | reduzir P e/ou I com controles | hardening, MFA, segmentação, backups imutáveis |
| Transferir | repassar parte do risco | seguro, contrato/terceiro, cláusulas e SLAs |
| Evitar | remover a atividade que gera o risco | descontinuar sistema, remover exposição |
| Aceitar | custo/viabilidade não justificam mitigação agora | aceite formal com expiração e revisão |

---

## 9) Aceite de risco (governança)

### 9.1 Regras
Um risco só pode ser “Aceito” se:
- existir **Risk Owner** (responsável final)
- houver justificativa e contexto
- houver **data de expiração** (obrigatória)
- existirem controles compensatórios quando aplicável
- houver registro de aprovação (assinatura/registro)

### 9.2 Quando NÃO aceitar
- risco crítico sem controles compensatórios mínimos
- risco com obrigação legal clara (ex.: privacidade) sem avaliação jurídica
- risco que esteja em exploração ativa ou com incidente em andamento

---

## 10) Cadência de revisão (sugestão)

- **Crítico:** semanal/quinzenal
- **Alto:** mensal
- **Médio:** trimestral
- **Baixo:** semestral/anual

**Gatilhos de reavaliação imediata:**
- incidente real relacionado ao risco
- mudança em escopo/infra (cloud migration, novo fornecedor, produto)
- descoberta de vulnerabilidade crítica em ativo relacionado
- mudança regulatória/contratual

---

## 11) Artefatos e rastreabilidade

Requisitos mínimos no Risk Register:
- ID único do risco
- descrição no formato “Se X, então Y, resultando em Z”
- P, I, pontuação e criticidade
- controles existentes
- estratégia + plano de ação (owner + prazo)
- risco residual
- evidências e links (tickets, auditorias, relatórios)

---
