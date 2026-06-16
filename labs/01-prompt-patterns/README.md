# Lab 01 — Padrões de Prompt

Este laboratório explora como diferentes estruturas de prompt afetam a qualidade, clareza, consistência e confiabilidade das respostas geradas por um LLM.

A ideia central deste estudo é entender que prompts não são apenas perguntas feitas para uma IA. Prompts funcionam como uma interface entre a intenção da pessoa usuária e o comportamento esperado do modelo.

## Objetivo

Entender como o design do prompt influencia o comportamento do modelo e como diferentes padrões podem melhorar a utilidade das respostas em estudos, automações e aplicações reais com LLMs.

## Pergunta principal

Como pequenas mudanças na estrutura de um prompt alteram a qualidade da resposta gerada por um LLM?

## Critérios de avaliação

Durante os experimentos, as respostas devem ser avaliadas considerando:

1. Clareza
2. Completude
3. Aderência ao pedido
4. Facilidade de reutilização
5. Risco de ambiguidade
6. Consistência do formato de saída

---

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

### Observação

O prompt simples tende a gerar uma resposta ampla e genérica.

O prompt estruturado oferece ao modelo uma tarefa mais clara, um público definido e um formato esperado de resposta.

### Conclusão

Quando o prompt define público, objetivo e estrutura, a resposta tende a ser mais útil para estudo, documentação ou uso em produto.

---

## Experimento 02 — Prompt com papel definido

```txt
Atue como uma pessoa engenheira de IA sênior orientando uma pessoa desenvolvedora iniciante.

Explique o que é engenharia de prompts e por que ela importa na criação de aplicações com LLMs.
```

### Observação

Definir um papel ajuda o modelo a ajustar o tom, o nível técnico e a perspectiva da resposta.

### Conclusão

Prompt com papel definido é útil quando a resposta precisa assumir uma perspectiva específica, como professora, revisora técnica, analista de produto, pessoa especialista em segurança ou pessoa desenvolvedora sênior.

---

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

### Saída esperada

```json
{
  "categoria": "problema_tecnico"
}
```

### Observação

Definir o formato de saída reduz ambiguidade e facilita o uso da resposta em sistemas reais.

### Conclusão

Prompts com formato de saída são importantes quando a resposta será processada por código, salva em banco, enviada para uma API ou usada em automações.

---

## Experimento 04 — Prompt com restrições

### Prompt sem restrições

```txt
Explique engenharia de prompts.
```

### Prompt com restrições

```txt
Explique engenharia de prompts em português.

Restrições:
- Use linguagem simples.
- Não use metáforas infantis.
- Não ultrapasse 4 parágrafos.
- Inclua um exemplo prático voltado para desenvolvimento de software.
```

### Observação

As restrições ajudam a controlar tamanho, linguagem, estilo e profundidade da resposta.

### Conclusão

Restrições tornam o resultado mais previsível. Isso é importante quando o LLM será usado dentro de uma experiência de produto, onde respostas longas, vagas ou fora do tom podem prejudicar a pessoa usuária.

---

## Experimento 05 — Prompt com contexto

### Prompt sem contexto

```txt
Crie um tutorial sobre autenticação.
```

### Prompt com contexto

```txt
Estou estudando desenvolvimento web e quero entender autenticação em aplicações modernas.

Crie um tutorial curto explicando a diferença entre autenticação e autorização.

O tutorial deve ser simples, direto e pensado para pessoas desenvolvedoras iniciantes.
```

### Observação

O contexto ajuda o modelo a entender o cenário de uso, o público e a finalidade da resposta.

### Conclusão

Quanto melhor o contexto, maior a chance de a resposta ser aplicável ao problema estudado. Sem contexto, o modelo tende a responder de forma genérica.

---

## Experimento 06 — Prompt com exemplo de saída

```txt
Extraia as informações principais da mensagem abaixo.

Use exatamente este formato:

{
  "problema": "",
  "tecnologia": "",
  "urgencia": ""
}

Mensagem:
"O sistema de login apresentou erro após a atualização. Algumas pessoas usuárias não conseguem acessar a plataforma."
```

### Saída esperada

```json
{
  "problema": "Erro no sistema de login após atualização",
  "tecnologia": "Sistema de login",
  "urgencia": "alta"
}
```

### Observação

Mostrar um exemplo de saída reduz a chance de o modelo inventar formatos diferentes.

### Conclusão

Exemplos são úteis quando queremos padronizar respostas, especialmente em tarefas de classificação, extração e transformação de dados.

