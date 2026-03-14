# Regras Globais do Pipeline

> Aplicam-se a TODOS os blocos e fases. Nenhuma pode ser ignorada.

---

## 1. Regra Penman (growth → risk) ⚠️

**Se `g > IPCA + 1%`, questionar obrigatoriamente se `Ke` não deveria aumentar.**

- Crescimento acima da inflação real exige reinvestimento adicional → risco marginal maior
- Exigir justificativa explícita com fonte primária (guidance + peer) quando g elevado
- Revisar WACC antes de aceitar premissa de crescimento acelerado

```
Se g > IPCA + 1% → alertar "❗ Regra Penman ativada — revisar Ke"
```

---

## 2. Sistema de Alertas ❗/🟠

| Símbolo | Nível | Ação Obrigatória |
|---------|-------|-----------------|
| ❗ | GRAVE | **Parar o pipeline.** Exige correção antes de prosseguir. |
| 🟠 | ATENÇÃO | Investigar, documentar e justificar com dado primário. |

Emitir alerta quando:
- `FCFF ≠ NOPAT + D&A – CAPEX_total – ΔWC` → ❗
- `CAPEX_total ≠ CAPEX_exp + CAPEX_man` → ❗
- `Soma segmentos ≠ Consolidado` (tolerância: R$ 1 mi ou 0,1 pp) → ❗
- `g > IPCA + 1%` sem justificativa → 🟠
- `TV/EV > 75%` → 🟠 (checar sanity do valor terminal)
- Fonte única sem confirmação → 🟠

---

## 3. Conservadorismo > Otimismo

- Margem de segurança empírica sempre
- Default: haircut de **10–15% em guidance de receita/margem**
- Default: **+30–50% em timeline de projetos** (base rate: só 35% dos projetos entregam on-time)
- Cenário Base = 100%. Nunca "chutar para cima" sem evidência

---

## 4. Haircut de Management

**Nunca usar guidance corporativo sem descontar pelo track record histórico.**

Protocolo:
1. Levantar guidances dos últimos 5–10 anos
2. Calcular % de acerto (receita, margem, capex, timeline)
3. Gerar Score de Credibilidade (1–5) e % de Haircut correspondente
4. Aplicar haircut sistematicamente em toda premissa forward-looking

| Score | Track Record | Haircut Recomendado |
|-------|-------------|-------------------|
| 5 | > 90% acerto | 0–5% |
| 4 | 75–90% acerto | 5–10% |
| 3 | 60–75% acerto | 10–15% |
| 2 | 40–60% acerto | 15–25% |
| 1 | < 40% acerto | 25–40% |

---

## 5. Justificativa Rigorosa

Cada premissa deve citar:
- Fonte bibliográfica ou base rate empírica, **ou**
- Dado oficial (ITR/DFP/RI da empresa), **ou**
- Regressão com metodologia descrita (1º/2º/3º nível)

Premissas sem justificativa → classificar como "Atenção" na tabela herdada.

---

## 6. Prior Bayesiano (base rate como ponto de partida)

**Partir sempre da média do setor como prior. Ajustar pela evidência da empresa.**

```
P(H|E) = P(E|H) × P(H) / P(E)
```

- Consultar `references/base-rates.md` antes de definir qualquer premissa de ROIC, margem ou fade
- Só desviar da mediana setorial com evidência marginal explícita e documentada
- Documentar o quanto a empresa se afasta do prior e por quê

---

## 7. Outside View antes de Inside View (Tetlock)

1. **Base rates primeiro**: qual a taxa base de sucesso de empresas nessa situação?
2. **Inside view depois**: o que torna esta empresa diferente?
3. Anchor na estatística histórica, ajuste para o caso específico com evidência

---

## 8. Hierarquia de Dados

| Prioridade | Fonte | Uso |
|-----------|-------|-----|
| 1 (MÁXIMA) | ITR/DFP oficiais da CVM + RI da empresa | DRE, BP, DFC |
| 2 | StatusInvest, Economatica, Morningstar | Histórico > 10 anos |
| 3 | yfinance / Yahoo Finance | Cotações, beta, volume |
| 4 | Estimativas por regressão | Quando dados oficiais ausentes |

> **NUNCA** usar dados de agregadores como fonte primária para DRE, BP ou DFC. Sempre validar contra ITR/DFP oficial.

---

## 9. Regra Red Queen (Capex Manutenção)

Separar obrigatoriamente:
- **CAPEX_exp**: investimento em crescimento (novos projetos, expansão)
- **CAPEX_man**: investimento para manter capacidade atual (Red Queen — correr para ficar no lugar)

Teste: `PP&E líquido / PP&E bruto < 0,4` → 🟠 Sub-investimento em manutenção

```
FCFF real = NOPAT + D&A – CAPEX_exp – CAPEX_man – ΔWC
```

---

## 10. Consistência g × ROIIC

```
g = ROIIC × Taxa de Reinvestimento
```

Se g calculado ≠ g projetado com diferença > 1 pp → ❗ Inconsistência interna
