# Stress Test & Validação Cruzada

> Equivalente à Fase 7 do DCF Pipeline v3. Executar após o modelo base estar aprovado.

---

## 1. Via Negativa — Condições de Invalidação

Liste explicitamente o que **tornaria a tese errada** em cada horizonte:

### Curto Prazo (0–12 meses)
- [ ] O que invalidaria a tese em 12 meses?
- Ex.: deterioração de margem > 3 pp, guidance rebaixado, perda de contrato chave

### Médio Prazo (1–3 anos)
- [ ] O que invalidaria a tese em 1–3 anos?
- Ex.: novo entrante competitivo, capex 40% acima do orçado, alavancagem > 4,5× EBITDA

### Longo Prazo (3–10 anos)
- [ ] O que invalidaria a tese em 3–10 anos?
- Ex.: disrupção tecnológica, mudança regulatória, moat corroído

**Regra**: se qualquer cenário de invalidação tiver probabilidade > 20%, documentar como risco primário e reduzir conviction score.

---

## 2. Stress-Checks Relâmpago

### A. WACC Sensitivity

| Δ WACC | Δ Valor Terminal | Δ Fair Value |
|--------|-----------------|-------------|
| +50 bps | | |
| +100 bps | | |
| −50 bps | | |

### B. Receita / ARPU

| Cenário | Δ FCFF 2029 | Δ Fair Value |
|---------|-------------|-------------|
| −5% receita/ARPU | | |
| −10% receita/ARPU | | |
| Churn +2 pp | | |

### C. CAPEX Manutenção

| Cenário | Δ Spread ROIC–WACC Terminal | Δ Fair Value |
|---------|---------------------------|-------------|
| CAPEX_man +2 pp receita | | |
| CAPEX_man +5 pp receita | | |

### D. Macro Brasil

| Cenário | Premissa | Δ WACC | Δ Fair Value |
|---------|---------|--------|-------------|
| Risco-país +100 bps | EMBI+ sobe | | |
| IPCA +2 pp | | | |
| Câmbio +20% | Para exportadoras/importadoras | | |

---

## 3. Fat Tails — Cenários Extremos (> 3σ)

| Cenário | Probabilidade | Fair Value | Peso no EV |
|---------|--------------|------------|-----------|
| Distress / Falência | % | R$ 0 ou < 0 | |
| Bear severo | % | | |
| Base | % | | |
| Bull | % | | |
| Mega-bull | % | | |
| **Expected Value ponderado** | 100% | | |

```
EV = Σ (p_i × FV_i)
```

---

## 4. Triangulação — Validação Cruzada (≥ 3 métodos)

| Método | Fair Value | % Upside/Downside | Peso |
|--------|------------|-------------------|------|
| FCFF (modelo base) | | | 40% |
| EPV (Earnings Power Value) | | | 20% |
| Múltiplos (EV/EBITDA peers) | | | 20% |
| Reverse DCF (implícito no preço) | | | 10% |
| P/VP = 1 (floor contábil) | | | 10% |
| **Football Field (range)** | min–max | | |

**Regra de coerência**: se FCFF e EPV divergem > 30% → ❗ investigar qual premissa é responsável.

---

## 5. Auditoria de Vieses Cognitivos

| Viés | Presente? | Mitigação Aplicada |
|------|-----------|--------------------|
| Ancoragem (no preço histórico) | | |
| Confirmação (buscar só evidência favorável) | | |
| Overconfidence (intervalo de confiança estreito) | | |
| Narrative fallacy (história sedutora sem base) | | |
| Herding (seguir consenso sem questionar) | | |
| Recency bias (dar peso excessivo ao recente) | | |

---

## 6. QMJ Score — Quality Minus Junk

Avaliar a "qualidade" da empresa em 3 dimensões:

| Dimensão | Indicadores | Nota (1-5) |
|----------|-------------|-----------|
| **Profitabilidade** | ROE, ROIC, margens, FCO/Lucro | |
| **Crescimento** | g receita, g NOPAT, crescimento IC | |
| **Segurança** | Alavancagem, cobertura juros, Z-Score | |
| **QMJ Total** | Média ponderada | |

**Referência**: Fama-French + Asness, Frazzini & Pedersen (2019).

---

## 7. Tabela Sensibilidade 7×7

WACC × g terminal (ou WACC × Margem NOPAT):

| g \ WACC | WACC−1% | WACC−0,5% | WACC | WACC+0,5% | WACC+1% | WACC+1,5% | WACC+2% |
|----------|---------|-----------|------|-----------|---------|-----------|---------|
| g+1% | | | | | | | |
| g+0,5% | | | | | | | |
| g (base) | | | **BASE** | | | | |
| g−0,5% | | | | | | | |
| g−1% | | | | | | | |
| g−1,5% | | | | | | | |
| g−2% | | | | | | | |

Highlight: células com Fair Value ≥ Preço Atual → zona de compra.
