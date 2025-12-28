# DRP — Disaster Recovery Plan (Template)
**Plano de Recuperação de Desastres — Técnico (TI)**

Este documento descreve como recuperar tecnicamente sistemas e serviços após um desastre/interrupção, alinhado aos objetivos de continuidade (**RTO/RPO**) definidos no BIA.

> Baseado em:
- `bia-template.md`
- `rto-rpo-guidelines.md`
- BCP do processo/serviço: `bcp-template.md`

---

## 1) Identificação e Metadados

- **Serviço/Sistema:** _______________________________
- **Ambiente:** (Produção/Homologação/Dev) ____________
- **Criticidade (Tier):** Tier-0 / Tier-1 / Tier-2
- **IT Owner:** ______________________________________
- **Equipe responsável (Infra/SRE/Plataforma):** _______
- **Versão:** _______
- **Data:** ____/____/____
- **Periodicidade de revisão:** (trimestral/semestral) _______

**Links relacionados:**
- BIA: ______________________
- BCP: ______________________
- Documentação técnica (runbooks): ______________________
- Inventário/CMDB: ______________________

---

## 2) Objetivo, Escopo e Premissas

### 2.1 Objetivo do DRP
- Recuperar serviços/sistemas em ordem correta e dentro do RTO/RPO.
- Reduzir risco de reinfecção/recorrência (quando a causa for incidente).
- Garantir rastreabilidade, validação e retorno seguro.

### 2.2 Escopo
- Inclui: ______________________________________
- Exclui: ______________________________________

### 2.3 Premissas
- Acesso a backups/replicação disponível: (Sim/Não) ___
- Time e suporte necessários: ________________________
- Dependências externas (fornecedor/cloud): ____________

---

## 3) Objetivos de Recuperação (RTO/RPO)

> Preencher conforme BIA aprovado.

- **MTPD:** ____ horas/dias
- **RTO:** ____ horas
- **RPO:** ____ minutos/horas

**Observações importantes:**
- RTO/RPO por componentes (se aplicável): ______________________
- Janela de maior criticidade: _________________________________

---

## 4) Cenários de desastre (quando usar este plano)

Marque os cenários relevantes:
- [ ] Indisponibilidade de região/zona/cloud
- [ ] Falha grave de storage/backup primário
- [ ] Corrupção de dados (sem malware)
- [ ] Ransomware/incidente afetando disponibilidade/integridade
- [ ] Falha de rede crítica (core, VPN, DNS)
- [ ] Perda de data center/local físico
- [ ] Erro humano com impacto amplo (misconfig/rollback falho)

---

## 5) Contatos e acessos (mínimo)

### 5.1 Contatos essenciais
| Função | Nome/Time | Contato | Backup |
|---|---|---|---|
| IT Owner |  |  |  |
| Infra/SRE |  |  |  |
| DBA |  |  |  |
| Redes |  |  |  |
| Segurança (IR) |  |  |  |
| Fornecedor/Cloud |  |  |  |

### 5.2 Acessos necessários (checklist)
- [ ] Console cloud / portal do provedor
- [ ] Ferramenta de backup/restore
- [ ] DNS e certificados (se aplicável)
- [ ] Painéis de monitoramento
- [ ] CMDB/inventário
- [ ] Credenciais break-glass (com governança)

---

## 6) Dependências e ordem de recuperação

> Regra: restaurar primeiro os componentes que habilitam outros (identidade, rede, DNS, dados).

### 6.1 Dependências críticas (mapa)
| Componente | Depende de | Observação |
|---|---|---|
| Identidade (IdP/AD) | DNS, Rede | autenticação |
| Banco de dados | Storage, Rede | dados transacionais |
| Aplicação | DB, IdP | serviço final |

### 6.2 Ordem de recuperação (prioridade)
1. ______________________________________
2. ______________________________________
3. ______________________________________
4. ______________________________________
5. ______________________________________

---

## 7) Estratégia de recuperação (escolher)

Marque a estratégia aplicada:
- [ ] **Restore de backup** (ponto no tempo)
- [ ] **Failover** para ambiente secundário (warm/hot)
- [ ] **Rebuild/Infra como código** + restore de dados
- [ ] **Workaround temporário** (com BCP)
- [ ] **Híbrida** (failover + restore parcial)

**Detalhes da estratégia:**
- Local de recovery (região/zona/site): ______________________
- Fonte de dados (backup/replicação): ________________________
- Ponto de restauração (RPO): ________________________________

---

## 8) Pré-validações (antes de recuperar)

### 8.1 Checklist técnico
- [ ] Escopo do impacto confirmado (quais sistemas)
- [ ] Backups disponíveis e íntegros (último “bom” identificado)
- [ ] Capacidade do ambiente de recovery (compute/storage/rede)
- [ ] DNS/certificados/segredos disponíveis
- [ ] Monitoramento pronto para acompanhar recuperação

### 8.2 Se a causa for incidente de segurança (ex.: ransomware)
- [ ] Confirmar contenção (IR) antes de restaurar
- [ ] Evitar reinfecção (credenciais, IOCs, persistência)
- [ ] Reset de credenciais críticas e validação de identidades
- [ ] Revisar integrações e acessos de terceiros

---

## 9) Procedimento de recuperação (runbook)

> Descreva passos objetivos e seguros. Evite informações sensíveis (segredos/chaves). Use links para runbooks internos quando necessário.

### 9.1 Passos por componente (modelo)
#### Componente: ______________________
- Objetivo: ______________________
- Fonte do restore/failover: ______________________
- Passos:
  1. ______________________________________
  2. ______________________________________
  3. ______________________________________
- Validação:
  - [ ] serviço responde
  - [ ] logs sem erros críticos
  - [ ] dados consistentes (se aplicável)
- Evidência:
  - link/print/log: ______________________

> Repita o bloco para cada componente crítico.

---

## 10) Validação pós-recuperação (obrigatória)

### 10.1 Validação técnica
- [ ] Health checks e monitoramento ok
- [ ] Autenticação/identidade ok (se aplicável)
- [ ] Conectividade com dependências ok
- [ ] Integridade de dados validada (DB/app)
- [ ] Performance em nível aceitável

### 10.2 Validação de negócio
- [ ] Dono do serviço validou fluxos essenciais
- [ ] Operação em modo normal (ou degradado) confirmada
- [ ] Comunicação de status realizada (via BCP)

### 10.3 Critério de “liberação” (all clear)
- Sem erros críticos por ____ horas
- Sem alertas anormais persistentes
- Backups retomados e verificados

---

## 11) Comunicação e checkpoints

- Checkpoint técnico: a cada ____ minutos durante recovery
- Atualização para liderança: a cada ____ horas (ou por marcos)
- Atualização para usuários: por marcos (restauração parcial/total)

> Recomenda-se usar um “Log do Evento” para timeline e decisões.

---

## 12) Pós-evento: evidências, lições e melhorias

Registrar:
- linha do tempo de recovery
- tempo real de recuperação vs RTO (atingiu? por quê?)
- perda real de dados vs RPO (atingiu? por quê?)
- falhas e gargalos (acesso, backup, dependências)
- ações corretivas (owner + prazo)

Recomendação:
- abrir/atualizar riscos no Risk Register (se houver gaps relevantes)
- atualizar BCP/DRP e plano de testes

---

## 13) Aprovações

- **IT Owner:** ____________________________  Data: ____/____/____  
- **Infra/SRE:** ___________________________  Data: ____/____/____  
- **Business Owner (ciente):** ______________  Data: ____/____/____  
- **GRC/Resiliência:** ______________________  Data: ____/____/____  

---
