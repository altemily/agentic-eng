# Resultados — Lab 01

Este arquivo registra os resultados dos experimentos realizados no laboratório de padrões de prompt.

Os testes foram executados no mesmo modelo e avaliados com critérios consistentes para observar como mudanças na estrutura do prompt influenciam a resposta gerada.

## Configuração dos testes

* **Modelo utilizado:** GPT-5.5 Thinking
* **Provedor ou plataforma:** OpenAI
* **Data de execução:** 15 de junho de 2026
* **Interface ou API:** ChatGPT Web
* **Temperatura:** não informada
* **Outras configurações:** configurações padrão da interface
* **Idioma das respostas:** português

## Procedimento

Para manter os testes consistentes:

1. Os prompts foram executados no mesmo modelo.
2. A interface utilizada foi mantida durante todos os testes.
3. Os prompts foram utilizados sem alterações durante cada comparação.
4. As respostas foram registradas integralmente.
5. Os resultados foram avaliados com os mesmos critérios.
6. As notas foram atribuídas de acordo com o comportamento observado.
7. Comportamentos inesperados e limitações foram documentados.

## Critérios de avaliação

| Critério          | Pergunta de avaliação                         |
| ----------------- | --------------------------------------------- |
| Clareza           | A resposta é fácil de compreender?            |
| Completude        | A resposta cobre os pontos necessários?       |
| Aderência         | A resposta segue as instruções do prompt?     |
| Relevância        | O conteúdo é útil para o cenário apresentado? |
| Reutilização      | A resposta pode ser reaproveitada facilmente? |
| Baixa ambiguidade | A resposta reduz interpretações conflitantes? |
| Consistência      | O formato esperado foi respeitado?            |

## Escala de avaliação

| Nota | Interpretação |
| ---: | ------------- |
|    1 | Muito fraco   |
|    2 | Fraco         |
|    3 | Adequado      |
|    4 | Bom           |
|    5 | Muito bom     |

Uma nota alta em `baixa ambiguidade` significa que a resposta apresentou pouco risco de interpretações conflitantes.

---

## Experimento 01 — Prompt simples vs prompt estruturado

### Objetivo

Observar como a definição de público e formato influencia a organização, a profundidade e a utilidade da resposta.

### Prompt simples

```txt
Explique o que é um LLM.
```

### Resposta do prompt simples

Um LLM, ou Large Language Model, é um modelo de inteligência artificial treinado com grandes volumes de texto para compreender e gerar linguagem.

Ele funciona analisando padrões presentes nos dados de treinamento e prevendo quais tokens têm maior probabilidade de aparecer em seguida. Isso permite realizar tarefas como responder perguntas, resumir textos, gerar conteúdo, traduzir idiomas e auxiliar na escrita de código.

Apesar de produzir respostas convincentes, um LLM pode gerar informações incorretas ou inventadas. Por isso, suas respostas devem ser avaliadas e validadas, principalmente em situações que exigem precisão.

### Prompt estruturado

```txt
Explique o que é um LLM para uma pessoa desenvolvedora iniciante.

Use esta estrutura:

1. Definição simples
2. Exemplo prático
3. Limitação comum
4. Por que isso importa ao criar produtos com IA
```

### Resposta do prompt estruturado

#### 1. Definição simples

Um LLM, ou Large Language Model, é um modelo de inteligência artificial treinado para compreender e gerar linguagem.

Ele recebe um texto como entrada e produz uma resposta calculando quais tokens têm maior probabilidade de aparecer em seguida.

#### 2. Exemplo prático

Imagine uma aplicação que recebe mensagens de suporte técnico.

Um LLM pode analisar uma mensagem como:

```txt
Não consigo acessar minha conta depois de trocar a senha.
```

E classificá-la como um problema relacionado à autenticação.

Essa classificação pode ser usada para encaminhar automaticamente a solicitação para a equipe correta.

#### 3. Limitação comum

Um LLM pode gerar respostas incorretas com aparência convincente.

