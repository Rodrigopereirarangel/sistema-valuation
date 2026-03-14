# Sistema de Valuation Integrado — DFC para Ações BR

Sistema de análise de **Fluxo de Caixa Descontado (FCFF)** para ações da B3, baseado nos princípios de Munger, Buffett, Mauboussin, Lynch e Damodaran.

## Objetivo

Executar valuation rigoroso de ações brasileiras usando FCFF descontado a WACC dinâmica, com:
- WACC dinâmica pela curva (NTN-B, IPCA, D/EBITDA anual)
- Projeção explícita 2025–2034 com ramp-up logístico
- Fade de ROIC → WACC + 0,5% no período terminal
- Auditoria 360° aritmética e cross-segmento

## Estrutura do Projeto

```
sistema-valuation/
├── CLAUDE.md                  # Instruções de contexto para Claude
├── sistema_valuation.md       # Prompt consolidado do sistema (base do projeto)
├── blocos/
│   ├── bloco1-modelo-negocio.md
│   ├── bloco2-moat-concorrencia.md
│   ├── bloco3a-reinvestimento.md
│   ├── bloco3b-custo-capital.md
│   ├── bloco3c-auditoria360.md
│   └── bloco5-valuation-preco-alvo.md
└── referencias/
    ├── parametros-tecnicos.md
    └── regras-globais.md
```

## Metodologia

| Componente | Abordagem |
|---|---|
| Modelo | FCFF descontado a WACC dinâmica |
| Crescimento | Projeção explícita 2025–2034 com ramp-up logístico |
| WACC | Dinâmica: NTN-B curva + IPCA + D/EBITDA + Beta realavancado |
| Terminal | Fade ROIC → WACC + 0,5% · g real ≤ PIB potencial |
| Auditoria | 360°: FCFF = NOPAT + D&A – CAPEX_total – ΔWC |
| Cenário | Sempre Base (sem otimismo ou pessimismo extremo) |

## Como Usar como Referência no Claude

1. Adicione a URL deste repositório como referência no seu **Claude Project**
2. O arquivo [CLAUDE.md](CLAUDE.md) contém o contexto principal do sistema
3. O arquivo [sistema_valuation.md](sistema_valuation.md) contém o prompt consolidado completo

## Filosofia

> "Pense devagar, sempre reconfirme os cálculos e variáveis. Priorize qualidade > velocidade."

Inspirado em:
- **Charlie Munger** — clareza mental, antifragilidade
- **Warren Buffett** — negócio compreensível, gestão de qualidade
- **Michael Mauboussin** — análise probabilística, valor esperado, fade de retornos
- **Peter Lynch** — GARP, simplicidade de tese
- **Aswath Damodaran** — rigor técnico em FCFF, coerência matemática

## Parâmetros LLM Recomendados

```json
{
  "temperature": 0.2,
  "top_p": 0.35,
  "frequency_penalty": 0.3,
  "max_tokens": 1500
}
```
