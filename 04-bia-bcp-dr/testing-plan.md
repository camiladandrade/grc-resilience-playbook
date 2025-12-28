# Testing Plan — Resiliência (BCP/DR) — Plano de Testes

Este documento define o **plano de testes** para Continuidade (BCP) e Recuperação (DRP), garantindo que **RTO/RPO** e procedimentos sejam **validados na prática**, com evidências e melhoria contínua.

> Relacionados:
- `bia-template.md`
- `rto-rpo-guidelines.md`
- `bcp-template.md`
- `drp-template.md`

---

## 1) Objetivos do plano de testes

- Validar se RTO/RPO definidos no BIA são **atingíveis**
- Exercitar papéis, comunicação e tomada de decisão
- Testar procedimentos de workaround (BCP) e recuperação técnica (DRP)
- Detectar lacunas (pessoas, acessos, ferramentas, dependências)
- Gerar evidências para auditoria e governança
- Alimentar melhoria contínua (backlog de resiliência)

---

## 2) Escopo e criticidade

### 2.1 Serviços/processos em escopo
Liste os serviços com BIA concluído (mínimo Tier-0/Tier-1).

| Serviço/Processo | Tier | RTO | RPO | Dono do Serviço | DRP existe? | BCP existe? |
|---|---|---:|---:|---|---|---|
|  |  |  |  |  | Sim/Não | Sim/Não |

### 2.2 Frequência mínima por criticidade (sugestão)
- **Tier-0:** 2 testes/ano (mínimo) + restore drill semestral
- **Tier-1:** 1 teste/ano (mínimo)
- **Tier-2:** conforme criticidade e mudanças relevantes

> Gatilhos de teste extra: mudanças grandes (migração cloud, novo fornecedor), incidentes reais, falhas de backup, auditoria.

---

## 3) Tipos de teste (catálogo)

### 3.1 Tabletop (simulação guiada)
**O que valida:** decisão, comunicação, papéis, fluxos, gatilhos e priorização.  
**Duração típica:** 60–120 min.  
**Evidências:** ata, decisões, gaps, plano de ação.

### 3.2 Exercício de continuidade (workaround / modo degradado)
**O que valida:** execução real do BCP (processo manual/alternativo).  
**Duração:** 2–4h (ou por janela).  
**Evidências:** checklist executada, métricas de operação e falhas.

### 3.3 Restore Drill (teste de restauração)
**O que valida:** restore de backups e integridade/tempo real.  
**Duração:** 2–8h.  
**Evidências:** logs de restore, tempo medido, validação de dados.

### 3.4 Teste de DR (failover/fallback)
**O que valida:** mudança de ambiente (secundário) e retorno controlado.  
**Duração:** 4–24h (ou conforme ambiente).  
**Evidências:** roteiro, tempos, validações e estabilidade.

### 3.5 Teste de cadeia de dependências
**O que valida:** recuperação na ordem correta (identidade, rede, DNS, dados, app).  
**Evidências:** sequência executada, bloqueios, ajustes no DRP.

---

## 4) Planejamento anual (calendário)

> Preencha com datas reais. Mantém previsibilidade e disciplina.

| Mês/Trimestre | Serviço/Processo | Tipo de teste | Responsável | Janela | Status |
|---|---|---|---|---|---|
| T1 |  | Tabletop |  |  | Planejado |
| T2 |  | Restore Drill |  |  | Planejado |
| T3 |  | Exercício BCP |  |  | Planejado |
| T4 |  | Teste DR |  |  | Planejado |

---

## 5) Roteiro padrão do teste (antes, durante e depois)

### 5.1 Antes do teste (preparação)
- [ ] Definir objetivo e escopo do teste
- [ ] Confirmar participantes (negócio + TI + GRC)
- [ ] Confirmar documentos atualizados (BIA/BCP/DRP)
- [ ] Validar acessos necessários (break-glass com governança)
- [ ] Definir critérios de sucesso (RTO/RPO e validações)
- [ ] Definir “plano de reversão” (rollback) quando aplicável

### 5.2 Durante o teste (execução)
- [ ] Registrar linha do tempo (início, marcos, encerramento)
- [ ] Registrar decisões e justificativas
- [ ] Coletar evidências (prints/logs/IDs)
- [ ] Medir tempos reais (restore, validação, estabilização)
- [ ] Capturar bloqueios e falhas

### 5.3 Depois do teste (encerramento)
- [ ] Consolidar resultados (RTO/RPO atingidos?)
- [ ] Documentar gaps (pessoas/processos/tecnologia)
- [ ] Criar plano de ação (owner + prazo + prioridade)
- [ ] Atualizar BCP/DRP conforme lições aprendidas
- [ ] Reportar para liderança (resumo executivo)

---

## 6) Critérios de sucesso (mínimo)

### 6.1 Critérios técnicos
- Restore/failover executado conforme runbook
- Integridade de dados validada (quando aplicável)
- Monitoramento e alertas funcionais durante o recovery

### 6.2 Critérios de negócio
- Fluxos essenciais validados pelo dono do serviço
- Operação em modo normal (ou degradado) estável
- Comunicação feita conforme plano

### 6.3 Critérios de RTO/RPO
- **RTO real (medido)** ≤ RTO definido no BIA
- **Perda real de dados (RPO medido)** ≤ RPO definido no BIA

> Se não atingir: registrar justificativa e plano de evolução (ou revisão do BIA, se necessário).

---

## 7) Evidências (para auditoria e rastreabilidade)

Para cada teste, armazenar:
- plano/escopo do teste
- participantes e datas
- linha do tempo com marcos
- logs/prints/IDs (restore, failover, validações)
- tempos medidos (RTO real e RPO real)
- lista de gaps e plano de ação
- aprovação/ciência do Business Owner e IT Owner

---

## 8) Métricas do programa (KPIs)

Sugestões de KPIs para governança:
- % de serviços Tier-0/Tier-1 com BIA atualizado (últimos 12 meses)
- % de serviços com BCP e DRP atualizados
- Taxa de execução do calendário de testes (planejado vs realizado)
- % de testes que atingiram RTO
- % de testes que atingiram RPO
- Principais causas de falha (top 5 gaps recorrentes)

---

## 9) Modelo de relatório do teste (resumo executivo)

**Serviço/Processo:** ____  
**Tipo de teste:** ____  
**Data:** ____  
**Resultado:** (Aprovado / Aprovado com ressalvas / Reprovado)

- **RTO definido:** ____ | **RTO real:** ____  
- **RPO definido:** ____ | **RPO real:** ____  
- **Principais gaps:**  
  1) ____  
  2) ____  
- **Plano de ação (top 3):**  
  1) ____ (owner: __, prazo: __)  
  2) ____  
  3) ____  

---

## 10) Governança e responsabilidades

- **Owner do plano de testes:** GRC/Resiliência
- **Responsáveis por execução técnica:** Infra/SRE/Plataforma/DBA (conforme serviço)
- **Validação de negócio:** Business Owner
- **Aprovação de mudanças de alto impacto:** liderança definida

---

