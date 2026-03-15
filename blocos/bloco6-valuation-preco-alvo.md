# Bloco 6 — Valuation FCFF & Preço-Alvo

> **Tabela Herdada:** manter internamente como contexto. Não exibir no output.
>
> **Output obrigatório:** executar TODOS os sub-itens deste bloco com tabelas completas e Opinião Analítica 3×3 após cada sub-seção. Nunca resumir nem pular seções. Se ultrapassar o limite → "Parte 1 → CONT." e continuar imediatamente.
> Pré-requisito: Bloco 5 (Auditoria 360°) aprovado sem ❗.

---

## 1. Tabela FCFF (Anos 1–10)

Integrar FCFF anual dos Blocos 3 e 4 com fator de desconto.

| Ano | FCFF | Fator Desconto (WACC_ano) | VP do FCFF |
|-----|------|--------------------------|-----------|
| 1 | | | |
| 2 | | | |
| 3 | | | |
| 4 | | | |
| 5 | | | |
| 6 | | | |
| 7 | | | |
| 8 | | | |
| 9 | | | |
| 10 | | | |
| **Σ VP FCFFs** | | | |

*Opinião Analítica 3×3 — Driver → Impacto quantificado → Ação + KPI + Confiança*

---

## 2. Valor Terminal (Fade ROIC)

```
ROIC_10   = WACC_10 + 1 pp
Spread_10 = 1 pp
Taxa_Reinvest_10 = 35%
g_etern   = Spread_10 × Taxa_Reinvest_10 = 1% × 35% = 0,35%

VT = FCFF_11 / (WACC_10 − g_etern)
   = FCFF_10 × (1 + g_etern) / (WACC_10 − g_etern)

VP_VT = VT / (1 + WACC_10)^10
```

| Variável | Valor |
|----------|-------|
| FCFF_ano10 | |
| WACC_ano10 | % |
| g_etern | 0,35% |
| Valor Terminal (VT) | R$ _____ mi |
| VP do Valor Terminal | R$ _____ mi |
| TV/EV (%) | ___% → se > 75% → 🟠 |

Sanity checks:
- `g_real ≤ PIB potencial Brasil (~2–2,5% real)` → ✅/🟠
- `TV/EV < 75%` → ✅/🟠
- `ROIC_terminal > WACC_terminal` (spread positivo) → ✅/❗

*Opinião Analítica 3×3*

---

## 3. Bridge EV → Equity Value → Preço-Alvo

```
EV = Σ VP_FCFFs + VP_VT
Equity Value = EV − Dívida Líquida + Caixa − Minoritários + Outros ativos não-operacionais
Preço-Alvo = Equity Value / Nº Ações (diluído)
```

| Item | Valor (R$ mi) |
|------|--------------|
| Σ VP FCFFs (Anos 1–10) | |
| VP Valor Terminal | |
| **Enterprise Value (EV)** | |
| (−) Dívida Líquida | |
| (+) Caixa não-operacional | |
| (−) Minoritários | |
| (+/−) Outros ajustes | |
| **Equity Value** | |
| Nº Ações (diluído, mi) | |
| **Preço-Alvo (R$)** | |
| Preço Atual (R$) | |
| **Upside / Downside (%)** | |

*Opinião Analítica 3×3*

---

## 4. ERP Implícito (ERP*) ❗ OBRIGATÓRIO — não pode ser pulado

> **Esta seção é obrigatória e não pode ser omitida.** O ERP* é o termômetro de quanto o mercado está exigindo vs. o modelo. Sem ele, a análise não está completa.

```
ERP* = ERP que, mantendo todas as outras premissas fixas,
       iguala o Equity Value/Ação ao Preço Atual de mercado.

Procedimento:
1. Fixar: FCFF_1..10, VT (g e ROIC_terminal), Dívida Líquida, Nº Ações, NTN-B exata, βl, Kd
2. Iterar ERP até: Equity Value / Nº Ações = Preço Atual de mercado
3. ERP* é o valor que fecha essa equação
4. WACC* = NTN-B_real + IPCA + βl × ERP*

Δ ERP = ERP* − ERP_base usado no modelo
```

| Variável | Valor |
|----------|-------|
| Preço Atual de mercado (R$) | |
| ERP base usado no modelo | % |
| NTN-B real usada (vencimento exato, taxa ANBIMA) | % |
| βl terminal | |
| **ERP implícito (ERP*)** | % |
| **WACC* implícito** | % |
| Δ ERP vs. base (pp) | |
| ERP histórico Brasil (Damodaran, ref. ano atual) | % |
| ERP* vs. ERP histórico — sinal | acima → ação cara ou risco elevado / abaixo → barata ou mercado otimista |

**Análise narrativa obrigatória (mínimo 2 parágrafos):**
- O que o ERP* revela sobre o que o mercado está precificando implicitamente?
- O ERP* é plausível dado o ambiente macro atual (NTN-B, EMBI+, ciclo de juros)?
- Confrontar ERP* com ERP de mercados emergentes (Damodaran) e com o CRP atual do Brasil.

*Opinião Analítica 3×3*

---

## 5. Tabela de Sensibilidade (WACC × g)

| g \ WACC | −1% | −0,5% | Base | +0,5% | +1% | +1,5% | +2% |
|----------|-----|-------|------|-------|-----|-------|-----|
| g + 1% | | | | | | | |
| g + 0,5% | | | | | | | |
| **g base** | | | **BASE** | | | | |
| g − 0,5% | | | | | | | |
| g − 1% | | | | | | | |
| g − 1,5% | | | | | | | |
| g − 2% | | | | | | | |

Highlight: células com Preço-Alvo ≥ Preço Atual → zona de atratividade.

*Opinião Analítica 3×3*

---

## 6. Comentários Críticos do Analista (≥ 7 pontos)

1.
2.
3.
4.
5.
6.
7.

---

## 7. Resumo Técnico Final

- Fair Value: R$ _____ · Upside/Downside: _____%
- Principal driver de valor: _____
- Principal risco ao cenário base: _____
- Confiança geral na análise: Alta / Média / Baixa
- KPIs a monitorar: (1) _____ · (2) _____
