# 05 — Resumo Executivo

**Projeto:** Aplicativo móvel de agendamento de consultas médicas
**Fase:** Intermediária (desenvolvimento) · **Equipe:** 4 devs + 1 QA
**Status geral de risco:** 🟡 **Atenção** — riscos gerenciáveis, mas um risco crítico exige ação imediata.

---

## Panorama

O projeto avança em fase intermediária, porém concentra riscos relevantes em **integração**,
**conformidade (LGPD)**, **escopo** e **capacidade da equipe**. Foram identificados **8 riscos**,
sendo **1 crítico**, **3 altos** e **4 médios**. A boa notícia: os riscos são conhecidos e há plano
de resposta para todos. A atenção principal recai sobre a integração com o sistema de prontuário,
que sustenta a funcionalidade central do produto.

## Riscos que exigem atenção da liderança

| Prioridade | Risco | Exposição | Resposta |
|:---:|---|:---:|---|
| 1 | **Integração instável com o prontuário** | 🟥 Crítico | Camada de abstração, testes de contrato, resiliência e modo degradado |
| 2 | **Mudanças frequentes de requisitos** | 🟧 Alto | Controle formal de mudanças e priorização por valor |
| 3 | **Sobrecarga da equipe** | 🟧 Alto | Cronograma realista, limite de WIP, reforço nos picos |
| 4 | **Dados sensíveis de saúde (LGPD)** | 🟧 Alto | Criptografia, mínimo necessário, RBAC, DPO e plano de incidente |

## Estratégia central recomendada

Concentrar esforço na **estabilização da integração com o prontuário (R01)**. É a resposta de
**maior efeito alavancado**: reduz de uma só vez a pressão sobre **prazo, esforço e qualidade**, por
ser a dependência mais crítica do produto. A abordagem combina **camada de abstração**, **testes de
contrato**, **resiliência (retry/fallback/fila assíncrona)** e um **modo degradado** de contingência
que mantém o agendamento funcionando mesmo com o serviço externo instável.

## Decisões solicitadas ao patrocinador

1. **Aprovar reforço temporário de QA** para sustentar a cobertura de testes durante a estabilização da integração.
2. **Referendar o processo de controle de mudanças** (congelamento de escopo por sprint) para conter o *scope creep*.
3. **Priorizar as ações de conformidade LGPD** com apoio de DPO/Jurídico antes do próximo marco.

## Indicadores a acompanhar

- Taxa de erros da integração com o prontuário (gatilho de R01).
- Volume de mudanças de escopo por sprint (gatilho de R03).
- Horas extras e defeitos em produção (gatilhos de R04 e R05).

---

*Documento de síntese. O detalhamento está nos artefatos [01](01-identificacao-de-riscos.md) a
[04](04-comunicacao-stakeholders.md) deste repositório.*