Ele também não possui acesso automático a informações atualizadas, bancos de dados privados ou sistemas externos. Para isso, precisa ser conectado a ferramentas e fontes autorizadas.

#### 4. Por que isso importa ao criar produtos com IA

Ao criar um produto com LLMs, não basta produzir uma resposta bem escrita.

A aplicação precisa validar resultados, controlar o contexto, proteger dados privados, tratar falhas e utilizar ferramentas externas quando a tarefa exigir informações atuais ou operações exatas.

### Avaliação

| Critério          | Prompt simples | Prompt estruturado |
| ----------------- | -------------: | -----------------: |
| Clareza           |              4 |                  5 |
| Completude        |              3 |                  5 |
| Aderência         |              5 |                  5 |
| Relevância        |              4 |                  5 |
| Reutilização      |              3 |                  5 |
| Baixa ambiguidade |              4 |                  5 |
| Consistência      |              3 |                  5 |

### Justificativa das notas

A resposta do prompt simples foi correta e compreensível, mas apresentou uma explicação genérica. Ela não tinha um público definido nem uma estrutura que facilitasse seu uso em material de estudo.

A resposta estruturada explicou o conceito em etapas, apresentou um exemplo voltado para desenvolvimento de software, destacou uma limitação e relacionou o assunto à criação de produtos com IA.

### Diferenças observadas

* O prompt estruturado produziu uma resposta mais organizada.
* A definição de público ajustou o nível técnico da explicação.
* O exemplo tornou o conceito mais fácil de aplicar.
* A limitação foi apresentada de forma explícita.
* A resposta estruturada pode ser reutilizada com menos alterações.

### Comportamentos inesperados

* O prompt simples também mencionou limitações, mesmo sem essa exigência.
* O modelo acrescentou informações sobre tokens sem que o conceito tivesse sido solicitado diretamente.

### Conclusão

A definição de público, formato e pontos obrigatórios tornou a resposta mais completa e adequada para estudo.

O prompt simples funcionou para uma consulta rápida, enquanto o prompt estruturado produziu uma resposta mais previsível e reutilizável.

---

## Experimento 03 — Prompt com formato de saída

### Objetivo

Verificar se o modelo consegue classificar uma mensagem e retornar apenas um objeto JSON válido.

### Prompt utilizado

```txt
Classifique a seguinte mensagem do usuário em uma destas categorias:

- pergunta
- solicitacao_de_tarefa
- apoio_emocional
- problema_tecnico
- outro

Retorne apenas JSON.

Mensagem do usuário:
"Tentei rodar npm build, mas falhou com um erro de TypeScript."
```

### Resposta obtida

```json
{
  "categoria": "problema_tecnico"
}
```

### Validação da saída

* [x] A resposta contém apenas JSON.
* [x] O JSON é válido.
* [x] A propriedade `categoria` está presente.
* [x] O valor pertence à lista permitida.
* [x] Não existem explicações fora do JSON.

### Avaliação

| Critério          | Nota |
| ----------------- | ---: |
| Clareza           |    5 |
| Completude        |    5 |
| Aderência         |    5 |
| Relevância        |    5 |
| Reutilização      |    5 |
| Baixa ambiguidade |    5 |
| Consistência      |    5 |

### Justificativa das notas

O modelo seguiu todas as instruções e retornou somente o objeto JSON solicitado.

A categoria escolhida estava entre os valores permitidos e representava corretamente a mensagem fornecida.

### Problemas encontrados

Nenhum problema foi encontrado nesta execução.

### Validações necessárias em uma aplicação real

* Validar o JSON antes de processá-lo.
* Verificar se a propriedade `categoria` está presente.
* Validar o valor com uma lista ou enumeração permitida.
* Tratar respostas inválidas ou incompletas.
* Definir uma estratégia de nova tentativa.
* Registrar falhas para avaliação futura.

### Conclusão

O prompt foi suficiente para produzir uma saída utilizável nesta execução.

