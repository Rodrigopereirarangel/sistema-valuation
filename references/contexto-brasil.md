# Contexto Brasil — Adaptações para o Mercado Brasileiro

---

## Taxa Livre de Risco

- **NTN-B** (Tesouro IPCA+) como proxy de taxa real livre de risco
- Usar a NTN-B com vencimento **igual ou superior** ao ano projetado (curva, não ponto)
- Para valor terminal: NTN-B +10
- **Selic**: âncora de custo de oportunidade para investidor doméstico
- Fonte: Tesouro Direto (tesourodireto.gov.br) ou Anbima

---

## Country Risk Premium (CRP)

- **EMBI+** Brasil ou CDS Brasil (5 anos) como proxy de risco-país
- Fonte: JPMorgan (EMBI+) ou Bloomberg/Damodaran (CDS)
- Damodaran atualiza CRP anualmente em damodaran.com (tabela por país)
- CRP Brasil histórico: 1,5–4,5% dependendo do ciclo político/fiscal

---

## Inflação

| Índice | Uso |
|--------|-----|
| IPCA | Custos salariais, deflator de receita real, taxa real no WACC |
| IGP-M | Contratos indexados, aluguéis, alguns insumos industriais |
| INCC | Construção civil |

**WACC nominal vs. real:**
- Projetar em termos nominais (moeda corrente) com WACC nominal
- `WACC_real = (1 + WACC_nominal) / (1 + IPCA) − 1`
- Calcular WACC real dinamico sempre

---

## Tributação

| Item | Alíquota |
|------|---------|
| IR + CSLL | 34% (nominal) |
| JCP (Juros sobre Capital Próprio) | Dedutível da base de IR/CSLL → reduz custo efetivo do equity |
| Dividendos | Isentos para PF (atenção a mudanças legislativas) |
| Cash Tax Rate efetivo | Calcular: IR pago / EBT (histórico 5 anos, excluindo não-recorrentes) |

> **ATENÇÃO:** Sempre usar Cash Tax Rate efetivo (real), não a alíquota nominal de 34%.

---

## IFRS 16 — Leases

- IFRS 16 entrou em vigor no Brasil em 2019 (ITRs a partir de 2019 já refletem)
- Ajustar comparabilidade ao analisar histórico pré/pós 2019
- Separar ROU assets e passivos de arrendamento ao calcular Invested Capital
- Incluir D&A de ROU e juros de leasing ao construir NOPAT e FCFF ajustados

---

## Fontes de Dados

| Fonte | Uso | Prioridade |
|-------|-----|-----------|
| CVM — ITR/DFP | Financeiros oficiais | 1 (MÁXIMA) |
| RI da empresa | Apresentações, press releases, guidance | 1 |
| B3 | Dados de mercado, estrutura acionária | 2 |
| Economatica / Refinitiv | Histórico longo (> 10 anos) | 2 |
| StatusInvest / Fundamentei | Verificação rápida, screening | 3 |
| yfinance | Cotações live, beta, volume | 3 |
| Damodaran Online | Beta setorial, ERP, base rates globais | 2 |

---

## Governança

| Segmento B3 | Características |
|-------------|----------------|
| Novo Mercado | Apenas ON; tag along 100%; mínimo 25% free float |
| Nível 2 | ON e PN; tag along 100% ON, 100% PN |
| Nível 1 | Mínimo 25% free float; algumas restrições |
| Bovespa Mais | PMEs; menos liquidez |
| Básico | Regras mínimas da CVM |

**Implicação**: Desconto de governança 5–20% para empresas fora do Novo Mercado com estrutura dual class ou controlling family.

---

## Câmbio

- Empresas exportadoras (commodities, agro): exposição cambial positiva em receita
- Importadoras ou com dívida USD: exposição cambial negativa em custos/serviço da dívida
- Hedge natural: avaliar se a empresa exporta e tem dívida em USD (offsetting)
- Fonte: B3 (futuro dólar), Banco Central (ptax oficial)

---

## Curva de Juros Brasileira

> **❗ REGRA INVIOLÁVEL — NTN-B:** Usar EXCLUSIVAMENTE as taxas publicadas pelo ANBIMA para cada vencimento específico. PROIBIDO aproximar, estimar, arredondar ou interpolar sem mostrar cálculo explícito.

Para WACC dinâmico por ano:
1. Acessar ANBIMA → Mercados → Taxas de Referência → Títulos Públicos → NTN-B
2. Baixar a tabela de vencimentos do dia da análise (registrar data)
3. Para cada ano projetado, usar a NTN-B com vencimento **igual ou imediatamente superior**
4. Se interpolação necessária: `Rf_ano = Rf_A + (Rf_B − Rf_A) × (ano − venc_A) / (venc_B − venc_A)` — mostrar valores
5. Ajustar Beta e D/EBITDA para cada ano (nunca constante)
6. Recalcular WACC para cada ano

**Fonte primária obrigatória:** ANBIMA — anbima.com.br > Mercados > Taxas de Referência
**Fonte alternativa (verificação):** Tesouro Direto — tesourodireto.gov.br > Consultar Taxas

**Vencimentos NTN-B disponíveis (referência típica — verificar sempre data atual):**
| Vencimento | Código | Periodicidade cupom |
|------------|--------|---------------------|
| 15/08/2026 | NTN-B | Semestral |
| 15/05/2027 | NTN-B | Semestral |
| 15/08/2028 | NTN-B | Semestral |
| 15/08/2030 | NTN-B | Semestral |
| 15/05/2035 | NTN-B | Semestral |
| 15/08/2040 | NTN-B | Semestral |
| 15/05/2045 | NTN-B | Semestral |
| 15/08/2050 | NTN-B | Semestral |
| 15/08/2055 | NTN-B | Semestral |

> Para o valor terminal: usar NTN-B com vencimento mais longo disponível (≥ 2045).

---

## Peers Maduros — Critérios para Cash-Sweep

Para definir D/EBITDA alvo e payout referência:
- ≥ 10 anos listados em bolsa (BR ou exterior)
- > 40% payout (dividendos + buybacks) nos últimos 3 anos
- Mesmo setor ou setor comparável
- Fontes: Economatica, Bloomberg, Damodaran (páginas setoriais)
