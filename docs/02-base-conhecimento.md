# Base de Conhecimento

## Dados Utilizados

Descreva se usou os arquivos da pasta `data`, por exemplo:

| Arquivo | Formato | Utilização no Agente |
|---------|---------|---------------------|
| `historico_atendimento.csv` | CSV | Contextualizar interações anteriores |
| `perfil_investidor.json` | JSON | Personalizar recomendações |
| `produtos_financeiros.json` | JSON | Sugerir produtos adequados ao perfil |
| `transacoes.csv` | CSV | Analisar padrão de gastos do cliente |

> [!TIP]
> **Quer um dataset mais robusto?** Você pode utilizar datasets públicos do [Hugging Face](https://huggingface.co/datasets) relacionados a finanças, desde que sejam adequados ao contexto do desafio.

---

## Adaptações nos Dados

> Você modificou ou expandiu os dados mockados? Descreva aqui.

| Arquivo | Formato | Utilização no Agente |
|---------|---------|---------------------|
| `historico_atendimento.csv` | CSV | Analisar padrão de gastos do casal, identificar excessos e gerar alertas |
| `perfil_investidor.json` | JSON | Personalizar recomendações de poupança e investimentos conforme perfil e metas |
| `produtos_financeiros.json` | JSON | Sugerir produtos adequados ao perfil e objetivos (Tesouro, CDB, fundos |
| `transacoes.csv` | CSV | Contextualizar interações anteriores e evitar repetição de informações |

---

## Estratégia de Integração

### Como os dados são carregados?
> Descreva como seu agente acessa a base de conhecimento.

Os arquivos CSV/JSON são carregados no início da sessão.

O agente consulta dinamicamente os dados para:

Gerar alertas de gastos.

Sugerir planos de investimento simples.

Motivar hábitos saudáveis com mensagens personalizadas.

### Como os dados são usados no prompt?
> Os dados vão no system prompt? São consultados dinamicamente?

O system prompt define apenas o papel do agente (ex.: “Você é um assistente financeiro que ajuda casais a organizar gastos, poupança e investimentos”).

Os dados reais (transações, perfil, produtos, histórico) são carregados e formatados como contexto adicional no momento da consulta.

Isso permite que o agente use informações atualizadas sem precisar reescrever o system prompt.

---

## Exemplo de Contexto Montado

> Mostre um exemplo de como os dados são formatados para o agente.
```
Dados do Cliente:
- Nome: João Silva
- Perfil: Moderado
- Renda mensal: R$ 5.000
- Objetivo principal: Completar reserva de emergência (meta R$ 15.000, atual R$ 10.000)

Últimas transações:
- 01/10: Supermercado - R$ 450
- 05/10: Netflix - R$ 55,90
- 10/10: Restaurante - R$ 120
- 25/10: Combustível - R$ 250

Resumo financeiro:
- Despesas totais: R$ 2.637,90
- Saldo líquido: R$ 2.362,10
- Alertas: gasto elevado em lazer e alimentação

Sugestões de investimento:
- Tesouro Selic: aporte sugerido R$ 1.000 (reserva de emergência)
- CDB Liquidez Diária: aporte sugerido R$ 500 (segurança e liquidez)
```

Hábitos recomendados:
- Guardar 20% da renda mensal
- Limitar lazer a R$ 300/mês
