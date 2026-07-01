# Contexto Técnico Lite - Etapa 2 (PoC)

## 1. Escopo de Testes da PoC (O que foi testado)
Para validar a viabilidade técnica da solução para a ClearIT de forma isolada e segura, focamos em testar a Engenharia de Prompts para duas funções críticas:
1. **Estruturação de Feedbacks no Modelo SBI** (Situação, Comportamento, Impacto).
2. **Geração Baseada no Framework de Levels** (Geração de pautas personalizadas).

Conforme as restrições de riscos mapeadas, todos os testes foram realizados utilizando **dados 100% fictícios**, garantindo conformidade com a LGPD.

## 2. Tecnologias Avaliadas
* **Modelos de Linguagem (LLMs):** Utilizados para simular o motor de IA do aplicativo (Engenharia de Prompts).
* **Ambiente de Teste:** Interface de chat para validação manual de respostas (Human-in-the-loop).

## 3. Engenharia de Prompts e Resultados (Evidências)

### Teste 1: Formatador SBI Inteligente
* **Prompt Utilizado:**
  > "Abaixe o papel de assistente de RH. Pegue o texto informal de um líder e transforme estritamente na estrutura SBI (Situação, Comportamento e Impacto). Se houver dados pessoais sensíveis ou linguagem tóxica, remova e avise."
* **Input de Teste (Líder Fictício):** 
  > "O Joãozinho foi super grosso na reunião com o cliente ontem de tarde, interrompeu o cara duas vezes e o cliente ficou visivelmente incomodado, quase melou o projeto."
* **Output da IA (Resultado Esperado):**
  * **Situação:** Reunião com o cliente ontem à tarde.
  * **Comportamento:** O colaborador interrompeu a fala do cliente duas vezes.
  * **Impacto:** O cliente demonstrou desconforto, colocando em risco a confiança no projeto.

### Teste 2: Gerador de Pauta (Framework de Levels)
* **Prompt Utilizado:**
  > "Gere 2 perguntas de desenvolvimento focadas em carreira para um desenvolvedor Júnior que precisa evoluir na competência de 'Comunicação com Stakeholders' para chegar a Pleno."
* **Output da IA:** 
  1. *Como você avalia sua clareza ao explicar impedimentos técnicos para o cliente nas últimas sprints?*
  2. *Que apoio você precisa para liderar a próxima apresentação de status sem depender do seu coordenador?*

## 4. Alinhamento com os Resultados Esperados e Próximos Passos
Os testes provaram que a IA consegue traduzir linguagem informal em estruturas profissionais (SBI) e aplicar as regras de negócio do RH sem a necessidade de desenvolvimento de código complexo nesta fase. 

**Escopo Pretendido para o MVP:**
* Interface Web simples (Acesso fácil via browser para mobile/desktop).
* Campo de texto/áudio para o líder inserir as notas da reunião.
* Tela de visualização e edição do relatório SBI gerado pela IA antes de salvar.
* Exportação dos dados consolidados em formato CSV/Excel para envio ao RH.
