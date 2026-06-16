# 01 — Fundamentos de LLMs

## O que é um LLM?

Large Language Model, ou LLM, é um modelo de linguagem treinado para identificar padrões em grandes volumes de texto e gerar sequências de tokens com base no contexto recebido.

De forma simplificada, um LLM recebe uma entrada, calcula quais tokens são mais prováveis de aparecer em seguida e continua esse processo até produzir uma resposta.

Um LLM não funciona como um banco de dados tradicional. Ele não procura necessariamente uma informação exata armazenada em uma tabela. Sua resposta é gerada com base em padrões aprendidos durante o treinamento, nas instruções recebidas e no contexto atual.

## Modelo mental

Uma forma útil de compreender um LLM é pensar nele como um mecanismo probabilístico de transformação de linguagem.

Ele pode:

* Receber uma instrução
* Interpretar padrões no contexto
* Relacionar conceitos
* Transformar informações
* Gerar uma sequência de saída

Entretanto, uma resposta linguisticamente convincente não é garantia de que a informação esteja correta.

## Tokens

Tokens são as unidades de texto processadas pelo modelo.

Um token pode representar:

* Uma palavra inteira
* Parte de uma palavra
* Um número
* Um símbolo
* Um sinal de pontuação
* Um espaço ou combinação de caracteres

A divisão exata depende do tokenizador utilizado pelo modelo.

### Por que tokens importam?

A quantidade de tokens influencia:

* O tamanho do contexto disponível
* O custo de utilização de APIs
* O tempo de processamento
* O tamanho máximo da resposta
* A quantidade de documentos que pode ser enviada ao modelo

Texto, instruções, histórico da conversa e resposta gerada compartilham o limite de contexto do modelo.

## Tokenização

Tokenização é o processo de transformar texto em tokens que podem ser processados pelo modelo.

Por exemplo, uma palavra longa ou pouco comum pode ser dividida em vários tokens, enquanto uma palavra frequente pode ser representada por um único token.

Isso significa que número de palavras e número de tokens não são a mesma coisa.

## Janela de contexto

A janela de contexto representa a quantidade máxima de tokens que o modelo consegue considerar durante uma interação.

Ela pode incluir:

* Instruções do sistema
* Mensagens da pessoa usuária
* Respostas anteriores
* Exemplos
* Documentos
* Dados estruturados
* Resultados de ferramentas
* A resposta que está sendo gerada

Quando o conteúdo ultrapassa o limite disponível, parte dele precisa ser removida, resumida, dividida ou recuperada apenas quando necessária.

### Contexto não é memória permanente

Informações presentes em uma conversa fazem parte do contexto atual, mas isso não significa que o modelo tenha criado uma memória permanente.

Memória em aplicações com LLMs normalmente exige mecanismos externos, como:

* Banco de dados
* Histórico persistente
* Resumos de conversa
* Busca semântica
* Perfis de usuário
* Sistemas próprios de memória

## Treinamento e inferência

### Treinamento

O treinamento é o processo em que o modelo aprende padrões a partir de grandes volumes de dados.

Durante esse processo, seus parâmetros internos são ajustados para melhorar a capacidade de prever tokens e representar relações entre diferentes elementos da linguagem.

### Inferência

Inferência é o momento em que um modelo já treinado recebe uma entrada e gera uma resposta.

Durante uma conversa comum, o modelo normalmente não está sendo treinado novamente. Ele utiliza:

* Padrões aprendidos anteriormente
* Instruções da aplicação
* Contexto da conversa
* Exemplos fornecidos
* Dados retornados por ferramentas

## Geração probabilística

Um LLM não produz respostas a partir de uma única sequência obrigatória.

Para cada etapa da geração, diferentes tokens podem possuir diferentes probabilidades. O sistema utiliza uma estratégia de seleção para decidir qual token será gerado.

Por isso, o mesmo prompt pode produzir respostas diferentes em execuções distintas.

## Temperatura

A temperatura é um parâmetro que pode influenciar o nível de variação da geração.

Em termos gerais:

* Temperaturas mais baixas tendem a produzir respostas mais previsíveis
* Temperaturas mais altas tendem a produzir respostas mais variadas