---

## Experimento 07 — Prompt com checklist de qualidade

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

### Observação

O checklist orienta o modelo a revisar a resposta com critérios explícitos.

### Conclusão

Prompts com checklist são úteis para revisão, melhoria de conteúdo, validação de requisitos e análise crítica.

---

## Experimento 08 — Prompt com decomposição da tarefa

### Prompt amplo

```txt
Me ajude a estudar RAG.
```

### Prompt com decomposição

```txt
Me ajude a estudar RAG dividindo a explicação em etapas:

1. O problema que RAG resolve
2. Como funciona em alto nível
3. Principais componentes
4. Exemplo simples de uso
5. Limitações comuns
6. Próximos assuntos para estudar
```

### Observação

A decomposição transforma uma tarefa ampla em partes menores e mais fáceis de responder.

### Conclusão

Prompts com decomposição são úteis quando o assunto é complexo, quando a pessoa ainda está aprendendo ou quando a resposta precisa seguir uma linha de raciocínio mais organizada.

---

## Experimento 09 — Prompt para comparação

```txt
Compare prompt engineering e fine-tuning.

Use esta estrutura:

- Definição de prompt engineering
- Definição de fine-tuning
- Quando usar prompt engineering
- Quando usar fine-tuning
- Exemplo prático
- Principal diferença
```

### Observação

Pedir uma comparação estruturada ajuda o modelo a organizar diferenças, vantagens e cenários de uso.

### Conclusão

Prompts de comparação são úteis para estudar conceitos próximos e evitar confusões entre termos técnicos.

---

## Experimento 10 — Prompt para extração estruturada

```txt
Extraia as informações da mensagem abaixo e retorne apenas JSON.

Campos:
- nome
- curso
- interesse
- nivel_de_experiencia

Mensagem:
"Olá, sou Marina, estudo Sistemas de Informação e quero começar a aprender sobre agentes de IA. Ainda estou no nível iniciante."
```

### Saída esperada

```json
{
  "nome": "Marina",
  "curso": "Sistemas de Informação",
  "interesse": "agentes de IA",
  "nivel_de_experiencia": "iniciante"
}
```

### Observação

A extração estruturada transforma texto livre em dados organizados.

### Conclusão

Esse padrão é importante para aplicações que precisam interpretar mensagens, classificar solicitações, preencher campos ou preparar dados para outros sistemas.

---

## Comparação entre padrões

| Padrão               | Quando usar                          | Principal benefício |
| -------------------- | ------------------------------------ | ------------------- |
| Prompt simples       | Perguntas rápidas e exploratórias    | Velocidade          |
| Prompt estruturado   | Estudos, explicações e documentação  | Clareza             |
| Papel definido       | Ajuste de tom e perspectiva          | Direcionamento      |
| Formato de saída     | Integração com sistemas              | Consistência        |
| Restrições           | Controle de tamanho, estilo e escopo | Previsibilidade     |
| Contexto             | Cenários específicos de uso          | Relevância          |
| Exemplo de saída     | Extração e classificação             | Padronização        |
| Checklist            | Revisão e validação                  | Qualidade           |
| Decomposição         | Assuntos complexos                   | Organização         |
| Comparação           | Conceitos parecidos                  | Diferenciação       |
| Extração estruturada | Transformar texto em dados           | Automação           |

---

## Notas

Padrões de prompt não são mágica. São design de interface.

Um bom prompt reduz ambiguidade, define o comportamento esperado e torna a saída mais fácil de usar em um sistema real.

A qualidade da resposta não depende apenas do modelo. Depende também da forma como a tarefa é apresentada.

## Aprendizados do Lab 01

* Prompts genéricos produzem respostas genéricas.
* Contexto melhora a relevância da resposta.
* Restrições ajudam a controlar o comportamento do modelo.
* Formatos de saída tornam a resposta mais útil em aplicações reais.
* Exemplos reduzem ambiguidade.
* Checklists melhoram revisão e consistência.
* Decompor tarefas ajuda em assuntos complexos.
* Comparações estruturadas ajudam a diferenciar conceitos parecidos.
* Engenharia de prompt é uma prática de design, produto e desenvolvimento.

## Próximos passos

* Executar os prompts em um LLM e comparar as respostas.
* Registrar diferenças entre os resultados.
* Testar variações de contexto, restrição e formato.
* Criar uma tabela de avaliação para cada experimento.
* Evoluir este laboratório com exemplos reais, porém genéricos e sem dados privados.
