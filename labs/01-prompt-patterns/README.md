# Lab 01 — Padrões de Prompt

Este laboratório explora como diferentes estruturas de prompt afetam a qualidade, clareza e confiabilidade das respostas de um LLM.

## Objetivo

Entender como o design do prompt influencia o comportamento do modelo.

## Experimento 01 — Prompt simples vs prompt estruturado

### Prompt simples

```txt
Explique o que é um LLM.
```

### Prompt estruturado

```txt
Explique o que é um LLM para uma pessoa desenvolvedora iniciante.

Use esta estrutura:

1. Definição simples
2. Exemplo prático
3. Limitação comum
4. Por que isso importa ao criar produtos com IA
```

## Observação

O prompt estruturado oferece ao modelo uma tarefa mais clara, um público definido e um formato esperado de resposta.

Isso geralmente produz uma resposta mais útil do que um prompt amplo e genérico.

## Experimento 02 — Prompt com papel definido

```txt
Atue como uma pessoa engenheira de IA sênior orientando uma pessoa desenvolvedora iniciante.

Explique o que é engenharia de prompts e por que ela importa na criação de aplicações com LLMs.
```

## Experimento 03 — Prompt com formato de saída

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

Saída esperada:

```json
{
  "categoria": "problema_tecnico"
}
```

## Notas

Padrões de prompt não são mágica. São design de interface.

Um bom prompt reduz ambiguidade, define o comportamento esperado e torna a saída mais fácil de usar em um sistema real.