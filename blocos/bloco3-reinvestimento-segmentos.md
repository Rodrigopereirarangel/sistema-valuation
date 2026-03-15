# Bloco 3 — Reinvestimento por Segmento

> **Tabela Herdada:** manter internamente como contexto. Não exibir no output.
>
> **Output obrigatório:** executar TODOS os sub-itens deste bloco com tabelas completas e Opinião Analítica 3×3 após cada sub-seção. Nunca resumir nem pular seções. Se ultrapassar o limite → "Parte 1 → CONT." e continuar imediatamente.

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

> **❗ REGRA ABSOLUTA:** Este segmento deve ser completamente projetado e auditado ANTES de iniciar o próximo. Proibido usar "[ver acima]", "[idem]" ou qualquer forma de referência cruzada que substitua dados reais.

#### 2A-0. Inventário de Projetos & Ramp-up por Projeto

Listar TODOS os projetos/contratos/expansões ativos ou previstos neste segmento. Para cada um:

| Projeto | Tipo | Cap_max (R$ mi) | k (vel.) | t0 (ano pico) | Status Atual | Receita Incremental Estimada |
|---------|------|----------------|---------|--------------|-------------|------------------------------|
| Proj 1 | expansão/M&A/ramp-up | | | | em ramp / maduro / planejado | |
| Proj 2 | | | | | | |

**S-curve obrigatória para cada projeto em fase de ramp-up:**
```
Cap_t = Cap_max / (1 + e^(−k×(t−t0)))
```
Calcular Cap_t explicitamente para cada ano de projeção (2025–2029). Não usar "onde aplicável" — se há ramp-up, calcular; se projeto maduro, documentar taxa de maturidade.

**Amadurecimento do parque/frota/carteira:**
- Receita do estoque atual: projetar com curva de degradação (anos de vida útil restantes, taxa de renovação)
- Receita de novos projetos: somar S-curves calculadas acima
- Separar explicitamente: Receita_estoque_atual + Receita_novos_projetos = Receita_total_segmento

| Ano | Receita_estoque_atual | g% | Receita_novos_projetos | Receita_total_seg | % mix novo/total |
|-----|-----------------------|----|----------------------|-------------------|-----------------|
| 2025 | | | | | |
| 2026 | | | | | |
| 2027 | | | | | |
| 2028 | | | | | |
| 2029 | | | | | |

#### 2A-1. Projeção Financeira do Segmento (anos 2025–2029+)

| Ano | Receita | g% | Margem NOPAT | NOPAT | D&A | CAPEX_exp | CAPEX_man | CAPEX_total | ΔWC_exp | ΔWC_man | ΔWC_total | FCFF_seg |
|-----|---------|----|-------------|-------|-----|----------|----------|------------|--------|--------|---------|---------|
| 2025 | | | | | | | | | | | | |
| 2026 | | | | | | | | | | | | |
| 2027 | | | | | | | | | | | | |
| 2028 | | | | | | | | | | | | |
| 2029 | | | | | | | | | | | | |

**Verificação aritmética (mostrar cálculo para cada ano):**
`FCFF = NOPAT + D&A − CAPEX_total − ΔWC_total`
- 2025: ___ + ___ − ___ − ___ = ___  ✅/❗
- 2026: ___ + ___ − ___ − ___ = ___  ✅/❗

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
| 2026 | | | | | |
| 2027 | | | | | |
| 2028 | | | | | |
| 2029 | | | | | |

*Opinião Analítica 3×3 — Driver → Impacto quantificado → Ação + KPI + Confiança*

---

### Segmento [B] — [Nome]

> **❗ REGRA ABSOLUTA:** Repetir COMPLETAMENTE as seções 2B-0, 2B-1, 2B-2, 2B-3 com todos os dados reais. Proibido escrever "[Repetir estrutura]" ou qualquer atalho.

#### 2B-0. Inventário de Projetos & Ramp-up por Projeto

[Estrutura idêntica à 2A-0 — listar projetos, S-curves calculadas, amadurecimento do parque]

#### 2B-1. Projeção Financeira do Segmento

[Tabela idêntica à 2A-1 com dados reais do Segmento B]

#### 2B-2. Invested Capital & D&A Granular

[Tabela idêntica à 2A-2 com dados reais do Segmento B]

#### 2B-3. ROIC do Segmento B

[Tabela idêntica à 2A-3 com dados reais do Segmento B]

*Opinião Analítica 3×3*

---

### Segmento [N] — [Nome]

> **Para TODOS os segmentos com receita ≥ 0,5% do total: repetir seções N-0, N-1, N-2, N-3 na íntegra.**
> Proibido consolidar segmentos menores sem análise individual documentada.

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

> **❗ NTN-B: PROIBIDO aproximar ou estimar.** Usar taxas exatas do ANBIMA publicadas.
> Fonte: ANBIMA → Mercados → Taxas de Referência → Títulos Públicos.
> Registrar data de consulta + vencimento exato usado para cada ano projetado.
> Se vencimento exato indisponível: interpolação linear entre vencimentos adjacentes — mostrar cálculo.

### 5A. Curva NTN-B (ANBIMA — data da consulta: dd/mm/aaaa)

| Vencimento NTN-B | Taxa ANBIMA (% real a.a.) | Ano(s) de Projeção Coberto(s) |
|------------------|--------------------------|-------------------------------|
| NTN-B 2026 | % | 2025–2026 |
| NTN-B 2028 | % | 2027–2028 |
| NTN-B 2030 | % | 2029–2030 |
| NTN-B 2035 | % | 2031–2035 |
| NTN-B 2045 | % | Terminal |

### 5B. Tabela WACC Anual

| Ano | NTN-B real (ANBIMA) | IPCA (Focus) | ERP EUA (Damodaran) | CRP Brasil (EMBI+ data) | ERP Total | βu peers | D/EBITDA | βl | Ke nominal | Kd×(1−t) | WACC nominal | WACC real |
|-----|--------------------|--------------|--------------------|------------------------|----------|---------|---------|-----|-----------|---------|------------|---------|
| 2025 | | | | | | | | | | | | |
| 2026 | | | | | | | | | | | | |
| 2027 | | | | | | | | | | | | |
| 2028 | | | | | | | | | | | | |
| 2029 | | | | | | | | | | | | |

Regras:
- `βl = βu × (1 + (1 − Cash Tax Rate) × D/EBITDA_ano)`
- `Ke_nominal = NTN-B_real + IPCA_ano + βl × ERP_total`
- ERP EUA: Damodaran atualização mais recente (citar data); CRP: EMBI+ ou CDS 5Y Brasil (citar valor e data)
- Kd: saí do inventário de dívida do Bloco 4.0 — não estimar genericamente

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
