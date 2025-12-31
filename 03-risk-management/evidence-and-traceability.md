# Evidências e Rastreabilidade (Audit Trail) — Gestão de Riscos

Este documento padroniza como manter **rastreabilidade** na gestão de riscos, garantindo que auditoria e liderança consigam verificar:
- o que foi avaliado
- o que foi decidido (e por quem)
- o que foi executado
- como validar que o risco reduziu

---

## 1) Princípios

- “Risco no Excel” não reduz risco: risco precisa de **ação** e **evidência**.
- Toda decisão relevante deve ter:
  - data, owner, aprovador (quando aplicável)
  - justificativa e trade-offs
  - link para ticket/change/evidência

---

## 2) Evidências típicas (exemplos)

- **Tratamento/mitigação**
  - ticket de remediação (com owner e prazo)
  - change request (janela e aprovação)
  - evidência de implementação (print sanitizado, config, log)
- **Validação**
  - re-scan (VM), evidência de hardening, log de evento esperado
  - resultados de testes (quando aplicável)
- **Decisões**
  - formulário de aceite (com expiração)
  - exceção temporária (com compensações)
  - atas/decision log de steering (quando aplicável)

---

## 3) O que deve existir para cada risco (checklist mínimo)

Para cada `RISK-XXX`, ter link para:
- [ ] registro no risk register
- [ ] ticket principal do plano (treatment)
- [ ] evidência de validação (quando tratado)
- [ ] aceite/exceção (se aplicável) **com expiração**
- [ ] revisão periódica registrada (data + resultado)

---

## 4) Modelo de “pacote” por risco (simples)

> Pode ser uma seção dentro do próprio Risk Register ou um doc por risco (se preferir).

- **Risco:** RISK-___ — ______________________
- **Owner:** ______________________
- **Status:** Aberto / Em andamento / Concluído / Aceito
- **Plano (ticket):** ______________________
- **Evidência de implementação:** ______________________
- **Evidência de validação:** ______________________
- **Aceite/Exceção (se houver):** ______________________
- **Última revisão:** ____/____/____ (resultado: ________)

---

## 5) Regras de retenção (sugestão)

- Riscos críticos/altos: manter evidências por período compatível com auditoria/contrato
- Exceções e aceites: manter histórico (com expirações e renovações)
- Evitar armazenar PII ou detalhes sensíveis em repositórios públicos

---
