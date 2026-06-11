
## `notes/01-llm-fundamentals.md`

```md
# 01 — Fundamentos de LLMs

## O que é um LLM?

Um Large Language Model, ou LLM, é um modelo treinado para prever e gerar texto com base em padrões aprendidos a partir de grandes volumes de dados.

Um LLM não "sabe" informações da mesma forma que um banco de dados sabe. Ele gera respostas com base em probabilidade, contexto, instruções e exemplos.

## No que LLMs são bons

LLMs são úteis para:

- Explicar conceitos
- Resumir informações
- Gerar textos
- Transformar conteúdos
- Classificar informações
- Extrair dados estruturados
- Ajudar com código
- Apoiar fluxos de decisão

## Onde LLMs falham

LLMs podem falhar quando precisam:

- Garantir precisão factual
- Acessar dados privados ou atualizados sem ferramentas
- Fazer cálculos exatos sem uma calculadora
- Lembrar informações entre sessões sem memória
- Seguir instruções vagas com consistência
- Demonstrar incerteza sem serem orientados a isso

## Conceito importante: contexto

O modelo responde com base no contexto que recebe.

Quanto melhor o contexto, melhor tende a ser a resposta.

O contexto pode incluir:

- Pedido do usuário
- Instruções do sistema
- Exemplos
- Documentos
- Resultados de ferramentas
- Mensagens anteriores
- Dados estruturados

## Conceito importante: alucinação

Uma alucinação acontece quando o modelo gera uma informação que parece correta, mas não é confiável ou verdadeira.

Isso pode acontecer quando:

- O prompt é vago
- O modelo não tem contexto suficiente
- A tarefa exige informação atualizada
- O modelo tenta preencher lacunas em vez de dizer que não sabe

## Como projetar considerando essas limitações

Um bom sistema com IA não assume que o modelo está sempre certo.

Ele usa estratégias como:

- Instruções claras
- Saídas estruturadas
- Uso de ferramentas
- Regras de validação
- Revisão humana
- Consulta a fontes confiáveis
- Testes de avaliação

## Principal aprendizado

LLMs são ferramentas poderosas de linguagem e raciocínio, mas se tornam muito mais úteis quando combinados com bons prompts, dados confiáveis, ferramentas externas e critérios claros de avaliação.