A temperatura não controla a veracidade da resposta.

Uma resposta mais previsível ainda pode estar errada, e uma resposta mais criativa não é necessariamente menos útil.

## No que LLMs são bons

LLMs podem ser úteis para:

* Explicar conceitos
* Resumir conteúdos
* Reescrever textos
* Classificar informações
* Extrair dados
* Gerar estruturas iniciais
* Traduzir conteúdos
* Apoiar desenvolvimento de código
* Comparar alternativas
* Analisar texto
* Criar interfaces conversacionais
* Orquestrar chamadas de ferramentas

O desempenho depende do modelo, do contexto, do prompt, dos dados fornecidos e dos critérios utilizados para avaliar a saída.

## Onde LLMs podem falhar

LLMs podem apresentar dificuldades quando precisam:

* Garantir precisão factual
* Trabalhar com informações atuais sem acesso a fontes externas
* Acessar dados privados sem ferramentas autorizadas
* Realizar cálculos exatos sem uma calculadora
* Manter consistência em tarefas longas
* Interpretar instruções ambíguas
* Identificar corretamente quando não possuem informação suficiente
* Produzir sempre o mesmo formato sem validação
* Lembrar informações entre sessões sem memória externa

## Alucinação

Alucinação é o nome dado a uma resposta gerada com informações incorretas, inventadas, não verificadas ou sem base suficiente no contexto.

Uma alucinação pode parecer convincente porque o modelo é capaz de produzir linguagem coerente mesmo quando não possui evidência adequada.

Isso pode acontecer quando:

* O prompt é vago
* O contexto é insuficiente
* A tarefa exige informação atualizada
* A fonte fornecida não contém a resposta
* O modelo tenta preencher lacunas
* A aplicação não exige citações ou validação
* A pessoa usuária pressupõe que toda resposta é factual

## Como reduzir riscos

Nenhuma técnica elimina completamente o risco de erro, mas algumas estratégias ajudam:

* Fornecer instruções claras
* Delimitar o escopo da tarefa
* Oferecer contexto confiável
* Solicitar indicação de incerteza
* Utilizar fontes verificáveis
* Conectar o modelo a ferramentas
* Validar saídas estruturadas
* Criar testes automatizados
* Manter revisão humana em tarefas críticas
* Registrar métricas e falhas

## Papéis das mensagens

Aplicações com LLMs podem organizar a interação em diferentes tipos de mensagem.

### System

Define regras gerais, comportamento, limites e contexto da aplicação.

### User

Representa a solicitação enviada pela pessoa usuária.

### Assistant

Representa as respostas geradas pelo modelo e pode fazer parte do histórico da conversa.

### Tool

Contém dados retornados por ferramentas externas, como APIs, bancos de dados, mecanismos de busca ou calculadoras.

A nomenclatura e o comportamento exato podem variar entre provedores.

## Hierarquia de instruções

Nem todas as instruções possuem a mesma prioridade.

Em uma aplicação, regras definidas pelo sistema normalmente possuem prioridade sobre solicitações da pessoa usuária.

Essa separação é importante para:

* Proteger regras da aplicação
* Manter comportamento consistente
* Reduzir conflitos de instrução
* Controlar acesso a ferramentas
* Aplicar limites de segurança

## LLMs e ferramentas

Um LLM isolado gera respostas com base no contexto disponível.

Quando conectado a ferramentas, ele pode solicitar operações externas, como:

* Pesquisar informações atualizadas
* Consultar bancos de dados
* Fazer cálculos
* Ler documentos
* Executar código
* Criar eventos
* Enviar informações para uma API
* Buscar dados de um sistema interno

Nesse fluxo, o modelo não necessariamente executa a operação diretamente.

Ele pode identificar a intenção, selecionar uma ferramenta, gerar argumentos e utilizar o resultado retornado para construir a resposta final.

## Saídas estruturadas

Em muitas aplicações, texto livre não é suficiente.

O sistema pode precisar que o modelo retorne dados em uma estrutura previsível, como:

```json
{
  "categoria": "problema_tecnico",
  "prioridade": "alta"
}
```