Entretanto, um único resultado correto não garante que todas as respostas futuras seguirão o mesmo formato. Em uma aplicação real, a saída ainda precisaria ser validada no código.

---

## Experimento 05 — Prompt sem contexto vs prompt com contexto

### Objetivo

Observar como informações sobre cenário, público e finalidade alteram a relevância da resposta.

### Prompt sem contexto

```txt
Crie um tutorial sobre autenticação.
```

### Resposta do prompt sem contexto

Autenticação é o processo utilizado para verificar a identidade de uma pessoa usuária antes de permitir seu acesso a um sistema.

Um fluxo básico de autenticação pode funcionar assim:

1. A pessoa informa seu e-mail e senha.
2. A aplicação envia os dados para o servidor.
3. O servidor procura o usuário no banco de dados.
4. A senha informada é comparada com o hash armazenado.
5. Se os dados estiverem corretos, o servidor cria uma sessão ou retorna um token.
6. Esse identificador é utilizado nas próximas requisições.

Para implementar autenticação com segurança, é importante utilizar HTTPS, armazenar senhas com algoritmos adequados, proteger tokens e limitar tentativas de login.

Também podem ser utilizados recursos como autenticação em dois fatores, recuperação de senha e login com provedores externos.

### Prompt com contexto

```txt
Estou estudando desenvolvimento web e quero entender autenticação em aplicações modernas.

Crie um tutorial curto explicando a diferença entre autenticação e autorização.

O tutorial deve ser simples, direto e pensado para pessoas desenvolvedoras iniciantes.
```

### Resposta do prompt com contexto

Autenticação e autorização fazem parte da segurança de uma aplicação, mas resolvem problemas diferentes.

### Autenticação

Autenticação responde à pergunta:

> Quem é você?

Ela acontece quando uma pessoa comprova sua identidade, por exemplo, usando e-mail e senha.

Depois que os dados são verificados, a aplicação pode criar uma sessão ou emitir um token.

### Autorização

Autorização responde à pergunta:

> O que você pode fazer?

Depois que a pessoa foi autenticada, a aplicação verifica quais recursos ou ações ela pode acessar.

Por exemplo:

* Uma pessoa usuária comum pode visualizar seu próprio perfil.
* Uma pessoa administradora pode visualizar e editar outros perfis.
* Uma pessoa não autenticada não pode acessar nenhuma dessas áreas.

### Exemplo de fluxo

1. A pessoa realiza o login.
2. A aplicação confirma sua identidade.
3. A pessoa tenta acessar uma página administrativa.
4. O sistema verifica suas permissões.
5. O acesso é permitido ou negado.

A autenticação identifica a pessoa. A autorização define suas permissões.

### Avaliação

| Critério          | Sem contexto | Com contexto |
| ----------------- | -----------: | -----------: |
| Clareza           |            4 |            5 |
| Completude        |            4 |            5 |
| Aderência         |            4 |            5 |
| Relevância        |            3 |            5 |
| Reutilização      |            3 |            5 |
| Baixa ambiguidade |            4 |            5 |
| Consistência      |            3 |            5 |

### Justificativa das notas

A resposta sem contexto apresentou um fluxo técnico de autenticação, mas não havia indicação sobre o nível de conhecimento esperado nem sobre o objetivo do tutorial.

A resposta com contexto diferenciou autenticação e autorização, utilizou perguntas simples para explicar cada conceito e apresentou um exemplo de fluxo adequado para iniciantes.

### Diferenças observadas

* O prompt sem contexto produziu uma explicação mais ampla e técnica.
* O prompt com contexto respondeu a uma dúvida específica.
* A linguagem foi adaptada para pessoas iniciantes.
* O exemplo reforçou a diferença entre identidade e permissão.
* A resposta contextualizada foi mais fácil de usar como material de estudo.

### Informações desnecessárias

Na resposta sem contexto, detalhes sobre hash, HTTPS e autenticação em dois fatores eram corretos, mas não ajudavam diretamente a responder à diferença entre autenticação e autorização.

