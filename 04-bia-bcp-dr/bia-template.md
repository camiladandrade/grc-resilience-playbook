# BIA — Business Impact Analysis (Template)

Template de **Análise de Impacto no Negócio (BIA)** para apoiar Resiliência (BCP/DR), definindo criticidade, dependências e objetivos de continuidade (RTO/RPO).

> Objetivo: identificar processos e serviços críticos, impactos por tempo de indisponibilidade e requisitos para continuidade.

---

## 1) Identificação

- **Área / Unidade:** ______________________
- **Processo / Serviço:** ______________________
- **Dono do Processo (Business Owner):** ______________________
- **Dono Técnico / TI (IT Owner):** ______________________
- **Analista (GRC/Resiliência):** ______________________
- **Data:** ____/____/____
- **Versão:** ______
- **Escopo (o que está incluído):** ______________________
- **Fora de escopo (o que não está incluído):** ______________________

---

## 2) Descrição do processo/serviço

- **Objetivo do processo/serviço:** ______________________________________
- **Entradas principais:** _______________________________________________
- **Saídas / entregáveis:** ______________________________________________
- **Clientes/usuários impactados:** ______________________________________
- **Canais de operação:** (sistemas, e-mail, call center, etc.) ______________________
- **Período de maior criticidade:** (horário comercial, 24x7, sazonalidade) ____________

---

## 3) Dependências (mapa mínimo)

### 3.1 Pessoas e times
- **Times essenciais:** _________________________________________________
- **Competências chave / funções críticas:** ______________________________
- **Fornecedores/terceiros essenciais:** _________________________________

### 3.2 Tecnologia (aplicações e infraestrutura)
Liste sistemas e componentes essenciais para operar o processo:

| Dependência | Tipo | Criticidade | Observação |
|---|---|---|---|
| Ex.: ERP | Aplicação | Alta | faturamento |
| Ex.: AD/IdP | Identidade | Alta | autenticação |
| Ex.: Banco de dados | Infra | Alta | dados transacionais |

### 3.3 Dados
- **Principais bases/datasets usados:** _________________________________
- **Classificação dos dados:** (Público/Interno/Confidencial/Sensível/PII) ________
- **Requisitos de retenção/regulatório (se houver):** ______________________

### 3.4 Integrações e dependências externas
- **APIs/Integrações críticas:** _________________________________________
- **Provedores (cloud, pagamento, e-mail, etc.):** _________________________

---

## 4) Impacto por tempo de indisponibilidade

> Preencha o impacto crescente à medida que o tempo de indisponibilidade aumenta.

Marque o nível (Baixo/Médio/Alto/Crítico) e descreva.

| Tempo de indisponibilidade | Operacional | Financeiro | Legal/Compliance | Reputacional | Comentários |
|---|---|---|---|---|---|
| 0–2h |  |  |  |  |  |
| 2–8h |  |  |  |  |  |
| 8–24h |  |  |  |  |  |
| 1–3 dias |  |  |  |  |  |
| 3–7 dias |  |  |  |  |  |

---

## 5) MTPD, RTO e RPO

### 5.1 Definições (para alinhamento)
- **MTPD:** tempo máximo tolerável de interrupção (limite do negócio)
- **RTO:** tempo alvo para restaurar o serviço
- **RPO:** ponto máximo de perda aceitável de dados

### 5.2 Valores definidos
- **MTPD:** ____ horas/dias
- **RTO:** ____ horas
- **RPO:** ____ minutos/horas

**Justificativa (por quê estes valores):**  
____________________________________________________________

---

## 6) Controles atuais e capacidade de recuperação

### 6.1 Controles e resiliência existentes
- Backups: (tipo, frequência, retenção, imutabilidade) ______________________
- DR: (site alternativo, replicação, warm/hot/cold) _________________________
- Monitoramento/alertas: ________________________________________________
- Procedimentos de restore/testes: ________________________________________

### 6.2 Riscos e pontos fracos (gaps)
- Principais gargalos (pessoas, tecnologia, fornecedor): ___________________
- SPOFs (pontos únicos de falha): _______________________________________
- Dependências sem alternativa: _________________________________________

---

## 7) Estratégia de continuidade (alto nível)

- Estratégia recomendada: (manual workaround / failover / restore / alternativo) ________
- Workarounds possíveis (processo manual): _______________________________
- Comunicação em interrupções: __________________________________________
- Requisitos mínimos para operar “modo degradado”: _______________________

---

## 8) Priorização e classificação final

- **Criticidade do processo/serviço:** (Tier-0 / Tier-1 / Tier-2) ________
- **Justificativa da criticidade:** ______________________________________
- **Prioridade de recuperação:** (1, 2, 3...) ________

---

## 9) Aprovações

- **Business Owner:** ______________________  Data: ____/____/____  
- **IT Owner:** ____________________________  Data: ____/____/____  
- **GRC/Resiliência:** ______________________  Data: ____/____/____  

---

## 10) Saídas do BIA (para próximos documentos)

Após concluir este BIA, gerar/atualizar:
- BCP do processo/serviço (plano de continuidade)
- DRP técnico (plano de recuperação)
- Plano de testes (tabletop + restore drills)
- Roteiro de comunicação em crise
- Atualização de riscos (Risk Register)

---
