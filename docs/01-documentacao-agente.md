# Documentação do Agente

## Caso de Uso

### Problema
> Qual problema financeiro seu agente resolve?

Muitos casais têm dificuldade em ter gastos, poupança e investimentos

### Solução
> Como o agente resolve esse problema de forma proativa?

Agente que centraliza finanças, gera alertas, sugere planos simples de investimento e motiva hábitos saudáveis.

### Público-Alvo
> Quem vai usar esse agente?

Casais, sobre tudo recéns casados.

---

## Persona e Tom de Voz

### Nome do Agente
[Rosalina]

### Personalidade
> Como o agente se comporta? (ex: consultivo, direto, educativo)

[Amigável, acessível]

### Tom de Comunicação
> Formal, informal, técnico, acessível?

[Com tom consultivo ou motivacional]

### Exemplos de Linguagem
- Saudação: [ex: "Olá! Como posso ajudar com suas finanças hoje?"]
- Confirmação: [ex: "Entendi! Deixa eu verificar isso para você."]
- Erro/Limitação: [ex: "Não tenho essa informação no momento, mas posso ajudar com..."]

---

## Arquitetura

### Diagrama

```mermaid
flowchart TD
    A[Cliente] -->|Mensagem| B[Interface]
    B --> C[LLM]
    C --> D[Base de Conhecimento]
    D --> C
    C --> E[Validação]
    E --> F[Resposta]
```

### Componentes

| Componente | Descrição |
|------------|-----------|
| Interface | [ex: Chatbot em Streamlit] |
| LLM | [ex: GPT-4 via API] |
| Base de Conhecimento | [ex: JSON/CSV com dados do cliente] |
| Validação | [ex: Checagem de alucinações] |

---

## Segurança e Anti-Alucinação

### Estratégias Adotadas

- [ ] [ex: Agente só responde com base nos dados fornecidos]
- [ ] [ex: Respostas incluem fonte da informação]
- [ ] [ex: Quando não sabe, admite e redireciona]
- [ ] [ex: Não faz recomendações de investimento sem perfil do cliente]

### Limitações Declaradas
> O que o agente NÃO faz?

[Liste aqui as limitações explícitas do agente]
