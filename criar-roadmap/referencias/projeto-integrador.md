# Projeto integrador

Os blocos ensinam peças isoladas. O projeto integrador obriga a juntar tudo e a **tomar decisões que não têm resposta única**, como no trabalho real. Os bugs mais caros moram na junção entre peças que, isoladas, estavam certas.

## Quando incluir

Sempre que o objetivo envolver construir, operar ou diagnosticar sistemas. Se a pessoa já tem um projeto próprio, **evolua esse**: o integrador não precisa ser um projeto separado.

## O cenário

Escreva um cenário do mundo da pessoa, com uma tela ou um fluxo concreto, e **restrições numéricas** que obriguem a escolher:

```markdown
## O cenário
O time de <produto> precisa de <sistema> para <tela ou fluxo>.

<Um desenho ASCII da tela ou do fluxo, se ajudar>

**Restrições reais:**
- A tela precisa responder em menos de 500 ms
- A API A demora ~300 ms, e a B ~400 ms
- Chamadas sequenciais já estouram o orçamento
- Dados sensíveis não podem aparecer em log
- <Uma restrição de disponibilidade: "se a API B cair, o que o usuário vê?">
```

As restrições são o que transforma "fazer funcionar" em "decidir e justificar". Sem elas, o projeto vira um exercício de tutorial.

## As fases

Uma fase por etapa relevante, cada uma construindo sobre a anterior:

| Fase | Amarrada a | Padrão de conteúdo |
|---|---|---|
| 1 | Etapa em que o projeto passa a rodar | O núcleo funcional: agregação, autenticação, tratamento de erro |
| 2 | Etapa de dados ou cache | A camada de dados, com uma decisão justificada (ex.: TTL) |
| 3 | Etapa de observabilidade | Logs, métricas, resiliência |
| Avaliação final | Início da etapa de infraestrutura | A defesa |
| 4 | Etapa de infraestrutura | Deploy real, pipeline e war room ao vivo às cegas |

Cada `fase-N.md` tem:
- **Quando fazer** e o que precisa estar pronto antes;
- **requisitos** com **critério de pronto verificável** (comando e saída esperada);
- **🔴 a decisão a justificar**, destacada ("sequencial ou paralelo? faça a conta antes de escolher e escreva o porquê no commit");
- as **dívidas herdadas** cobradas naquela fase;
- **a prova que fecha a fase**, por exemplo: "um deploy com requisições em loop não produz um único erro. Sem isso a fase não está pronta, só parece".

Atraso numa fase bloqueia as seguintes. Quando isso acontecer, diga explicitamente e reordene o plano da etapa para destravá-la primeiro.

## Code review do projeto

Um `code-review-regras.md` com o processo (como submeter, severidades 🔴🟡🟢, o que avalia e o que não avalia) e um `fase-N-code-review.md` com os critérios de cada fase. O resultado vai para o `fase-N-feedback.md`. Ver [avaliacao-e-feedback.md](avaliacao-e-feedback.md).

## A avaliação final: defesa, não produção

Não é sobre escrever mais código. É sobre sustentar o que foi feito, como numa conversa com o time de arquitetura.

```markdown
# Avaliação final — Projeto integrador

> Obrigatório: link do repositório com o código de todas as fases.

## Parte 1 — Code review do próprio código
Segurança, resiliência, cache, performance: perguntas que a obrigam a achar os próprios defeitos.

## Parte 2 — As decisões que você tomou
Para cada decisão: o que fez, por quê e o que faria diferente agora.

## Parte 3 — Cenário de war room com o seu projeto
Um alerta às 2h da manhã. Primeira ação nos 30 segundos, quais logs, com qual filtro, que hipóteses.

## Parte 4 — Autoavaliação honesta
O que você sustenta com segurança, o que ainda é frágil, o que estudaria em seguida.
```

## O exame final

Se o roadmap tem Modo Sabotagem, a última fase termina com **war room ao vivo às cegas**, na infraestrutura real do projeto: **três incidentes consecutivos, cada um dentro do timebox**, com relatório completo. Esse é o momento em que o checklist final do `README.md` deixa de ser teórico.
