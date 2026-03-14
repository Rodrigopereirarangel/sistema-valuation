# Bloco 3 — Reinvestimento por Segmento

> **Tabela Herdada:** manter internamente como contexto. Não exibir no output.

---

## Auditor Embedded (executar mentalmente antes de cada output)

```
1. NOPAT = Receita × Margem NOPAT
2. FCFF = NOPAT + D&A – CAPEX_total – ΔWC_total
3. CAPEX_total = CAPEX_exp + CAPEX_man  (por segmento E no consolidado)
4. ΔWC_total  = ΔWC_exp  + ΔWC_man   (por segmento E no consolidado)
5. Σ segmentos = consolidado (tolerância R$ 1 mi ou 0,1 pp)
6. Se qualquer ❗ → parar e corrigir antes de prosseguir
```

---

## PRÉ-ETAPA OBRIGATÓRIA — Auditoria de Guidance & Haircut de Management

> Executar antes de usar qualquer número forward-looking da empresa.
> Ver protocolo completo em `references/management-check.md`.

### A. Levantamento de Guidances Passados (5–10 anos)

| Ano | Métrica | Guidance Dado | Realizado | Erro (pp ou %) | Direção |
|-----|---------|--------------|-----------|----------------|---------|
| | Receita | | | | Over/Under |
| | EBITDA | | | | |
| | CAPEX | | | | |
| | Timeline projeto | | | | |

Base rate de referência (prior): gestão típica erra +10–15% em receita/margem e subestima capex em 10–20% e timeline em 30–50%.

### B. Score de Credibilidade & Haircut

| Score | % Acerto Histórico | Haircut Aplicado |
|-------|--------------------|-----------------|
| 5 | > 90% | 0–5% |
| 4 | 75–90% | 5–10% |
| 3 | 60–75% | 10–15% |
| 2 | 40–60% | 15–25% |
| 1 | < 40% | 25–40% |

**Score calculado:** [ ] → **Haircut definido:** [ ]%

### C. Cash Tax Rate

`Cash Tax Rate = IR pago / EBT` — histórico 5 anos, excluindo não-recorrentes.
Se diferença vs. peers > ±5 p.p. → registrar como 🟠, documentar justificativa e continuar.

**Cash Tax Rate calculado:** [ ]% (vs. 34% nominal)

> **A partir daqui, toda premissa de guidance recebe o haircut calculado acima.**

---

## 1. Matriz de Premissas por Segmento

| Segmento | Variável | Fonte | Valor Bruto | Haircut (%) | Valor Ajustado | Status |
|----------|----------|-------|-------------|-------------|----------------|--------|
| Seg A | Receita g% | | | | | OK/Atenção |
| Seg A | Margem NOPAT | | | | | |
| Seg A | CAPEX total | | +30–40% timeline | | | |
| Seg B | Receita g% | | | | | |

**Regressões utilizadas (quando guidance ausente):**
- 1º nível: [ método ]
- 2º nível: [ método ]
- 3º nível: [ método ]

---

## 2. Análise por Segmento — INDIVIDUAL

> **Regra:** projetar cada segmento de forma independente. Nunca agregar antes de cada segmento estar fechado e auditado individualmente.

### Regras Globais por Segmento
- Ano = 365 dias
- Δ% Receita ≤ Guidance ajustado (com haircut) + 2 pp
- NOPAT ≤ EBITDA em qualquer ano
- Demanda baixa → Preço/ARPU não sobe
- `CAPEX_total = CAPEX_exp + CAPEX_man` por segmento
- `ΔWC_total = ΔWC_exp + ΔWC_man` por segmento

---

### Segmento [A] — [Nome]

#### 2A-1. Cronograma & Ramp-up Logístico

Projetos em andamento, M&A, ramp-ups, paradas de manutenção.
S-curve onde aplicável: `Cap_t = Cap_max / (1 + e^(−k×(t−t0)))`

| Ano | Receita | g% | Margem NOPAT | NOPAT | D&A | CAPEX_exp | CAPEX_man | CAPEX_total | ΔWC_exp | ΔWC_man | ΔWC_total | FCFF_seg |
|-----|---------|----|-------------|-------|-----|----------|----------|------------|--------|--------|---------|---------|
| 2025 | | | | | | | | | | | | |
| 2026 | | | | | | | | | | | | |
| 2027 | | | | | | | | | | | | |
| 2028 | | | | | | | | | | | | |
| 2029 | | | | | | | | | | | | |

#### 2A-2. Invested Capital & D&A Granular