### Comportamentos inesperados

* O modelo criou uma estrutura didática mesmo sem um formato explicitamente definido.
* A resposta contextualizada incluiu um exemplo de fluxo sem que isso tivesse sido exigido.

### Conclusão

O contexto alterou significativamente o escopo da resposta.

Sem contexto, o modelo interpretou o pedido de forma ampla. Com cenário, público e objetivo definidos, a resposta ficou mais relevante, didática e adequada ao estudo proposto.

---

## Experimento 07 — Prompt com checklist de qualidade

### Objetivo

Verificar se critérios explícitos tornam a revisão mais completa e consistente.

### Prompt utilizado

```txt
Revise a explicação abaixo sobre LLMs.

Checklist:
- A explicação está clara?
- Existe algum termo técnico sem explicação?
- A resposta pode causar uma interpretação errada?
- Falta algum exemplo prático?

Texto:
"LLMs são modelos treinados com muitos dados e usados para gerar respostas."
```

### Resposta obtida

#### 1. A explicação está clara?

* **Resultado:** parcialmente.
* **Justificativa:** a frase comunica a ideia geral, mas é curta demais para explicar o que diferencia um LLM de outros tipos de modelo.
* **Sugestão de melhoria:** informar que um LLM é um modelo de linguagem treinado para identificar padrões e gerar sequências de texto.

#### 2. Existe algum termo técnico sem explicação?

* **Resultado:** sim.
* **Justificativa:** a sigla `LLM` não foi explicada. A expressão “modelos treinados” também pode não ser clara para uma pessoa iniciante.
* **Sugestão de melhoria:** apresentar o significado de Large Language Model e explicar brevemente o que significa treinamento.

#### 3. A resposta pode causar uma interpretação errada?

* **Resultado:** sim.
* **Justificativa:** dizer apenas que LLMs são usados para gerar respostas pode sugerir que eles recuperam uma resposta pronta ou que sempre produzem informações corretas.
* **Sugestão de melhoria:** mencionar que a geração é probabilística e que o modelo pode produzir informações incorretas.

#### 4. Falta algum exemplo prático?

* **Resultado:** sim.
* **Justificativa:** não há um exemplo mostrando como um LLM pode ser utilizado.
* **Sugestão de melhoria:** incluir uma situação como resumir um texto, classificar uma mensagem ou auxiliar na escrita de código.

#### Versão revisada

Um LLM, ou Large Language Model, é um modelo de linguagem treinado com grandes volumes de texto para identificar padrões e gerar novas sequências de linguagem.

Ele pode ser utilizado para tarefas como explicar conceitos, resumir documentos, classificar mensagens e auxiliar na escrita de código.

Como sua geração é baseada em probabilidades, um LLM também pode produzir informações incorretas. Por isso, suas respostas precisam ser avaliadas de acordo com o contexto e o risco da tarefa.

### Validação do checklist

* [x] A clareza do texto foi avaliada.
* [x] Os termos técnicos foram avaliados.
* [x] Possíveis interpretações incorretas foram avaliadas.
* [x] A ausência de exemplo prático foi avaliada.
* [x] Cada item recebeu uma justificativa.
* [x] Cada item recebeu uma sugestão de melhoria.

### Avaliação

| Critério          | Nota |
| ----------------- | ---: |
| Clareza           |    5 |
| Completude        |    5 |
| Aderência         |    5 |
| Relevância        |    5 |
| Reutilização      |    5 |
| Baixa ambiguidade |    5 |
| Consistência      |    5 |

### Justificativa das notas

A resposta percorreu todos os itens do checklist, apresentou justificativas específicas e propôs melhorias aplicáveis.

Além da avaliação, o modelo gerou uma versão revisada, o que aumentou a utilidade prática da resposta.

### Pontos fortes

* Todos os critérios foram analisados.
* As justificativas foram relacionadas diretamente ao texto.
* As sugestões podiam ser aplicadas imediatamente.
* A resposta identificou risco de interpretação incorreta.
* A versão revisada consolidou as melhorias propostas.

