# Bloco 5 — Auditoria 360° (GATE)

> **Este bloco é um GATE obrigatório.**
> Se houver ≥ 1 ❗ ou qualquer desvio de Gravidade Alta → **reabrir Bloco 3 ou 4 para correção**.
> Somente prosseguir para o Bloco 6 com aprovação total.

---

## Missão

Revisar cada número dos Blocos 3 e 4 confirmando:
- Coerência aritmética (fórmulas fecham)
- Integração Segmento ↔ Consolidado
- Conformidade com o Cenário Base (sem otimismo oculto)

---

## 1. Teste de Coerência & Integração Total

### a) Cadeia Receita → NOPAT → FCFF

- Recalcular `NOPAT = Receita × Margem NOPAT` para cada ano e segmento
- Recalcular `FCFF = NOPAT + D&A – CAPEX_total – ΔWC_total`
- Alerta ❗ se Delta > ±R$ 1 mi em qualquer ano

### b) Segmento ↔ Consolidado

- Receita, NOPAT, CAPEX, FCFF, ROIC: `Σ segmentos = consolidado`
- Spread ROIC–WACC consolidado = média ponderada dos spreads segmentados
- Marcar 🟠 se diferença > 0,1 pp ou R$ 1 mi

### c) Cash-Flow Loop: FCFF → D/EBITDA → Beta → WACC

- `Amortização dívida = Cash-Sweep – Dividendos`
- `βl = βu × (1 + (1 − Cash Tax Rate) × D/EBITDA_ano)`
- Se WACC variar fora do esperado (> ±10 bps por fator não modelado) → ❗

### d) CAPEX Integridade (Red Queen)

- `CAPEX_total = CAPEX_exp + CAPEX_man` em TODOS os anos e segmentos
- `Asset Age = PP&E líq / PP&E bruto < 0,4` → 🟠 sub-investimento

**Tabela de alertas (incluir APENAS Gravidade Média 🟠 ou Alta ❗):**

| Variável | Valor Modelo | Valor Recalculado | Δ | Gravidade |
|----------|-------------|-----------------|---|-----------|
| | | | | |

*Opinião Analítica 3×3 — Driver → Impacto quantificado → Ação + KPI + Confiança*

---

## 2. Desvios Ocultos do Cenário Base

*Gravidade: Baixa ≤ 1 pp · Média 1–2 pp · Alta > 2 pp*

Verificar se alguma premissa escorregou para otimismo sem justificativa:
- Receita crescendo > Guidance ajustado (com haircut) + 2 pp
- Margem NOPAT > EBITDA em qualquer ano
- g > IPCA + 1% sem revisão de Ke (Penman Rule)
- Demanda baixa com ARPU/preço subindo

**Tabela (apenas Média 🟠 ou Alta ❗):**

| Premissa | Valor Usado | Limite Cenário Base | Δ | Gravidade |
|----------|------------|-------------------|---|-----------|
| | | | | |

*Opinião Analítica 3×3*

---

## 3. Stress-Checks Relâmpago

| Stress | Δ FCFF / Valor Terminal | Gravidade |
|--------|------------------------|-----------|
| +50 bps WACC | Δ Valor Terminal: ____% | |
| −5% Receita/ARPU principal segmento | Δ FCFF ano 5: ____% | |
| +2 pp CAPEX_man (% receita) | Δ Spread ROIC–WACC Terminal: ____ pp | |
| +100 bps CRP (risco-país) | Δ WACC: ____ · Δ VT: ____% | |

*Opinião Analítica 3×3*

---

## 4. Diagnóstico Estratégico

- Robustez da alocação de capital (buyback × dividendo × reinvestimento)
- Fade ROIC adere à experiência de pares maduros do setor? (ver `references/base-rates.md`)
- 2 KPIs críticos a monitorar + nível de confiança (Alta / Média / Baixa)

*Opinião Analítica 3×3*

---

## 5. Veredito GATE

| Critério | Status |
|----------|--------|
| Nenhum ❗ pendente | ✅/❗ |
| Nenhum desvio de Gravidade Alta | ✅/🟠 |
| Cadeia aritmética fecha | ✅/❗ |
| Segmento ↔ Consolidado alinhados | ✅/❗ |
| Cenário Base confirmado (sem otimismo oculto) | ✅/🟠 |

**Se GATE = ✅ APROVADO → prosseguir para Bloco 6**
**Se GATE = ❗ REPROVADO → reabrir Bloco [3/4] para correção do item indicado**
