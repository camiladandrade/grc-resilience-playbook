# BCP — Business Continuity Plan (Template)
**Plano de Continuidade de Negócios — Processo/Serviço**

Este documento descreve como manter (ou recuperar parcialmente) a operação do **processo/serviço** em caso de interrupção, com foco em **modo degradado**, comunicação e coordenação.

> Baseado no BIA: `bia-template.md`  
> Diretrizes de RTO/RPO: `rto-rpo-guidelines.md`

---

## 1) Identificação e Metadados

- **Processo/Serviço:** _______________________________
- **Área/Unidade:** ___________________________________
- **Business Owner (Dono do Processo):** _______________
- **IT Owner (Dono Técnico):** _________________________
- **GRC/Resiliência (Responsável):** ___________________
- **Versão:** _______
- **Data:** ____/____/____
- **Periodicidade de revisão:** (trimestral/semestral) _______
- **Links relacionados:**
  - BIA: `./bia-template.md` (ou link interno do repo)
  - Risk Register (risco relacionado, se houver): `../03-risk-management/risk-register-template.md`

---

## 2) Objetivo, Escopo e Premissas

### 2.1 Objetivo do BCP
Descrever procedimentos para:
- manter operação mínima do processo/serviço durante interrupção
- reduzir impacto operacional/financeiro/compliance
- orientar comunicação e tomada de decisão
- suportar retorno controlado (“volta ao normal”)

### 2.2 Escopo (inclui)
- Sistemas/atividades incluídas: ______________________________________
- Sites/locais incluídos: _____________________________________________

### 2.3 Fora do escopo
- ______________________________________

### 2.4 Premissas e dependências críticas
- Dependências “não negociáveis”: _____________________________________
- Restrições (time, janela, fornecedor, etc.): __________________________

---

## 3) Criticidade e Objetivos (do BIA)

> Preencha com base no BIA aprovado.

- **Criticidade (Tier):** Tier-0 / Tier-1 / Tier-2
- **MTPD:** ____ horas/dias
- **RTO:** ____ horas
- **RPO:** ____ minutos/horas

**Resumo do impacto (alto nível):**
- Operacional: ______________________________________
- Financeiro: _______________________________________
- Legal/Compliance (ex.: LGPD): ______________________
- Reputacional: _____________________________________

---

## 4) Critérios de Ativação e Desativação do Plano

### 4.1 Gatilhos para ativar o BCP
Ativar este plano quando ocorrer (um ou mais):
- [ ] indisponibilidade do serviço/processo acima de ____ minutos
- [ ] falha de fornecedor crítico / integração essencial
- [ ] indisponibilidade de site/ambiente (data center/cloud/filial)
- [ ] incidente de segurança afetando disponibilidade/integridade
- [ ] perda de equipe-chave (capacidade operacional reduzida)
- [ ] decisão executiva (por risco/compliance)

**Quem pode ativar:**
- [ ] Business Owner
- [ ] IT Owner
- [ ] Líder de Continuidade/Resiliência
- [ ] Patrocinador Executivo

### 4.2 Gatilhos para desativar o BCP (“volta ao normal”)
Desativar quando:
- serviço/processo operando em modo normal por ____ horas sem falhas
- backlog controlado / operação estabilizada
- comunicação de encerramento enviada para stakeholders

---

## 5) Papéis e Responsabilidades (BCP)

> Ajuste conforme estrutura. Em incidentes, alinhar com IR quando aplicável.

| Papel | Responsabilidades | Contato |
|---|---|---|
| Business Owner | priorização do negócio, validação de continuidade | ____ |
| IT Owner | recuperação técnica, coordenação TI | ____ |
| Líder BCP | coordenação do plano, comunicação e checkpoints | ____ |
| Operações/TI | execução de procedimentos, acessos, suporte | ____ |
| Comunicação | mensagens internas/externas (se aplicável) | ____ |
| Jurídico/Privacidade | orientação legal/regulatória (se aplicável) | ____ |
| Fornecedor | suporte/escalação (se aplicável) | ____ |

---

## 6) Dependências (Checklist rápido)

### 6.1 Pessoas
- Funções essenciais para operar em modo degradado:
  - ______________________
  - ______________________

### 6.2 Tecnologia (mínimo para operar)
Liste o “mínimo viável” para continuidade:

| Dependência | Tipo | Obrigatória para “modo degradado”? | Observação |
|---|---|---|---|
|  | Aplicação/Infra/Identidade/Dados | Sim/Não |  |

### 6.3 Fornecedores/terceiros
- Fornecedor crítico: ______________________  SLA/Contato: ______________________

---

## 7) Estratégia de Continuidade (Modo Degradado)

> Descreva como operar com capacidade reduzida.

