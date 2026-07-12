# 01 — Identificação de Riscos

Registro de riscos (*risk register*) do projeto do aplicativo de agendamento de consultas médicas.
Cada risco é descrito no formato **Causa → Evento (risco) → Consequência**, o que evita confundir o
risco com o seu efeito e facilita a definição da resposta.

> **Convenção de escrita:** *Devido a* **[causa]**, *pode ocorrer* **[evento incerto]**, *o que levaria a* **[consequência]**.

---

## Registro de riscos

### R01 — Instabilidade na integração com o sistema de prontuário
- **Categoria:** Técnico / Integração
- **Descrição:** Devido à **API externa de prontuário mal documentada e sujeita a mudanças sem aviso prévio**, pode ocorrer **falha ou comportamento inesperado na comunicação entre o app e o prontuário**, o que levaria a **agendamentos inconsistentes, indisponibilidade de funcionalidades centrais e retrabalho**.
- **Gatilho (sinal de alerta):** aumento de erros de API em log, respostas fora do contrato esperado, mudança anunciada pelo time do prontuário.
- **Responsável:** Tech Lead

### R02 — Exposição de dados sensíveis de saúde (LGPD)
- **Categoria:** Segurança / Conformidade / Legal
- **Descrição:** Devido ao **tratamento de dados sensíveis de saúde sem todos os controles de proteção maduros**, pode ocorrer **acesso indevido, vazamento ou uso inadequado desses dados**, o que levaria a **sanções da LGPD, dano à reputação e perda de confiança dos pacientes**.
- **Gatilho:** achado em pentest/auditoria, acesso sem controle de perfil, ausência de criptografia em algum fluxo.
- **Responsável:** Tech Lead + DPO/Jurídico

### R03 — Atraso no cronograma por mudanças frequentes de requisitos (*scope creep*)
- **Categoria:** Gestão / Escopo
- **Descrição:** Devido à **ausência de um escopo estável e de um processo formal de controle de mudanças no fluxo de agendamento**, pode ocorrer **inclusão contínua de novas exigências durante o desenvolvimento**, o que levaria a **retrabalho, desvio de cronograma e desgaste da equipe**.
- **Gatilho:** novas solicitações fora da sprint, replanejamentos recorrentes, backlog crescendo mais rápido do que é entregue.
- **Responsável:** Product Owner / Gerente de Projeto

### R04 — Sobrecarga e esgotamento (*burnout*) da equipe
- **Categoria:** Recursos Humanos / Gestão
- **Descrição:** Devido à **equipe pequena (4 devs + 1 tester) sob pressão de prazo e acúmulo de frentes**, pode ocorrer **sobrecarga e esgotamento das pessoas**, o que levaria a **queda de produtividade, aumento de erros e risco de perda de integrantes**.
- **Gatilho:** horas extras recorrentes, aumento de bugs, atrasos, sinais de desmotivação em 1:1s.
- **Responsável:** Gerente de Projeto

### R05 — Cobertura de testes insuficiente (gargalo de QA)
- **Categoria:** Qualidade
- **Descrição:** Devido à **dependência de um único tester e à pressão por entregas**, pode ocorrer **cobertura de testes insuficiente**, o que levaria a **defeitos chegando à produção em um sistema de saúde, onde falhas têm baixa tolerância**.
- **Gatilho:** fila de testes acumulada, defeitos encontrados só em produção, ausência de testes automatizados.
- **Responsável:** QA + Tech Lead

### R06 — Dependência de fornecedor externo
- **Categoria:** Externo / Fornecedor
- **Descrição:** Devido à **dependência de um fornecedor/terceiro que mantém o prontuário e outros serviços**, pode ocorrer **indisponibilidade, mudança de contrato ou descontinuidade do serviço**, o que levaria a **bloqueio de funcionalidades e ausência de plano B**.
- **Gatilho:** quebra de SLA, aviso de mudança contratual, instabilidade recorrente do serviço externo.
- **Responsável:** Gerente de Projeto

### R07 — Concentração de conhecimento (*bus factor*)
- **Categoria:** Recursos Humanos / Conhecimento
- **Descrição:** Devido à **equipe pequena com conhecimento concentrado em poucas pessoas e pouca documentação**, pode ocorrer **saída ou ausência de um integrante-chave**, o que levaria a **paralisação de partes do projeto e dificuldade de continuidade**.
- **Gatilho:** apenas uma pessoa domina um módulo, ausência de documentação, férias/afastamento sem cobertura.
- **Responsável:** Tech Lead

### R08 — Baixa adoção por problemas de usabilidade/acessibilidade
- **Categoria:** Produto / Negócio
- **Descrição:** Devido a um **público amplo e diverso de pacientes (incluindo pessoas idosas e com baixa familiaridade digital)**, pode ocorrer **dificuldade de uso do aplicativo**, o que levaria a **baixa adoção, sobrecarga dos canais tradicionais (telefone/balcão) e não atingimento dos objetivos do produto**.
- **Gatilho:** alto abandono no fluxo de agendamento, chamados de suporte, avaliações negativas nas lojas.
- **Responsável:** Product Owner / UX

---

## Resumo dos riscos identificados

| ID | Risco | Categoria |
|---|---|---|
| R01 | Instabilidade na integração com o prontuário | Técnico / Integração |
| R02 | Exposição de dados sensíveis de saúde (LGPD) | Segurança / Legal |
| R03 | Atraso por mudanças de requisitos (*scope creep*) | Gestão / Escopo |
| R04 | Sobrecarga e esgotamento da equipe | RH / Gestão |
| R05 | Cobertura de testes insuficiente | Qualidade |
| R06 | Dependência de fornecedor externo | Externo / Fornecedor |
| R07 | Concentração de conhecimento (*bus factor*) | RH / Conhecimento |
| R08 | Baixa adoção por usabilidade/acessibilidade | Produto / Negócio |

➡️ A avaliação de probabilidade, impacto e prioridade de cada risco está em
[02 — Análise Qualitativa](02-analise-qualitativa.md).
