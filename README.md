# Análise de Riscos e Resumo Executivo — App de Agendamento de Consultas Médicas

Artefatos de **gestão de riscos e comunicação** produzidos para a atividade prática da unidade
de IA Generativa aplicada a projetos de software (AKCIT).

O trabalho utiliza o **estudo de caso proposto no curso**: um aplicativo móvel de agendamento de
consultas médicas, em fase intermediária de desenvolvimento, com integração instável ao sistema de
prontuário, mudanças frequentes de requisitos e uma equipe pequena sob pressão de prazo.

---

## Cenário (contexto do projeto)

| Item | Descrição |
|---|---|
| **Produto** | Aplicativo móvel para pacientes agendarem, remarcarem e cancelarem consultas médicas. |
| **Fase** | Intermediária (desenvolvimento ativo, com parte das funcionalidades já entregue). |
| **Equipe** | 4 pessoas desenvolvedoras + 1 pessoa de QA (tester). |
| **Integrações** | Sistema de prontuário eletrônico (API externa, mantida por terceiro/outra área). |
| **Dados tratados** | Dados pessoais e **dados sensíveis de saúde** (sujeitos à LGPD). |
| **Dores atuais** | Integração instável e mal documentada, escopo mudando com frequência, equipe sobrecarregada, gargalo de testes. |

---

## Como navegar por este repositório

Os artefatos seguem o fluxo clássico de gerenciamento de riscos: **identificar → analisar →
planejar respostas → comunicar → resumir para a decisão**.

| # | Artefato | O que contém |
|---|---|---|
| 01 | [Identificação de Riscos](01-identificacao-de-riscos.md) | Registro de riscos (risk register) com causa, evento e consequência. |
| 02 | [Análise Qualitativa](02-analise-qualitativa.md) | Escalas de probabilidade × impacto, matriz 5×5 e priorização. |
| 03 | [Estratégias de Resposta](03-estrategias-de-resposta.md) | Plano de tratamento de cada risco (mitigar, evitar, transferir, aceitar) + contingências. |
| 04 | [Comunicação com Stakeholders](04-comunicacao-stakeholders.md) | Plano de comunicação por público, canal e frequência. |
| 05 | [Resumo Executivo](05-resumo-executivo.md) | Visão de uma página para o patrocinador e a tomada de decisão. |
| — | [Prompts de IA utilizados](prompts-ia.md) | Prompts que apoiaram a construção dos artefatos (transparência de processo). |

---

## Método

A identificação e a estruturação dos riscos foram apoiadas por **IA Generativa** (LLM), usada como
acelerador para ampliar a lista de riscos, organizar a análise e padronizar a redação. A
**classificação de probabilidade/impacto, a priorização e o julgamento final foram validados
manualmente** — a IA não substituiu a decisão humana. O detalhamento desse processo, com os prompts
e as limitações percebidas, está em [`prompts-ia.md`](prompts-ia.md).

## Legenda de exposição ao risco

`Exposição = Probabilidade × Impacto` (escala 1 a 5 em cada eixo):

| Faixa | Classificação |
|---|---|
| 🟩 1 – 5 | Baixo |
| 🟨 6 – 12 | Médio |
| 🟧 13 – 19 | Alto |
| 🟥 20 – 25 | Crítico |