### 7.1 Estratégia escolhida (marcar)
- [ ] Operação manual / workaround
- [ ] Uso de sistema alternativo
- [ ] Redirecionamento de fluxo (ex.: canal alternativo)
- [ ] Priorização de subset de serviços (“somente essencial”)
- [ ] Operação parcial (capacidade reduzida)

### 7.2 Regras de priorização do negócio
Defina “o que continua” primeiro:
1. ______________________________________
2. ______________________________________
3. ______________________________________

### 7.3 Limitações do modo degradado
- volume máximo suportado: ______________________
- atividades suspensas: __________________________
- riscos assumidos temporariamente: _______________

---

## 8) Procedimentos Operacionais (Runbook de Continuidade)

> Checklist prático para executar.

### 8.1 Primeiros 30 minutos
- [ ] Confirmar gatilho e ativar BCP (registrar horário)
- [ ] Abrir canal de coordenação (chat/call) e registrar participantes
- [ ] Comunicar stakeholders iniciais (ver seção 9)
- [ ] Confirmar impacto e escopo (o que parou? quando? por quê?)
- [ ] Acionar TI/fornecedor (se aplicável)
- [ ] Definir prioridade (o que manter primeiro)

### 8.2 Execução do modo degradado (passo a passo)
Descrever passos objetivos (sem detalhes sensíveis), por exemplo:
1. ______________________________________
2. ______________________________________
3. ______________________________________

### 8.3 Controles de segurança mínimos no modo degradado
- [ ] manter controle de acesso (sem compartilhamento de credenciais)
- [ ] registrar decisões e aprovações
- [ ] proteger dados sensíveis (PII/confidencial)
- [ ] manter trilha de auditoria (logs/planilhas de controle)

---

## 9) Plano de Comunicação

### 9.1 Stakeholders e canais
| Público | Objetivo | Canal | Responsável |
|---|---|---|---|
| Liderança | decisão e visibilidade | e-mail/meet/chat | ____ |
| Usuários internos | instruções claras | e-mail/intranet/chat | ____ |
| Clientes (se aplicável) | transparência controlada | e-mail/site | ____ |
| Fornecedores | suporte e escalonamento | portal/e-mail | ____ |
| Jurídico/Privacidade | obrigações | call/e-mail | ____ |

### 9.2 Cadência de updates (sugestão)
- Atualização tática: a cada ____ horas
- Atualização executiva: a cada ____ horas
- Atualização para usuários: por marcos (ativação, workaround, retorno)

### 9.3 Mensagens prontas (modelos curtos)
**Mensagem interna (ativação do BCP):**  
> Estamos enfrentando indisponibilidade no serviço/processo ____ desde __:__.  
> Ativamos o Plano de Continuidade e operaremos em modo degradado.  
> Próxima atualização às __:__. Contato: ____.

**Mensagem interna (workaround):**  
> Enquanto o serviço ____ estiver indisponível, siga o procedimento alternativo: ____.

**Mensagem de encerramento (retorno ao normal):**  
> O serviço/processo ____ foi normalizado às __:__. Obrigado pela colaboração.  
> Próximos passos: análise pós-evento e melhorias.

---

## 10) Registro e Evidências (governança)

Durante a ativação do BCP, registrar:
- horário de ativação/desativação
- impacto e escopo
- decisões e justificativas
- ações executadas (com owner)
- evidências e links (tickets, prints, relatórios)

> Recomenda-se manter um “Log do Evento” (planilha/arquivo) para auditoria.

---

## 11) Retorno ao Normal (Plano de Transição)

### 11.1 Critérios para iniciar transição
- [ ] serviço/infra estabilizado
- [ ] validação do Business Owner (processo ok)
- [ ] backlog controlado
- [ ] riscos temporários mitigados

### 11.2 Passos de transição
1. ______________________________________
2. ______________________________________
3. ______________________________________

### 11.3 Validação pós-retorno
- [ ] validar dados/processos críticos
- [ ] monitorar por ____ horas/dias
- [ ] confirmar com stakeholders que operação normal voltou

---

## 12) Testes, Manutenção e Melhorias

### 12.1 Tipos de teste recomendados
- [ ] Tabletop (simulação de decisão e fluxo)
- [ ] Exercício operacional (execução do workaround)
- [ ] Teste de restauração (conectado ao DRP, quando aplicável)

### 12.2 Frequência sugerida
- Tier-0: semestral (mínimo)
- Tier-1: anual (mínimo)
- Tier-2: conforme necessidade

### 12.3 Melhorias e lições aprendidas
Registrar:
- o que funcionou
- o que falhou
- ações corretivas (owner + prazo)

---

## 13) Aprovações

- **Business Owner:** ______________________  Data: ____/____/____  
- **IT Owner:** ____________________________  Data: ____/____/____  
- **GRC/Resiliência:** ______________________  Data: ____/____/____  

---
