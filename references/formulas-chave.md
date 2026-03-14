# Fórmulas-Chave — Referência Rápida

---

## Valuation Core

| Fórmula | Expressão | Bloco/Fase |
|---------|-----------|-----------|
| FCFF | `FCFF = NOPAT + D&A − CAPEX_total − ΔWC_total` | 3a, 3b |
| NOPAT | `NOPAT = EBIT × (1 − t)` | 1, 3a |
| ROIC | `ROIC = NOPAT / Invested Capital` | 1, 2 |
| ROIIC | `ROIIC = ΔNOPAT / ΔIC` | 2, 3a |
| ROE Decomposed | `ROE = ROIC + (ROIC − Kd×(1−t)) × D/E` | 1, 2 |
| Gordon TV | `TV = FCFF(t+1) / (WACC − g)` | 5 |
| McKinsey CV | `CV = NOPAT(t+1) × (1 − g/RONIC) / (WACC − g)` | 5 |
| EPV | `EPV = NOPAT normalizado / WACC` | 5, 7 |
| g consistency | `g = ROIIC × Taxa de Reinvestimento` | 3a, 3b |

---

## Capex (Red Queen)

| Fórmula | Expressão | Nota |
|---------|-----------|------|
| Capex total | `CAPEX_total = CAPEX_exp + CAPEX_man` | Obrigatório em todos os anos |
| ΔWC total | `ΔWC_total = ΔWC_exp + ΔWC_man` | Obrigatório em todos os anos |
| Asset Age | `Age = PP&E líquido / PP&E bruto` | < 0,4 → 🟠 sub-investimento |
| FCFF real | `FCFF = NOPAT + D&A − CAPEX_exp − CAPEX_man − ΔWC` | Nunca somar Exp + Man ao FCFF |

---

## Custo de Capital (WACC Dinâmica)

| Fórmula | Expressão | Fase |
|---------|-----------|------|
| CAPM (Ke) | `Ke = Rf + β × ERP + CRP` | 4 |
| WACC | `WACC = Ke × E/(D+E) + Kd×(1−t) × D/(D+E)` | 4 |
| β Unlevered | `βu = βl / [1 + (1−t) × D/E]` | 4 |
| β Relevered | `βl = βu × [1 + (1−t) × D/E_target]` | 4 |
| **Penman Rule** | **`Se g > IPCA + 1% → questionar Ke ↑`** | **4, 3b** |

**WACC Brasil:**
- **Rf** = NTN-B com vencimento ≥ ano projetado (curva, não ponto)
- **ERP** = ERP EUA (Damodaran) + CRP (EMBI+ ou CDS Brasil)
- **β** = desalavancado de peers, realavancado com D/EBITDA do ano
- **IR** = Cash Tax Rate real (EBT/IR pago, histórico 5 anos, excluindo não-recorrentes)

---

## Fade de ROIC

| Fórmula | Expressão |
|---------|-----------|
| Fade Rate | `fade = ln(2) / half-life (anos)` |
| ROIC_t | `ROIC_t = WACC + (ROIC_0 − WACC) × e^(−fade × t)` |
| g terminal | `g = (ROIC_terminal − WACC_terminal) × reinvest_rate` |

**Regra do Valor Terminal:**
```
ROIC_10 = WACC_10 + 1 pp
reinvest_rate_10 = 35%
g_etern = 1% × 35% = 0,35%
VT = FCFF_11 / (WACC_10 − g_etern)
```
Verificar: `g_real ≤ PIB potencial Brasil (~2–2,5% real)`

---

## Detecção de Manipulação Contábil (Beneish M-Score)

```
M = −4,84 + 0,92×DSRI + 0,528×GMI + 0,404×AQI + 0,892×SGI
    + 0,115×DEPI − 0,172×SGAI + 4,679×TATA − 0,327×LVGI
```

| Score | Interpretação |
|-------|--------------|
| M > −1,78 | ❗ Alta probabilidade de manipulação |
| −2,22 < M < −1,78 | 🟠 Zona de atenção |
| M < −2,22 | OK (sem sinal de manipulação) |

**Componentes-chave:**
- **DSRI** = Days Sales Receivable Index (↑ = inflação de receita)
- **GMI** = Gross Margin Index (↓ = deterioração de margem)
- **AQI** = Asset Quality Index (↑ = ativos intangíveis suspeitos)
- **TATA** = Total Accruals / Total Assets (↑ = contabilidade agressiva)

---

## Ciclo de Caixa

| Fórmula | Expressão |
|---------|-----------|
| PMR | `Prazo Médio Recebimento = (CR / Receita) × 365` |
| PME | `Prazo Médio Estoque = (Estoque / CMV) × 365` |
| PMP | `Prazo Médio Pagamento = (CP / CMV) × 365` |
| Ciclo Operacional | `CO = PMR + PME` |
| Ciclo de Caixa | `CC = CO − PMP` |

---

## Sizing & Decisão

| Fórmula | Expressão |
|---------|-----------|
| Kelly Full | `f* = (p × b − q) / b` onde `q = 1 − p` |
| Half-Kelly | `f = f* × 0,5` ← **recomendado** |
| Conviction Score | `CS = 0,25×Upside + 0,20×Moat + 0,20×Mgmt + 0,15×Projeção + 0,10×Triangul + 0,10×QMJ` |

---

## Reverse DCF & MEROI

| Fórmula | Expressão |
|---------|-----------|
| MEROI | `MEROI = (EV − PV dos FCFs explícitos) / Reinvestimento total` |
| ERP implícito | `ERP* que iguala P_target a P_mkt` |
| Net Payout Yield | `NPY = (Buybacks + Dividendos − Emissões) / Market Cap` |

---

## Estatísticos

| Fórmula | Expressão |
|---------|-----------|
| Bayes Update | `P(H\|E) = P(E\|H) × P(H) / P(E)` |
| Valor Esperado | `E[V] = Σ p_i × V_i` (cenários ponderados) |
