# Tracker de Achados & CAPA — Template (Auditoria ISO 27001)

Este tracker padroniza o registro e acompanhamento de:
- **NC** (Não Conformidades)
- **Observações**
- **OM** (Oportunidades de Melhoria)
- **CAPA** (Ações corretivas e preventivas)

> Objetivo: garantir rastreabilidade ponta a ponta (achado → causa raiz → ação → evidência → verificação de efetividade).

---

## 1) Como usar (processo simples)

1. Registrar achados durante a auditoria (NC/Observação/OM)
2. Para **NC**, sempre:
   - definir **correção imediata** (se aplicável)
   - fazer **análise de causa raiz**
   - criar **CAPA** com owner e prazo
3. Coletar evidência de implementação
4. Verificar efetividade (o problema não volta?) e encerrar

---

## 2) Status padrão (sugestão)

- **Aberto** → registrado, sem ação definida
- **Em análise** → causa raiz / plano em definição
- **Em andamento** → CAPA em execução
- **Bloqueado** → impedimento externo
- **Aguardando evidência** → executado, faltando prova
- **Aguardando verificação** → evidência recebida, faltando checar efetividade
- **Encerrado** → efetividade verificada e aprovado

---

## 3) Tabela principal (copiar para planilha ou manter em Markdown)

> Dica: para operação real, uma planilha facilita filtros e prazos.
> Campos essenciais: ID, tipo, requisito/controle, owner, prazo, status e evidência.

| ID | Tipo (NC/Obs/OM) | Requisito/Controle | Descrição do achado (fato) | Evidência (link) | Risco/Impacto | Severidade | Owner do achado | Ação imediata (se houver) | Causa raiz | CAPA (ação corretiva/preventiva) | Owner CAPA | Prazo alvo | Status | Evidência de implementação (link) | Verificação de efetividade | Data de verificação | Aprovador | Data de encerramento | Observações |
|---|---|---|---|---|---|---|---|---|---|---|---|---:|---|---|---|---:|---|---:|---|
| AUD-0001 |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |

---

## 4) Guia para preencher campos críticos

### 4.1 “Descrição do achado (fato)”
- Escreva com base em evidência objetiva (o que foi observado).
- Evite opinião. Use: “Foi verificado que…”.

### 4.2 “Risco/Impacto”
- Relacione a consequência (C/I/A, compliance, financeiro, reputação).
- Se aplicável, linkar risco no Risk Register.

### 4.3 “Ação imediata”
- Correção rápida para reduzir exposição (ex.: revogar acesso, atualizar configuração).
- Não substitui CAPA (causa raiz).

### 4.4 “Causa raiz”
Sugestões de técnicas:
- 5 Porquês
- Ishikawa (espinha de peixe)
- Falha de processo x falha técnica x falha de governança

### 4.5 “CAPA”
Deve ser:
- específica (o que fazer)
- mensurável (como comprovar)
- com owner e prazo
- com critério de efetividade (como saber que resolveu de verdade)

---

## 5) Verificação de efetividade (mínimo)

Marcar como “encerrado” apenas quando:
- [ ] ação foi implementada (evidência objetiva)
- [ ] o controle está operando (amostra/execução)
- [ ] não há recorrência (por um período razoável ou novo teste)
- [ ] documentação/treinamento foi atualizado quando necessário

Exemplos de verificação:
- reauditoria por amostragem
- execução de teste (restore drill, VM scan, revisão de logs)
- revisão de tickets e evidências do período

---

## 6) Conexões recomendadas

- **Risk Register:** se o achado representar risco relevante, registrar/atualizar risco.
- **Métricas:** usar KPIs como “% CAPAs no prazo” e “tempo médio para fechar NC”.
- **Evidence Pack:** armazenar evidências de implementação e verificação.

---
