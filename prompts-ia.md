# Prompts de IA Generativa utilizados

Este arquivo registra, de forma transparente, como a **IA Generativa (LLM)** apoiou a construção dos
artefatos deste repositório. A IA foi usada como **acelerador de estruturação e redação**; a
**classificação, a priorização e o julgamento final foram feitos por revisão humana**.

Os prompts seguem a estrutura **Persona · Tarefa · Contexto · Formato de saída · Restrições**, que
tende a produzir respostas mais direcionadas e menos genéricas.

---

## 1. Identificação de riscos

> **Persona:** Você é um gerente de projetos de software experiente em produtos de saúde.
> **Tarefa:** Liste os riscos de um projeto, no formato *causa → evento → consequência*.
> **Contexto:** App móvel de agendamento de consultas médicas, em fase intermediária, equipe de 4 devs + 1 tester, integração instável e mal documentada com um sistema de prontuário externo, mudanças frequentes de requisitos e tratamento de dados sensíveis de saúde (LGPD).
> **Formato:** Tabela com ID, categoria e descrição.
> **Restrições:** Riscos específicos deste cenário; não repita o mesmo risco com outras palavras; separe o risco (evento incerto) da sua consequência.

## 2. Análise qualitativa (probabilidade × impacto)

> **Tarefa:** Proponha notas de probabilidade e impacto (escala 1–5) para os riscos abaixo e explique o raciocínio de cada nota.
> **Contexto:** [lista de riscos do artefato 01].
> **Restrições:** As notas são uma **sugestão inicial para eu validar** — justifique cada uma; não invente dados quantitativos que o cenário não fornece.

*(As notas sugeridas foram revisadas e ajustadas manualmente antes de entrar no artefato 02.)*

## 3. Estratégias de resposta

> **Tarefa:** Para cada risco, indique a estratégia de resposta (evitar, mitigar, transferir ou aceitar), as ações práticas e um plano de contingência quando fizer sentido.
> **Contexto:** [riscos priorizados].
> **Restrições:** Ações concretas e aplicáveis à realidade de uma equipe pequena; destaque a resposta de maior efeito alavancado.

## 4. Comunicação com stakeholders

> **Tarefa:** Monte um plano de comunicação de riscos por stakeholder, com o quê comunicar, frequência, canal e responsável, e escreva um modelo de comunicação para um risco crítico.
> **Contexto:** [stakeholders do projeto].
> **Restrições:** Adapte a linguagem ao público (diretoria x equipe técnica); comunicar risco sempre acompanhado de ação, sem alarmismo.

## 5. Resumo executivo

> **Tarefa:** Escreva um resumo executivo de uma página para o patrocinador, com panorama, top riscos, estratégia central e decisões solicitadas.
> **Restrições:** Linguagem de negócio, objetiva; foco em decisão, não em detalhe técnico.

---

## Limitações e cuidados percebidos no uso da IA

- **Generalização:** sem um contexto rico, a IA tende a devolver riscos genéricos ("riscos comuns de software"). Foi necessário **filtrar e contextualizar** para o cenário de saúde.
- **Classificação exige validação humana:** as notas de probabilidade/impacto sugeridas pela IA foram **revisadas e ajustadas** — essa priorização não pode ser delegada.
- **Risco de alucinação:** a IA pode sugerir termos, normas ou ações que não se aplicam; tudo passou por **conferência**.
- **Dados sensíveis:** por envolver saúde, **nenhum dado real de paciente foi inserido em ferramenta externa** — o cenário é fictício/didático.
- **A decisão continua humana:** a IA acelerou estruturação e redação, mas **julgamento, priorização e responsabilidade permaneceram da equipe**.
