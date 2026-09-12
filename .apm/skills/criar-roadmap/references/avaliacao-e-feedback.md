# Avaliação, code review e feedback

Três arquivos por bloco, com papéis diferentes:

| Arquivo | Papel | Quem escreve |
|---|---|---|
| `avaliacao.md` | O freio: perguntas com critério, antes de avançar | A skill, na criação do bloco |
| `code-review.md` | Critérios de revisão do código do bloco | A skill, na criação do bloco |
| `feedback.md` | A correção, e depois o histórico das rodadas | A skill, depois de cada entrega |

## `avaliacao.md`

Estrutura (template em [../templates/bloco/avaliacao.md](../templates/bloco/avaliacao.md)):

- **Pré-requisito no topo:** o link do repositório ou o caminho da pasta. Sem isso, nem avaliação nem code review.
- **Parte 0 — Resumo:** pede o `resumo.md` entregue, **sem critério de conteúdo**. Ele é da pessoa. Nunca liste seção vazia como pendência.
- **Parte 1 — Decisões de design:** situações com trade-off ("um colega sugeriu logar o corpo inteiro da request, você concorda?"). É aqui que mora tudo o que precisa ser medido.
- **Parte 2 — Cenário:** logs, métricas ou sintomas reais para diagnosticar, com perguntas em sequência: o que aconteceu, por quê, o que você reportaria, o que investigaria.
- **Parte 3 — Mostre o projeto:** tarefas com evidência colada (comando e saída).
- **Critérios de aprovação** explícitos no fim.

Regras:
- **Resposta certa sem justificativa não passa.**
- Pergunte a **consequência**, não só o mecanismo: *"e daí? o que isso muda para quem está de plantão?"*.
- Dívidas herdadas de blocos anteriores entram como **critério obrigatório nomeado**, com link para a origem.
- Pelo menos uma pergunta por bloco em que "depende" é a resposta certa, e o que se cobra é **do que** depende.

## `code-review.md`

Critérios agrupados por tema, cada um com severidade:

| Severidade | Significado |
|---|---|
| 🔴 **Blocker** | Não avança sem corrigir: segurança, comportamento incorreto, arquitetura quebrada |
| 🟡 **Warning** | Não bloqueia, mas precisa ser corrigido antes de produção: má prática, risco latente |
| 🟢 **Sugestão** | Clareza e qualidade, opcional |

O code review **não** avalia perfeição, estilo pessoal sem impacto nem funcionalidade fora do escopo. **Sempre** avalia segurança (dado sensível em log, exceção exposta ao cliente), correção, clareza ("um colega entenderia em 5 minutos?") e consistência com o que o roadmap já ensinou.

Rode o código antes de revisar sempre que possível. Revisão sem rodar deixa passar o sistema que parece pronto e não está.

## `feedback.md`

### A primeira avaliação

```markdown
# Feedback — <Bloco>

**Data da avaliação:** DD/MM/AAAA
**Resultado:** Aprovada | Aprovada com ressalvas | Precisa de nova rodada

## Leitura completa considerada
- `anotacoes.md` — <lido / vazio>
- `resumo.md` — <entregue>
- `avaliacao.md` — <respondida>

## O que já está sólido
<O que a pessoa pode parar de estudar. Com citação literal quando houver.>

## Pontos de atenção + perguntas de aprofundamento
🔴 <Blocker — responder antes de continuar>
🟡 <Warning — responder para consolidar>
🟢 <Sugestão>

## Code review
<Achados por severidade, com arquivo e linha>

## Perguntas obrigatórias
<Lista consolidada, numerada>

## Pode continuar?
<Sim / Responda X antes / Não — corrija Y antes>
```

### As rodadas seguintes

O `feedback.md` é **histórico**: nunca reescreva blocos anteriores. Cada nova resposta da pessoa vira um bloco datado no fim:

```markdown
---
# 🔁 <O que foi respondido> — DD/MM/AAAA

## 🟢 O que está certo
> *"<citação literal>"*
<Por que está certo e o que isso destrava.>

## ⚠️ O que corrigir
> *"<citação literal>"*
<O conceito correto. Se a própria fala dela já contém a correção, mostre isso.>

## Status das perguntas
- [x] P1 — respondida
- [ ] P3 — ainda aberta
```

Quando a pessoa responder uma pendência, registre direto no `feedback.md` e siga a conversa. Parar para perguntar "quer que eu registre?" a cada resposta interrompe o raciocínio dela.

### O tom

- **Primeiro o que está certo, com citação.** Um feedback que só lista falhas faz a pessoa sentir que não evolui mesmo quando evolui rápido.
- **Corrija explicitamente.** O que você corrige sobe na rodada seguinte, e o que você deixa passar cai.
- **Mecanismo sem nome não é erro.** Se ela descreveu certo sem o termo técnico, dê o nome e diga que o raciocínio estava lá.
- **Discordância com argumento conta como acerto.** Se ela estiver certa, diga que está e o que muda no roadmap.
- **Se a lacuna era do conteúdo, diga.** Se ela buscou fora algo que o `conteudo.md` devia ter explicado, não rotule como erro dela: corrija o conteúdo.
- Sem elogio genérico. Elogie o raciocínio específico, com a frase dela.
