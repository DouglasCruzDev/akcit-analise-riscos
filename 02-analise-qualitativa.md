# 02 — Análise Qualitativa dos Riscos

Avaliação de cada risco por **Probabilidade** e **Impacto**, com cálculo da **Exposição**
(`Probabilidade × Impacto`) e priorização. A análise é **qualitativa**: as notas refletem o
julgamento da equipe sobre o cenário, e não uma medição estatística.

---

## Escalas utilizadas

### Probabilidade (chance de o risco se concretizar)

| Nota | Nível | Referência |
|:---:|---|---|
| 1 | Muito baixa | Improvável no horizonte do projeto |
| 2 | Baixa | Pode ocorrer, mas não é esperado |
| 3 | Média | Tão provável quanto improvável |
| 4 | Alta | Esperado que ocorra |
| 5 | Muito alta | Quase certo / já ocorrendo |

### Impacto (efeito sobre prazo, custo, qualidade, conformidade ou reputação)

| Nota | Nível | Referência |
|:---:|---|---|
| 1 | Muito baixo | Efeito desprezível, absorvido sem esforço |
| 2 | Baixo | Pequeno ajuste de plano |
| 3 | Médio | Atraso/retrabalho perceptível, contornável |
| 4 | Alto | Compromete entrega, custo ou qualidade de forma relevante |
| 5 | Muito alto | Ameaça a viabilidade do projeto ou gera dano legal/reputacional grave |

### Faixas de exposição

| Exposição | Classificação | Postura |
|:---:|---|---|
| 🟩 1 – 5 | Baixo | Monitorar |
| 🟨 6 – 12 | Médio | Tratar com plano de ação |
| 🟧 13 – 19 | Alto | Tratar com prioridade |
| 🟥 20 – 25 | Crítico | Ação imediata e acompanhamento próximo |

---

## Avaliação dos riscos

| ID | Risco | Prob. | Impacto | Exposição | Classificação |
|---|---|:---:|:---:|:---:|:---:|
| R01 | Instabilidade na integração com o prontuário | 4 | 5 | **20** | 🟥 Crítico |
| R03 | Atraso por mudanças de requisitos (*scope creep*) | 4 | 4 | **16** | 🟧 Alto |
| R04 | Sobrecarga e esgotamento da equipe | 4 | 4 | **16** | 🟧 Alto |
| R02 | Exposição de dados sensíveis de saúde (LGPD) | 3 | 5 | **15** | 🟧 Alto |
| R05 | Cobertura de testes insuficiente | 4 | 3 | **12** | 🟨 Médio |
| R06 | Dependência de fornecedor externo | 3 | 4 | **12** | 🟨 Médio |
| R07 | Concentração de conhecimento (*bus factor*) | 3 | 4 | **12** | 🟨 Médio |
| R08 | Baixa adoção por usabilidade/acessibilidade | 3 | 3 | **9** | 🟨 Médio |

> **Observação:** R05 (testes) tem exposição média isolada, mas funciona como **amplificador** de
> R01 e R02 — falhas de qualidade aumentam a chance de defeitos de integração e de exposição de
> dados chegarem à produção. Por isso é tratado com prioridade acima da sua nota isolada.

---

## Matriz de Riscos (Probabilidade × Impacto)

Posição de cada risco na matriz 5×5. Linhas = Impacto (5 no topo), colunas = Probabilidade.

| Impacto ↓ / Prob. → | **1** | **2** | **3** | **4** | **5** |
|---|:---:|:---:|:---:|:---:|:---:|
| **5 — Muito alto** | 🟨 | 🟧 | 🟧 **R02** | 🟥 **R01** | 🟥 |
| **4 — Alto** | 🟩 | 🟨 | 🟨 **R06 · R07** | 🟧 **R03 · R04** | 🟥 |
| **3 — Médio** | 🟩 | 🟨 | 🟨 **R08** | 🟨 **R05** | 🟧 |
| **2 — Baixo** | 🟩 | 🟩 | 🟨 | 🟨 | 🟧 |
| **1 — Muito baixo** | 🟩 | 🟩 | 🟩 | 🟨 | 🟨 |

---

## Priorização (ordem de tratamento)

1. **R01 — Integração com o prontuário** 🟥 *Crítico* → ação imediata.
2. **R03 — Scope creep** 🟧 *Alto*
3. **R04 — Burnout da equipe** 🟧 *Alto*
4. **R02 — LGPD / dados de saúde** 🟧 *Alto* (impacto máximo; prioridade absoluta em conformidade).
5. **R05 — Cobertura de testes** 🟨 *Médio* (amplificador — tratar junto de R01/R02).
6. **R06 — Fornecedor externo** 🟨 *Médio*
7. **R07 — Bus factor** 🟨 *Médio*
8. **R08 — Adoção/usabilidade** 🟨 *Médio*

➡️ O plano de tratamento de cada risco está em
[03 — Estratégias de Resposta](03-estrategias-de-resposta.md).
