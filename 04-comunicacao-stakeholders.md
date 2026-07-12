# 04 — Comunicação com Stakeholders

Plano de comunicação dos riscos. O princípio é **adaptar a mensagem ao público**: a diretoria quer
o essencial e a decisão; a equipe técnica quer o detalhe e a ação. A comunicação de riscos deve ser
**clara, no tempo certo e sem alarmismo nem omissão**.

---

## Mapa de stakeholders

| Stakeholder | Interesse principal | O que comunicar | Nível de detalhe |
|---|---|---|---|
| **Patrocinador / Diretoria** | Viabilidade, custo, prazo, reputação | Riscos críticos/altos, impacto no negócio, decisões necessárias | Alto nível (resumo executivo) |
| **Gerente de Projeto / PO** | Prazo, escopo, priorização | Registro de riscos completo e evolução | Detalhado |
| **Equipe de Desenvolvimento / QA** | Ações técnicas, execução | Riscos técnicos, tarefas de mitigação, gatilhos | Técnico e operacional |
| **Cliente / Área de negócio (clínica/hospital)** | Entrega e funcionamento | Riscos que afetam prazo, escopo ou operação | Médio, sem jargão técnico |
| **Time do sistema de prontuário (fornecedor/área)** | Integração e contratos | Riscos e necessidades de integração (R01, R06) | Técnico e contratual |
| **DPO / Jurídico** | Conformidade legal | Riscos de LGPD e dados sensíveis (R02) | Detalhado em conformidade |
| **Usuários finais (pacientes)** | Disponibilidade e confiança | Manutenções, indisponibilidades e uso de dados | Simples e objetivo |

---

## Plano de comunicação (o quê, quando, como)

| Público | Conteúdo | Frequência | Canal | Responsável |
|---|---|---|---|---|
| Patrocinador / Diretoria | Resumo executivo + top riscos + decisões pendentes | Mensal (ou ao surgir risco crítico) | Reunião de status + e-mail | Gerente de Projeto |
| Gerente de Projeto / PO | Registro de riscos e status das ações | Quinzenal | Reunião de acompanhamento | Tech Lead |
| Equipe Dev / QA | Riscos técnicos, tarefas e gatilhos | Diário/Semanal | Daily + quadro (board) | Tech Lead |
| Cliente / Negócio | Riscos que afetam prazo/escopo/operação | Quinzenal | Reunião + relatório | Gerente de Projeto / PO |
| Time do prontuário | Riscos de integração (R01) e SLA (R06) | Semanal / sob demanda | Reunião técnica + canal direto | Tech Lead |
| DPO / Jurídico | Riscos de LGPD (R02) e conformidade | Sob demanda / marcos | Reunião + parecer | Tech Lead + DPO |
| Usuários finais | Manutenções, indisponibilidades, política de dados | Sob demanda / quando necessário | Notificação no app + aviso | PO / Suporte |

---

## Diretrizes de comunicação de risco

- **Transparência responsável:** comunicar o risco e **junto a ação/plano**, para informar sem gerar pânico.
- **Priorizar o relevante:** para a diretoria, poucos riscos que realmente importam; não afogar a decisão em detalhe.
- **Gatilhos definem urgência:** ao sinal de alerta (gatilho) de um risco crítico, comunicar **fora do calendário regular**.
- **Registro único e rastreável:** o registro de riscos é a fonte da verdade; todas as comunicações derivam dele.
- **Escalonamento:** riscos que ultrapassam a alçada da equipe são **escalados** ao patrocinador com recomendação de decisão.

---

## Modelo de comunicação de risco crítico (exemplo — R01)

> **Assunto:** [ATENÇÃO] Risco crítico de integração pode afetar o marco de agosto
>
> **Para:** Patrocinador · **Cc:** Gerência de Projeto
>
> **Situação:** a integração com o sistema de prontuário apresentou instabilidade recorrente na última semana (gatilho: aumento de erros de API), colocando em risco a confiabilidade do agendamento.
>
> **Impacto:** possível atraso no marco de agosto e agendamentos inconsistentes.
>
> **Ação em curso:** camada de abstração + testes de contrato + fila assíncrona; alinhamento agendado com o time do prontuário.
>
> **Decisão necessária:** aprovar 1 semana adicional de reforço de QA **ou** liberar o marco em **modo degradado** (agendamento com confirmação assíncrona).

➡️ A visão consolidada para a decisão está em [05 — Resumo Executivo](05-resumo-executivo.md).
