# Auditoria Forense Contábil

> Equivalente à Fase 1 do DCF Pipeline v3. Execute antes de qualquer projeção.

---

## Objetivo

Garantir que os números usados na análise são **limpos, normalizados e não manipulados**. Detectar:
- Manipulação contábil (Beneish M-Score)
- Itens não-recorrentes que distorcem o lucro
- Divergências entre lucro contábil e geração de caixa
- Sub/sobreinvestimento em ativos fixos

---

## 1. Beneish M-Score

### Fórmula

```
M = −4,84
  + 0,92  × DSRI   (Days Sales Receivable Index)
  + 0,528 × GMI    (Gross Margin Index)
  + 0,404 × AQI    (Asset Quality Index)
  + 0,892 × SGI    (Sales Growth Index)
  + 0,115 × DEPI   (Depreciation Index)
  − 0,172 × SGAI   (SGA Index)
  + 4,679 × TATA   (Total Accruals to Total Assets)
  − 0,327 × LVGI   (Leverage Index)
```

### Interpretação

| M-Score | Sinal |
|---------|-------|
| M > −1,78 | ❗ Alta probabilidade de manipulação |
| −2,22 < M ≤ −1,78 | 🟠 Zona de atenção — investigar |
| M ≤ −2,22 | OK — sem sinal relevante |

### Componentes — Cálculo e Interpretação

| Componente | Fórmula | Sinal de Alerta |
|-----------|---------|----------------|
| DSRI | `(CR_t/Receita_t) / (CR_{t-1}/Receita_{t-1})` | > 1,05 → 🟠 |
| GMI | `Margem Bruta_{t-1} / Margem Bruta_t` | > 1,00 → 🟠 |
| AQI | `(1 − (AC+PP&E)/Ativo_t) / (1 − (AC+PP&E)/Ativo_{t-1})` | > 1,05 → 🟠 |
| SGI | `Receita_t / Receita_{t-1}` | > 1,20 → 🟠 |
| DEPI | `(D&A_{t-1}/PP&E_{t-1}) / (D&A_t/PP&E_t)` | > 1,00 → 🟠 |
| SGAI | `(SGA/Receita)_t / (SGA/Receita)_{t-1}` | > 1,00 → 🟠 |
| TATA | `(Lucro Operacional − FCO) / Ativo Total` | > 0,031 → ❗ |
| LVGI | `(CP + DLP)_t/Ativo_t / (CP + DLP)_{t-1}/Ativo_{t-1}` | > 1,00 → 🟠 |

> **TATA** (accruals) é o componente mais preditivo. Accruals altos = lucro não suportado por caixa.

---

## 2. Qualidade do Lucro

### Índice de Qualidade de Accruals

```
Accruals = Lucro Líquido − FCO
Índice QA = FCO / Lucro Líquido  →  ideal > 1,0
```

| QA | Interpretação |
|----|--------------|
| > 1,0 | Lucro de alta qualidade (caixa > lucro) |
| 0,7–1,0 | OK |
| 0,5–0,7 | 🟠 Verificar composição dos accruals |
| < 0,5 | ❗ Lucro não suportado por caixa |

### Checklist de Normalização

Antes de projetar, ajustar o lucro base excluindo:
- [ ] Ganho/perda na venda de ativos
- [ ] Reversão de provisões
- [ ] Impairment de goodwill
- [ ] Resultado de equivalência patrimonial relevante
- [ ] Créditos tributários diferidos não recorrentes
- [ ] Hedge accounting distorcido
- [ ] SBC (Stock-Based Compensation) se relevante

---

## 3. ROE DuPont 5 Níveis

```
ROE = (Lucro / Receita) × (Receita / Ativo) × (Ativo / PL)
    = Margem Líquida × Giro do Ativo × Alavancagem Financeira

Decomposição 5 níveis:
ROE = (EBIT/Receita) × (Receita/Ativo) × (EBT/EBIT) × (LL/EBT) × (Ativo/PL)
    = Margem Operacional × Giro × Juros × Carga Fiscal × Alavancagem
```

**Objetivo**: identificar qual driver está mudando o ROE no tempo — operacional ou financeiro?

---

## 4. 3-Statement Check

Verificar consistência entre DRE, BP e DFC:

```
FCO ≈ EBITDA − ΔWC − IR pago − Juros pagos
FCI ≈ −CAPEX (aquisições líquidas)
FCF = FCO + FCI

Variação caixa = FCO + FCI + FCF
Caixa final = Caixa inicial + Variação caixa
```

Se inconsistência > 2% do Ativo Total → ❗ Investigar item fora do DFC

---

## 5. Análise de Sub-investimento (Asset Age)

```
Asset Age = PP&E líquido / PP&E bruto

Interpretação:
> 0,7  → Ativos novos (recente expansão ou pouco CAPEX man)
0,4–0,7 → Normal
< 0,4  → 🟠 Sub-investimento (risco de backlog de manutenção)
```

---

## 6. Tabela de Saída da Auditoria

| Item | Valor Reportado | Ajuste | Valor Normalizado | Fonte | Status |
|------|----------------|--------|-------------------|-------|--------|
| Receita | | | | | |
| EBITDA | | | | | |
| Margem EBITDA | | | | | |
| EBIT | | | | | |
| NOPAT | | | | | |
| FCO | | | | | |
| CAPEX | | | | | |
| ROE | | | | | |
| ROIC | | | | | |
| M-Score | | N/A | | | |
| Asset Age | | N/A | | | |

**Veredicto da Auditoria:**
- [ ] ✅ Aprovado — números limpos, análise pode prosseguir
- [ ] 🟠 Atenção — ajustes aplicados, documentados
- [ ] ❗ Reprovado — números não confiáveis, interromper pipeline
