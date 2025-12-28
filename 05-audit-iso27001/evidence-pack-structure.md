# Estrutura do Pacote de Evidências — ISO 27001 (Evidence Pack)

Este documento padroniza como organizar e armazenar evidências do SGSI para **auditoria interna/externa**, garantindo rastreabilidade, consistência e facilidade de verificação.

> Objetivo: reduzir esforço de auditoria, evitar “caça a evidências” e aumentar qualidade do SGSI.

---

## 1) Princípios de organização

- **Uma evidência = um link/arquivo rastreável**
- Evidências devem ter: **data**, **owner**, **contexto** e **versão** (quando aplicável)
- Evitar arquivos soltos: usar estrutura por **área/processo** e/ou por **controle**
- Manter trilha de auditoria: quem gerou, quando, e como validar

---

## 2) Convenção de nomes (padrão)

Sugestão de padrão:
`AAAA-MM-DD_[Area]_[Tipo]_[DescricaoCurta]_vX`

Exemplos:
- `2026-01-10_GRC_Politica_PoliticaSegInfo_v1.pdf`
- `2026-02-03_VM_Relatorio_ScanMensal_v2.xlsx`
- `2026-02-15_IR_PIR_IncidenteIR-004_v1.docx`
- `2026-03-01_BCP_Teste_RestoreDrillServicoX_v1.pdf`

> Se a empresa já tiver padrão, adote o padrão corporativo.

---

## 3) Estrutura recomendada de pastas (modelo)

> Use esta estrutura em um drive corporativo (SharePoint/Drive/Confluence/Repo interno).
> Para este repositório público, mantenha apenas a estrutura e exemplos fictícios.

```text
Pacote-de-Evidencias/
├─ 00-Administrativo/
│  ├─ Plano-de-Auditoria/
│  ├─ Relatorio-de-Auditoria/
│  ├─ Achados-e-CAPAs/                  # NC/OM e ações corretivas (CAPA)
│  └─ Indice-de-Evidencias.xlsx         # índice mestre (opcional, recomendado)
│
├─ 01-Contexto-e-Escopo/
│  ├─ Escopo-do-SGSI/
│  ├─ Partes-Interessadas/
│  ├─ Criterios-de-Risco/
│  └─ Visao-Geral-do-Inventario-de-Ativos/
│
├─ 02-Lideranca-e-Governanca/
│  ├─ Politica-do-SGSI/
│  ├─ Papeis-e-Responsabilidades/
│  ├─ Analise-Critica-da-Direcao/       # Management Review
│  └─ Objetivos-de-Seguranca-e-OKRs/
│
├─ 03-Gestao-de-Riscos/
│  ├─ Metodologia-de-Riscos/
│  ├─ Registro-de-Riscos/
│  └─ Planos-de-Tratamento-de-Riscos/
│
├─ 04-SoA-e-Controles/
│  ├─ Declaracao-de-Aplicabilidade/     # SoA
│  └─ Evidencias-de-Controles/
│     ├─ A.5-Organizacionais/
│     ├─ A.6-Pessoas/
│     ├─ A.7-Fisicos/
│     └─ A.8-Tecnologicos/
│
├─ 05-Operacoes/
│  ├─ Gestao-de-Vulnerabilidades/
│  ├─ Logs-e-Monitoramento/
│  ├─ Gestao-de-Mudancas/
│  ├─ Backup-e-Restauracao/
│  └─ Gestao-de-Fornecedores/
│
├─ 06-Gestao-de-Incidentes/
│  ├─ Politica-de-Incidentes/
│  ├─ Registro-de-Incidentes/
│  ├─ Relatorios-de-Incidentes-e-PIRs/
│  └─ Exercicios/
│
├─ 07-Resiliencia/
│  ├─ BIA/
│  ├─ BCP/
│  ├─ DRP/
│  └─ Testes-e-Resultados/
│
└─ 08-Conformidade-e-Privacidade/
   ├─ Legal-e-Contratual/
   ├─ LGPD/
   └─ Treinamentos-e-Conscientizacao/
```
---


## 4) Índice mestre de evidências (recomendado)

Manter um arquivo `Evidence-Index.xlsx` (ou planilha) com:

| ID | Controle/Requisito | Evidência | Local/Link | Data | Owner | Status | Observação |
|---|---|---|---|---|---|---|---|
| EV-0001 | ISO 27001 5.2 | Política SGSI v1 | link | 2026-01-10 | GRC | OK |  |
| EV-0002 | Anexo A - Logging | Padrão de logs | link | 2026-02-01 | TI | OK |  |

> Ajuda muito em auditorias externas.

---

## 5) Evidências por “tipo” (o que normalmente é aceito)

### 5.1 Evidência documental (políticas e normas)
- política aprovada (com versão e data)
- padrão/procedimento publicado
- registro de comunicação (quando aplicável)

### 5.2 Evidência operacional (prova de execução)
- tickets (mudanças, incidentes, riscos)
- relatórios (scans, auditorias, backups)
- logs e prints (sanitizados)
- atas de reuniões (ex.: análise crítica do SGSI)

### 5.3 Evidência de efetividade
- KPIs (tendências e metas)
- resultados de testes (restore drills, tabletop)
- melhoria contínua (CAPAs encerradas com evidência)

---

## 6) Regras de qualidade (para evitar reprovação em auditoria)

- Evidência deve ser **contemporânea** ao período auditado
- Deve ser possível validar **quem**, **quando** e **o quê**
- Evitar prints sem contexto: incluir “o que é, por que prova, data”
- Para controles recorrentes, guardar amostras **mensais/trimestrais** (conforme cadência)
- Evidências sensíveis devem ser **sanitizadas** (sem credenciais/PII)

---

## 7) Como mapear evidência para ISO 27001 (dica prática)

Dois jeitos simples:
1) **Por controle (Anexo A)** → pasta por A.5/A.6/A.7/A.8  
2) **Por processo** (VM, IR, Backup, Supplier, etc.) e mapear na planilha índice

> Melhor prática: usar os dois — evidência por processo e índice com mapeamento para controles.

---

## 8) Checklist final (antes da auditoria)

- [ ] Plano de auditoria e agenda aprovados
- [ ] SoA atualizado e consistente com escopo e riscos
- [ ] Risk Register revisado (com owners e tratamento)
- [ ] Evidências organizadas por período e controle/processo
- [ ] Índice mestre atualizado (links funcionando)
- [ ] Amostras prontas para controles recorrentes (backup, VM, logs, IR)
- [ ] Evidências sanitizadas (sem dados sensíveis)

---
