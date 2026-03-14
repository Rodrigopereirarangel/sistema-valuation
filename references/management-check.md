# Análise de Gestão & Alocação de Capital

> Equivalente à Fase 2.5 do DCF Pipeline v3. Executar antes de usar qualquer guidance na projeção.

---

## Objetivo

Avaliar a **qualidade e credibilidade da gestão** para:
1. Calibrar o haircut sobre guidance (nunca usar sem desconto)
2. Avaliar a disciplina de alocação de capital (ROIC incremental de cada decisão)
3. Mapear projetos em andamento com S-curves (ramp-up logístico)

---

## 1. Track Record de Assertividade

### Protocolo

1. Levantar guidances dos últimos **5–10 anos** (call de resultados, press releases, RI)
2. Para cada guidance, registrar: prometido vs. realizado
3. Calcular % de acerto por métrica

### Tabela de Track Record

| Ano | Métrica | Guidance | Realizado | Erro (pp ou %) | Direção |
|-----|---------|----------|-----------|---------------|---------|
| 2024 | Receita | | | | Over/Under |
| 2024 | EBITDA | | | | |
| 2024 | CAPEX | | | | |
| 2023 | Receita | | | | |
| ... | ... | | | | |

### Score de Credibilidade

| Score | % Acerto Histórico | Haircut Default |
|-------|--------------------|-----------------|
| 5 | > 90% | 0–5% |
| 4 | 75–90% | 5–10% |
| 3 | 60–75% | 10–15% |
| 2 | 40–60% | 15–25% |
| 1 | < 40% | 25–40% |

**Base rate de referência:** gestão típica é 10–15% otimista em receita/margem e subestima capex em 10–20%.

---

## 2. Mapa de Alocação de Capital (10 anos)

Para cada grande decisão de capital, avaliar:

| Ano | Decisão | CAPEX/Invest. | ROIC Incremental | Spread (ROIC–WACC) | Status |
|-----|---------|--------------|------------------|-------------------|--------|
| | Expansão X | | | | Em andamento / Concluído |
| | Aquisição Y | | | | |
| | Buyback | | | | |
| | Dividendo extraordinário | | | | |

**Análise por decisão:**
- Acertos: o que foi feito bem?
- Erros: pontos cegos ou sobreinvestimentos?
- Efeito no valor: ROIC incremental, spread sobre WACC, impacto no FCFF

---

## 3. Projetos em Ramp-up (S-Curves)

Para cada projeto relevante em andamento:

### Template de S-Curve

```
Capacidade Máxima: [X unidades ou R$ Y de receita]
Início: [data]
Maturidade Esperada: [data]
CAPEX total estimado: R$ [X] mi

Progresso físico: [X]%
Progresso financeiro: [X]% do orçamento

Curva logística:
Capacidade_t = Cmax / (1 + e^(-k × (t - t0)))
onde k = taxa de crescimento, t0 = ponto de inflexão
```

### Base rates para projetos (aplicar como prior):
- On-time: ~35% dos projetos
- On-budget: ~30%
- Cost overrun médio: +40%
- Delay médio: +50% do prazo
- % que atingem ROIC projetado: ~25%

**Default haircut**: +30–50% no timeline, +30–40% no capex orçado.

---

## 4. Alocação de Capital — Sequenciamento

Avaliar o sequenciamento de projetos vs. ciclo de caixa:

1. **Os projetos foram sequenciados corretamente?** (não sobrecarregar D/EBITDA)
2. **Disciplina de preço:** há sacrifício de margem para crescer?
3. **Evolução da alavancagem:** D/EBITDA aumenta de forma controlada ou acelerada?
4. **Política de distribuição:** dividendos e buybacks vs. retorno marginal de novos projetos

---

## 5. Tabela de Saída — Management Score

| Critério | Nota (1-10) | Fonte | Observação |
|----------|-------------|-------|-----------|
| Assertividade de guidance | | | |
| Disciplina de CAPEX | | | |
| Alocação de capital (ROIC incremental) | | | |
| Transparência com mercado | | | |
| Track record de projetos | | | |
| **Média** | | | **Score final** |

**Haircut final aplicado às projeções:** _____%

---

## 6. Integração com o Modelo

- Receita projetada × (1 − haircut) antes de inserir no modelo
- Timeline de projetos ajustado pelo factor de delay histórico
- CAPEX de projetos ajustado pelo factor de custo overrun histórico
- Classificar premissas como "Atenção" na tabela herdada quando haircut > 10%