Prompts ajudam a orientar esse formato, mas aplicações reais também devem utilizar:

* Schemas
* Tipagem
* Parsers
* Validação
* Tratamento de erros
* Tentativas de correção

Solicitar JSON em um prompt não garante, sozinho, que todo resultado será válido.

## Prompt engineering

Prompt engineering é a prática de projetar instruções, contexto, exemplos, restrições e formatos para orientar o comportamento de um modelo.

Um prompt pode definir:

* A tarefa
* O público
* O contexto
* O formato esperado
* Os limites
* Os critérios de qualidade
* Os exemplos
* O comportamento em caso de incerteza

Um bom prompt reduz ambiguidade, mas não substitui arquitetura, validação ou avaliação.

## Avaliação

Uma resposta não deve ser considerada boa apenas porque parece bem escrita.

Ela pode ser avaliada com critérios como:

* Correção
* Clareza
* Completude
* Relevância
* Consistência
* Aderência às instruções
* Segurança
* Custo
* Tempo de resposta
* Facilidade de utilização pelo sistema

Avaliar LLMs exige observar tanto a qualidade da resposta quanto seu comportamento em diferentes entradas.

## Aplicações com LLMs

Uma aplicação com LLM normalmente possui mais componentes do que apenas modelo e prompt.

Uma arquitetura pode incluir:

```txt
Pessoa usuária
      ↓
Aplicação
      ↓
Instruções e contexto
      ↓
LLM
      ↓
Ferramentas ou fontes externas
      ↓
Validação
      ↓
Resposta final
```

A confiabilidade do sistema depende da combinação entre esses componentes.

## Princípios para criação de produtos com LLMs

1. Não assumir que o modelo está sempre correto.
2. Não depender apenas do prompt para garantir regras críticas.
3. Validar saídas antes de utilizá-las em outras operações.
4. Fornecer apenas o contexto necessário.
5. Usar ferramentas para dados atuais ou operações exatas.
6. Tratar falhas e respostas inesperadas.
7. Avaliar o sistema com diferentes tipos de entrada.
8. Manter revisão humana quando o risco for alto.
9. Proteger dados privados.
10. Monitorar custo, latência e qualidade.

## Glossário

### LLM

Modelo de linguagem treinado em grandes volumes de dados.

### Token

Unidade de texto processada pelo modelo.

### Tokenização

Processo de transformar texto em tokens.

### Contexto

Conjunto de informações disponíveis para o modelo durante uma interação.

### Janela de contexto

Limite de tokens que o modelo pode considerar.

### Inferência

Processo de gerar uma resposta usando um modelo treinado.

### Alucinação

Geração de informação incorreta, inventada ou sem base suficiente.

### Prompt

Entrada que contém instruções, contexto, exemplos ou dados para o modelo.

### Tool calling

Mecanismo pelo qual o modelo solicita o uso de uma ferramenta externa.

### Saída estruturada

Resposta organizada em um formato previsível, como JSON.

## Perguntas de revisão

1. O que diferencia um LLM de um banco de dados?
2. O que são tokens?
3. Por que número de palavras e número de tokens não são iguais?
4. O que pode ocupar a janela de contexto?
5. Contexto e memória permanente são a mesma coisa?
6. Qual é a diferença entre treinamento e inferência?
7. Por que o mesmo prompt pode produzir respostas diferentes?
8. A temperatura determina se uma resposta está correta?
9. O que caracteriza uma alucinação?
10. Como ferramentas externas ampliam as capacidades de um LLM?
11. Por que solicitar JSON não garante uma saída válida?
12. Qual é a função das mensagens de system, user, assistant e tool?
13. Por que um bom prompt não substitui validação?
14. Quais critérios podem ser utilizados para avaliar uma resposta?
15. Quais componentes podem fazer parte de uma aplicação com LLM?

## Principal aprendizado

LLMs são mecanismos probabilísticos de linguagem, não fontes infalíveis de verdade.

Eles se tornam mais úteis quando combinados com contexto adequado, instruções claras, dados confiáveis, ferramentas externas, validação e critérios de avaliação.
