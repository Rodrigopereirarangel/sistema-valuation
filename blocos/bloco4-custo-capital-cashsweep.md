# Bloco 4 — Custo de Capital & Cash-Sweep

> **Tabela Herdada:** manter internamente como contexto. Não exibir no output.
>
> **Output obrigatório:** executar TODOS os sub-itens deste bloco com tabelas completas e Opinião Analítica 3×3 após cada sub-seção. Nunca resumir nem pular seções. Se ultrapassar o limite → "Parte 1 → CONT." e continuar imediatamente.
> Pré-requisito: Bloco 3 aprovado sem ❗.

---

## 0. Estrutura Completa da Dívida (por Instrumento) ❗ OBRIGATÓRIO

> Executar ANTES de qualquer cálculo de WACC ou cash-sweep. O Kd real saí daqui.
> **Proibido usar custo de dívida agregado sem mapear cada instrumento individualmente.**

### 0A. Inventário de Instrumentos de Dívida

Para cada instrumento (debêntures, CRI, CRA, CCB, notas, BNDES, leasing financeiro, etc.):

| Instrumento | Código/Série | Saldo (R$ mi) | Indexador | Spread/Taxa | Taxa All-in | Vencimento | Prazo Restante (anos) | Amortização |
|-------------|-------------|--------------|---------|-------------|------------|------------|----------------------|-------------|
| Debênture 1 | | | IPCA+ / CDI+ / pré | | % a.a. | dd/mm/aaaa | | bullet/amort |
| Debênture 2 | | | | | | | | |
| CRI | | | | | | | | |
| BNDES | | | TJLP / IPCA | | | | | |
| Leasing IFRS 16 | | | | | | | | |
| **Total** | | | | | | | | |

**Fonte obrigatória:** Notas Explicativas (NE) do último ITR/DFP publicado. Citar nota e página.

### 0B. Kd Ponderado Real

```
Kd_bruto = Σ (Saldo_i × Taxa_all-in_i) / Σ Saldo_i
Kd_líquido = Kd_bruto × (1 − Cash Tax Rate)
```

| Métrica | Valor |
|---------|-------|
| Kd bruto ponderado | % a.a. |
| Cash Tax Rate aplicado | % |
| **Kd líquido (para WACC)** | % a.a. |
| Prazo médio ponderado da dívida | anos |
| % dívida indexada IPCA+ | % |
| % dívida indexada CDI+ | % |
| % dívida prefixada | % |

### 0C. Risco de Refinanciamento

| Ano | Vencimentos (R$ mi) | % da Dívida Total | Cobertura (FCFF/Vencimentos) | Risco |
|-----|--------------------|--------------------|-------------------------------|-------|
| 2025 | | | | Baixo/Médio/Alto |
| 2026 | | | | |
| 2027 | | | | |
| 2028 | | | | |
| 2029 | | | | |

🟠 se vencimento concentrado > 30% da dívida em 1 ano sem geração de caixa suficiente.

*Opinião Analítica 3×3 — Driver → Impacto quantificado → Ação + KPI + Confiança*

---

## 1. Cash-Sweep & Redução de Alavancagem

Alocar 60–80% do FCFF para amortização de dívida e/ou distribuição até D/EBITDA atingir nível de pares maduros.

**Regras:**
- ΔCaixa loop fecha: `Dívida_t = Dívida_{t-1} − Cash-Sweep_t + Novas emissões_t`
- Ações diminuem com buyback (atualizar preço por múltiplos de pares maduros no ano do buyback)
- Pares maduros: ≥ 10 anos em bolsa · > 40% payout nos últimos 3 anos · mesmo setor (ver `references/base-rates.md`)
- `% cash-sweep` definido pela premissa de manutenção do ROIC% e continuidade de expansão orgânica sem grandes projetos
- CAPEX_man, CAPEX_exp, ΔWC_exp, ΔWC_man calculados por regressão múltipla com técnica justificada (1º/2º/3º nível)
- WACC dinâmico ajustado anualmente pela curva