| Componente | Valor Inicial | Adições (CAPEX_exp) | Depreciação Anual | Saldo Final |
|------------|--------------|---------------------|------------------|-------------|
| PP&E operacional | | | | |
| ROU assets (IFRS 16) | | | | |
| Intangíveis / CAC | | | | |
| **IC Total Segmento A** | | | | |

#### 2A-3. ROIC do Segmento A

| Ano | NOPAT | IC Médio | ROIC_seg | WACC (ref) | Spread |
|-----|-------|---------|---------|-----------|--------|
| 2025 | | | | | |
| ... | | | | | |

*Opinião Analítica 3×3 — Driver → Impacto quantificado → Ação + KPI + Confiança*

---

### Segmento [B] — [Nome]

[Repetir estrutura 2B-1, 2B-2, 2B-3]

*Opinião Analítica 3×3*

---

### Segmento [N] — [Nome]

[Repetir para todos os segmentos ≥ 0,5% da receita]

---

## 3. Consolidação — Σ Segmentos

> Somente após TODOS os segmentos estarem individualmente fechados.

| Ano | Σ Receita | Σ NOPAT | Σ D&A | Σ CAPEX_total | Σ ΔWC_total | FCFF Consolidado | ✅/❗ |
|-----|----------|--------|-------|-------------|-----------|-----------------|------|
| 2025 | | | | | | | |
| 2026 | | | | | | | |
| 2027 | | | | | | | |
| 2028 | | | | | | | |
| 2029 | | | | | | | |

**Verificação por linha:**
- `FCFF_consol = Σ FCFF_seg` → diferença > R$ 1 mi = ❗
- `CAPEX_consol = Σ CAPEX_seg` → diferença > R$ 1 mi = ❗
- `ΔWC_consol = Σ ΔWC_seg` → diferença > R$ 1 mi = ❗

*Opinião Analítica 3×3*

---

## 4. Projeção de Dívida & D/EBITDA

| Ano | Dívida Líquida | EBITDA | D/EBITDA | Δ vs. anterior |
|-----|--------------|--------|---------|----------------|
| 2025 | | | | |
| ... | | | | |

---

## 5. WACC Dinâmico (nunca constante)

| Ano | NTN-B (venc. ≥ ano) | IPCA | D/EBITDA | βu peers | βl (realavancado) | Ke | Kd×(1−t) | WACC |
|-----|-------------------|------|---------|---------|-----------------|----|---------|----|
| 2025 | | | | | | | | |
| ... | | | | | | | | |

Regras:
- `βl = βu × (1 + (1−Cash Tax Rate) × D/EBITDA_ano)`
- NTN-B com vencimento ≥ ano projetado (curva, não ponto)
- ERP = ERP EUA (Damodaran) + CRP (EMBI+/CDS Brasil)

---

## 6. ROIC Consolidado & Spread

| Ano | NOPAT Consol | IC Médio Consol | ROIC | WACC | Spread ROIC–WACC |
|-----|------------|----------------|------|------|-----------------|
| 2025 | | | | | |
| ... | | | | | |

*Opinião Analítica 3×3*

---

## 7. Resumo do Cenário Base

- Por que esse cenário é **base e não otimista**
- Os 3 principais haircuts aplicados e suas justificativas
- Onde regressão foi usada (1º/2º/3º nível) e por quê

---

## 8. Auditoria

| Verificação | Resultado | Status |
|------------|-----------|--------|
| `FCFF = NOPAT + D&A – CAPEX_total – ΔWC` (cada seg + consol, por ano) | | ✅/❗ |
| `CAPEX_total = CAPEX_exp + CAPEX_man` (cada seg + consol) | | ✅/❗ |
| `ΔWC_total = ΔWC_exp + ΔWC_man` (cada seg + consol) | | ✅/❗ |
| `Σ segmentos = consolidado` (tolerância R$ 1 mi) | | ✅/❗ |
| `NOPAT ≤ EBITDA` em todos anos/segmentos | | ✅/❗ |
| Haircut de management aplicado e documentado | | ✅/❗ |
| Cash Tax Rate justificado | | ✅/🟠 |

Se qualquer ❗ → **"Reabrir Bloco 3 para correção antes de prosseguir"**

---

## 9. Alocação de Capital — Avaliação por Projeto

Para cada projeto relevante:
- Decisões acertadas (1–3 itens)
- Erros ou pontos cegos (1–3 itens)
- ROIC incremental, spread sobre WACC, impacto no FCFF

Análise geral: sequenciamento vs. ciclo de caixa · disciplina de preço · evolução de alavancagem.
