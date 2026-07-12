# 03 — Estratégias de Resposta aos Riscos

Plano de tratamento de cada risco. Para ameaças, consideramos as respostas clássicas:
**Evitar**, **Mitigar** (reduzir probabilidade e/ou impacto), **Transferir** (repassar a terceiro,
ex.: contrato/seguro) e **Aceitar** (assumir o risco, com ou sem reserva de contingência). Quando
cabível, registramos também o **plano de contingência** — o que fazer *se* o risco se concretizar.

---

## R01 — Instabilidade na integração com o prontuário 🟥 Crítico
**Estratégia principal: Mitigar** (é a de maior efeito alavancado — estabiliza a dependência mais crítica do produto).

- **Camada de abstração / anticorrupção** entre o app e a API de prontuário, isolando o restante do sistema de mudanças externas.
- **Testes de contrato (*contract testing*) e mocks** para detectar quebras da API externa antes que cheguem à produção.
- **Comunicação recorrente** com o time responsável pelo prontuário; **documentação interna** dos endpoints e comportamentos observados.
- **Resiliência:** *retry* com *backoff*, *fallback* e **fila assíncrona** para operações críticas de escrita.
- **Ambiente de homologação estável** para validar a integração de forma contínua.
- **Contingência:** modo degradado — permitir o agendamento localmente e **sincronizar quando a integração voltar**, comunicando o paciente sobre a confirmação pendente.

## R02 — Exposição de dados sensíveis de saúde (LGPD) 🟧 Alto
**Estratégia principal: Mitigar + Transferir**

- **Mitigar:** criptografia em trânsito e em repouso; **minimização de dados** (coletar só o necessário); controle de acesso por perfil (RBAC); **logs de auditoria**; anonimização/mascaramento em ambientes de teste; base legal e consentimento adequados.
- **Evitar:** não coletar nem armazenar dado sensível que não seja essencial ao agendamento.
- **Transferir:** cláusulas contratuais de proteção de dados com o fornecedor e avaliação de **seguro cibernético** para o risco residual.
- **Governança:** envolver **DPO/Jurídico**, registrar operações de tratamento (RoPA) e ter um plano de resposta a incidentes.
- **Contingência:** plano de resposta a incidente de dados — conter, avaliar, **notificar ANPD e titulares** nos prazos legais e registrar lições aprendidas.

## R03 — Atraso por mudanças de requisitos (*scope creep*) 🟧 Alto
**Estratégia principal: Mitigar**

- **Baseline de escopo** acordada e **processo formal de controle de mudanças** (toda mudança passa por avaliação de impacto em prazo/custo antes de entrar).
- **Priorização por valor** (ex.: MoSCoW) e **escopo congelado por sprint**.
- Distinguir claramente *must-have* de *nice-to-have* junto ao Product Owner e ao cliente.
- **Contingência:** repactuar prazo/escopo do próximo marco caso a mudança seja indispensável.

## R04 — Sobrecarga e esgotamento da equipe 🟧 Alto
**Estratégia principal: Mitigar**

- **Cronograma realista** e limite de **trabalho em progresso (WIP)** por pessoa.
- **Proteger a equipe** de interrupções e redistribuir carga; priorizar o essencial.
- Reforço temporário (contratação/realocação) nos picos; acompanhamento de sinais em **1:1s**.
- **Contingência:** replanejar entregas e negociar prazo antes que a sobrecarga vire perda de pessoas.

## R05 — Cobertura de testes insuficiente 🟨 Médio (amplificador)
**Estratégia principal: Mitigar**

- **Automação de testes** (pirâmide de testes) integrada ao CI, com **gate de qualidade** antes do merge.
- **Qualidade é responsabilidade de todos:** devs escrevem testes; QA foca em estratégia, exploratório e casos críticos.
- **Critérios de aceite claros** por história; testes de contrato compartilhados com R01.
- **Transferir/ampliar capacidade:** avaliar reforço de QA ou terceirização de testes em fases críticas.

## R06 — Dependência de fornecedor externo 🟨 Médio
**Estratégia principal: Transferir + Mitigar**

- **SLA formal** e cláusulas contratuais de disponibilidade, suporte e comunicação de mudanças.
- **Monitoramento** de disponibilidade e desempenho do serviço externo, com alertas.
- **Plano de saída/alternativa** mapeado (fornecedor ou abordagem substituta).
- **Aceitar** o risco residual que estiver fora do controle do projeto, de forma consciente e documentada.

## R07 — Concentração de conhecimento (*bus factor*) 🟨 Médio
**Estratégia principal: Mitigar**

- **Documentação** viva dos módulos e decisões; **pair programming** e **revisão de código**.
- **Rotação de tarefas** para reduzir silos de conhecimento.
- Evitar que um módulo crítico tenha uma única pessoa capaz de mantê-lo.

## R08 — Baixa adoção por usabilidade/acessibilidade 🟨 Médio
**Estratégia principal: Mitigar**

- **Testes de usabilidade** com usuários reais, incluindo pessoas idosas e com baixa familiaridade digital.
- **Acessibilidade** (diretrizes WCAG), *onboarding* simples e linguagem clara.
- **Canal de suporte** e coleta contínua de feedback; iteração baseada em métricas de abandono do fluxo.

---

## Quadro-síntese das respostas

| ID | Risco | Estratégia | Responsável |
|---|---|---|---|
| R01 | Integração com o prontuário | Mitigar (+ contingência em modo degradado) | Tech Lead |
| R02 | Dados de saúde / LGPD | Mitigar + Transferir | Tech Lead + DPO |
| R03 | Scope creep | Mitigar (controle de mudanças) | PO / GP |
| R04 | Burnout da equipe | Mitigar | Gerente de Projeto |
| R05 | Cobertura de testes | Mitigar | QA + Tech Lead |
| R06 | Fornecedor externo | Transferir + Mitigar + Aceitar residual | Gerente de Projeto |
| R07 | Bus factor | Mitigar | Tech Lead |
| R08 | Adoção / usabilidade | Mitigar | PO / UX |

➡️ Como esses riscos e ações são comunicados a cada público está em
[04 — Comunicação com Stakeholders](04-comunicacao-stakeholders.md).