**Técnica de regressão utilizada:**
- 1º nível: [ método ]
- 2º nível: [ método ]
- 3º nível: [ método ]

| Ano | FCFF | Cash-Sweep (%) | Cash-Sweep (R$) | Buyback | Dividendo | Δ Dívida Líquida | D/EBITDA | WACC |
|-----|------|----------------|----------------|---------|-----------|-----------------|---------|------|
| | | | | | | | | |

*Opinião Analítica 3×3 — Driver → Impacto quantificado → Ação + KPI + Confiança*

---

## 2. Reconciliação IFRS

Verificar desvio entre FCFF direto (DFC) e FCFF indireto (reconstruído):

| Item | FCFF Direto (DFC) | FCFF Indireto | Δ | Status |
|------|------------------|--------------|---|--------|
| NOPAT | | | | |
| D&A | | | | |
| CAPEX_total | | | | |
| ΔWC_total | | | | |
| **FCFF** | | | | |

Se desvio > 2 pp → corrigir antes de prosseguir.

*Opinião Analítica 3×3*

---

## 3. Fade de ROIC

D/EBITDA se mantém estático após convergência.
Fade do ROIC em no máximo 5 anos até `ROIC = WACC + 0,5%`.
WACC dinâmico ajustado por curva em cada ano.

| Ano | ROIC | WACC | Spread | g orgânico | Taxa Reinvest. | FCFF_fade |
|-----|------|------|--------|-----------|---------------|---------|
| | | | | | | |
| **Terminal** | WACC + 0,5% | | 0,5% | | | |

*Opinião Analítica 3×3*

---

## 4. Invested Capital & D&A Granular (pós cash-sweep)

Por segmento e consolidado, até ano de convergência do fade.

| Componente | Ano 1 | Ano 3 | Ano 5 | Ano 10 | Terminal |
|------------|-------|-------|-------|--------|---------|
| PP&E operacional | | | | | |
| ROU assets (IFRS 16) | | | | | |
| Intangíveis / CAC | | | | | |
| **IC Total Consolidado** | | | | | |

---

## 5. Projeção Anos 1–10 por Segmento e Consolidado

Por segmento até o Ano 10, depois consolidado. Priorizar guidance/entrevista com haircut aplicado.

**Tabela por segmento [A]:**

| Ano | Receita | NOPAT | D&A | CAPEX_total | ΔWC_total | FCFF_seg | ROIC_seg |
|-----|---------|-------|-----|------------|---------|---------|---------|
| 1 | | | | | | | |
| ... | | | | | | | |
| 10 | | | | | | | |

**Tabela Consolidada:**

| Ano | Σ Receita | Σ NOPAT | Σ D&A | Σ CAPEX | Σ ΔWC | FCFF | D/EBITDA | WACC | ROIC | Spread |
|-----|----------|--------|-------|--------|------|------|---------|------|------|--------|
| 1 | | | | | | | | | | |
| ... | | | | | | | | | | |
| 10 | | | | | | | | | | |

*Opinião Analítica 3×3*

---

## 6. Snapshot FCFF & g Terminal Real

```
g_etern = (ROIC_terminal − WACC_terminal) × Taxa_Reinvestimento_terminal
g_real ≤ PIB potencial Brasil (~2–2,5% real)
```

| Variável | Valor | Fonte |
|----------|-------|-------|
| FCFF_ano10 | | |
| ROIC_terminal | WACC + 0,5% | fade |
| WACC_terminal | | NTN-B longa + EMBI+ |
| Taxa Reinvest. terminal | | pares maduros |
| g_etern | | calculado |
| g_real implícito | | ≤ PIB potencial? |

*Opinião Analítica 3×3*

---

## 7. Resumo do Cenário Base

- Por que esse cenário é **base e não otimista**
- Justificativa do % de cash-sweep escolhido
- Justificativa da velocidade de fade de ROIC (vs. half-life setorial)
