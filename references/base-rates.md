# Base Rates Empíricas

> Fonte primária: Papers Mauboussin & Callahan (Morgan Stanley / Counterpoint Global)
> Usar como **prior bayesiano** em toda premissa. Só desviar com evidência marginal explícita.

---

## ROIC Mediano por Setor

| Setor | ROIC Mediano | P25 | P75 |
|-------|-------------|-----|-----|
| Technology | 18% | 8% | 35% |
| Healthcare (Pharma) | 14% | 5% | 28% |
| Consumer Staples | 16% | 10% | 25% |
| Consumer Discretionary | 12% | 5% | 22% |
| Industrials | 11% | 6% | 18% |
| Financials | 10% | 6% | 15% |
| Energy | 8% | 2% | 16% |
| Utilities | 6% | 4% | 9% |
| Materials | 9% | 4% | 16% |
| Real Estate | 5% | 3% | 8% |
| Telecom | 8% | 4% | 14% |

**Uso**: prior bayesiano inicial para spread ROIC–WACC em Bloco 2 e 3a.

---

## Persistência de ROIC

| Métrica | 5 anos | 10 anos | 15 anos |
|---------|--------|---------|---------|
| % empresas com ROIC > 15% | ~50% | ~30% | ~15% |
| % empresas com ROIC > WACC | ~60% | ~40% | ~25% |
| Half-life médio de excesso ROIC | 5–7 anos | — | — |

**Implicação**: A maioria das empresas tem fade de ROIC em 5–10 anos. Sustentar ROIC > WACC além de 10 anos exige moat excepcional.

---

## Fade Half-Life por Setor

| Setor | Half-Life (anos) | Fade Rate (ln2/HL) |
|-------|------------------|-------------------|
| Technology | 5–7 | 0,10–0,14 |
| Healthcare (Pharma) | 7–10 | 0,07–0,10 |
| Consumer Staples | 8–12 | 0,06–0,09 |
| Consumer Discretionary | 4–6 | 0,12–0,17 |
| Industrials | 6–8 | 0,09–0,12 |
| Energy | 3–5 | 0,14–0,23 |
| Utilities | 10–15 | 0,05–0,07 |
| Telecom | 6–9 | 0,08–0,12 |

```
Fade Rate = ln(2) / Half-life
```

**Uso**: definir velocidade de convergência ROIC → WACC no período terminal (Bloco 3b).

---

## Taxas de Sucesso de Grandes Projetos

| Métrica | Base Rate |
|---------|-----------|
| % projetos entregues on-time | ~35% |
| % projetos on-budget | ~30% |
| Cost overrun médio | +40% do orçamento original |
| Delay médio | +50% do prazo original |
| % projetos que atingem ROIC projetado | ~25% |

**Implicação direta**: Aplicar haircut de +30–50% no timeline e +30–40% no capex de projetos em andamento. Default haircut de gestão: 10–15% em receita/margem projetadas.

---

## Margem EBITDA por Setor

| Setor | Mediana | P25 | P75 |
|-------|---------|-----|-----|
| Software/SaaS | 25% | 15% | 40% |
| Pharma | 30% | 18% | 45% |
| Consumer Staples | 18% | 12% | 25% |
| Retail | 8% | 4% | 14% |
| Banking | 40% | 30% | 55% |
| Industrials | 14% | 8% | 22% |
| Mining | 35% | 15% | 50% |
| Utilities | 30% | 22% | 40% |
| Telecom | 28% | 20% | 38% |

---

## Mix de Alocação de Capital — Pares Maduros (referência para cash-sweep)

> "Pares maduros" = empresas do mesmo setor, ≥ 10 anos listadas, > 40% payout (dividendos + buybacks) nos últimos 3 anos.

| Uso | % do FCF — Referência Pares Maduros |
|-----|-------------------------------------|
| Capex manutenção | 15–25% |
| Capex expansão orgânica | 5–15% |
| M&A | 5–15% |
| Buybacks | 20–35% |
| Dividendos | 20–30% |
| Acúmulo de Caixa | 5–10% |

**Critério de seleção de pares maduros:**
- ≥ 10 anos listados em bolsa (BR ou exterior)
- > 40% payout (dividendos + buybacks) nos últimos 3 anos
- Mesmo setor ou setor comparável
- D/EBITDA estável nos últimos 3 anos (convergido)
- Fontes: Economatica, Bloomberg, Damodaran (páginas setoriais)

**Uso no modelo:**
- Definir D/EBITDA alvo para o período de cash-sweep (Bloco 3b)
- Calibrar % de cash-sweep (60–80% do FCFF) em linha com pares
- Referência para payout ratio no fade terminal (Bloco 3b, Bloco 5)

---

## Crescimento por Estágio do Ciclo de Vida

| Estágio | FCO | FCI | FCF | Crescimento Receita Típico |
|---------|-----|-----|-----|--------------------------|
| Start-up | − | − | + | > 30% |
| Growth | + | − | + | 15–30% |
| Mature | + | − | − | 3–8% |
| Shake-out | +/− | − | −/+ | 0–5% |
| Decline | − | + | − | < 0% |

---

## Concentração de Criação de Valor

| Métrica | Valor |
|---------|-------|
| % de empresas que criam 90% do wealth | ~4% |
| % de ações que superam T-Bills ao longo da vida | ~42% |
| Retorno mediano lifetime de uma ação | −3,7% |

**Implicação**: A maioria das empresas destrói valor. Empresas com moat forte e ROIC consistente são raras e merecem atenção premium.

---

## Guidance vs. Realizado — Viés Típico de Gestão

| Métrica | Viés médio |
|---------|-----------|
| Receita | +5 a +10% otimista |
| EBITDA | +8 a +15% otimista |
| Capex | −10 a −20% (subestima) |
| Timeline de projetos | −30 a −50% (subestima prazo) |

**Default de haircut**: 10–15% em receita/margem forward; +30–50% em timeline de projetos.