### Pontos fracos

* A resposta ficou consideravelmente maior do que o texto original.
* O modelo acrescentou uma versão revisada sem que isso tivesse sido solicitado.
* Em textos maiores, um checklist muito amplo pode gerar análises repetitivas.

### Conclusão

O checklist melhorou tanto a organização quanto a profundidade da revisão.

Em vez de apenas afirmar que o texto estava incompleto, o modelo identificou problemas específicos, justificou cada avaliação e sugeriu mudanças concretas.

---

## Comparação geral

| Experimento | Padrão testado     | Principal melhoria                   | Principal limitação                                |
| ----------- | ------------------ | ------------------------------------ | -------------------------------------------------- |
| 01          | Prompt estruturado | Organização e adequação ao público   | Exige mais elaboração no prompt                    |
| 03          | Formato de saída   | Resposta previsível e processável    | Ainda exige validação no código                    |
| 05          | Contexto           | Maior relevância para o objetivo     | Contexto inadequado pode direcionar mal a resposta |
| 07          | Checklist          | Revisão mais completa e justificável | Pode aumentar o tamanho e a repetição              |

## Principais descobertas

* Um prompt simples pode produzir uma resposta correta, mas oferece menos controle sobre profundidade e organização.
* Definir público e estrutura aumenta a utilidade da resposta para estudo e documentação.
* Solicitar JSON pode produzir uma saída adequada, mas não elimina a necessidade de validação.
* O contexto reduz interpretações amplas e direciona melhor o conteúdo.
* Checklists tornam avaliações mais explícitas e consistentes.
* Instruções claras não garantem que o modelo executará apenas o que foi solicitado.
* O modelo pode adicionar conteúdo útil, mas não solicitado.
* A qualidade de uma resposta depende tanto do modelo quanto da forma como a tarefa é apresentada.

## Limitações dos testes

* Apenas um modelo foi utilizado.
* Cada prompt foi executado apenas uma vez.
* A temperatura não estava disponível na interface.
* A avaliação das respostas envolve interpretação humana.
* Os resultados podem variar em outras execuções.
* A amostra de experimentos foi pequena.
* Não houve comparação entre diferentes provedores ou modelos.
* Os testes analisaram respostas isoladas, sem histórico de conversa.

## Conclusão do Lab 01

Os experimentos demonstraram que a estrutura do prompt influencia diretamente o comportamento e a utilidade das respostas geradas por um LLM.

O prompt simples foi suficiente para obter uma explicação geral, mas a inclusão de público, estrutura e pontos obrigatórios tornou a resposta mais completa e reutilizável.

O formato de saída permitiu obter um JSON válido e consistente. Entretanto, esse resultado não elimina a necessidade de schemas, validação e tratamento de erros em aplicações reais.

O experimento com contexto mostrou que informações sobre cenário, finalidade e público reduzem respostas genéricas e ajudam o modelo a selecionar conteúdos mais relevantes.

O checklist tornou a revisão mais completa porque transformou critérios abstratos em perguntas explícitas. Isso facilitou a identificação de problemas, a justificativa das avaliações e a criação de sugestões de melhoria.

O principal aprendizado deste laboratório é que engenharia de prompt não consiste apenas em escrever pedidos mais longos. Ela envolve definir com clareza o objetivo, o contexto, os limites, o formato e os critérios usados para avaliar a resposta.

Prompts melhores aumentam o controle sobre o comportamento do modelo, mas não substituem validação, testes e arquitetura.

## Checklist de conclusão

* [x] Pelo menos quatro experimentos foram executados.
* [x] O modelo e a plataforma foram registrados.
* [x] As respostas foram documentadas.
* [x] Os resultados foram avaliados.
* [x] As notas foram justificadas.
* [x] As diferenças foram comparadas.
* [x] As limitações foram registradas.
* [x] A conclusão foi baseada nos resultados observados.
* [x] Nenhum dado privado foi utilizado.
