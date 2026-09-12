# Checkpoints

O roadmap é um plano vivo. Três instrumentos mantêm o plano honesto: o **diagnóstico**, o **módulo de consolidação** e o **registro de decisão**.

## Diagnóstico

### Quando
- A cada duas etapas.
- Quando a pessoa disser algo como *"acho que estou evoluindo pouco"* ou *"estou só seguindo o roadmap"*.
- Quando as dívidas de uma etapa passarem de um punhado.

### Base
Leia tudo antes de escrever: todos os `feedback.md`, `avaliacao.md`, `anotacoes.md`, `resumo.md`, os `war-room-log.md` e o código (**rodando**, não só lido).

### Estrutura do `diagnostico-<periodo>.md`

1. **Resposta direta à pergunta da pessoa**, com evidência em ordem de data:

   | Data | O que aconteceu | O que isso exigia |
   |---|---|---|
   | <data> | <fato do arquivo, com número> | Reconhecer conceitos |
   | <data> | <fato> | Diagnosticar e generalizar |

   A coluna da direita mostra a **subida de exigência**, que é a evolução real.

2. **Por que ela sente diferente**, se sentir. Causas comuns: o feedback só mostra o que falta; o formato mede reconhecer e não produzir; a dificuldade sobe junto com a competência.
3. **O que o método errou.** Admita as falhas do roadmap e do feedback. Conteúdo que entregou código com defeito pronto é falha do conteúdo.
4. **O que já está sólido: pode parar de estudar.**
5. **Os gaps recorrentes**, com contagem de ocorrências e severidade. Ex.: *"🔴 Verificação: 7 ocorrências"*.
6. **Inventário honesto das dívidas.**
7. **Autoavaliação:** perguntas para a pessoa se medir sozinha.
8. **Mudanças de processo** que ela vai dirigir, não só seguir.
9. **Conteúdo para revisar**, priorizado pelos gaps.
10. **Resumo em cinco linhas.**

## Módulo de consolidação

### Quando
Quando o diagnóstico mostrar que o chão não está firme: muitas dívidas técnicas abertas, projeto quebrado, ou a sensação correta da pessoa de que está avançando sem consolidar. **A decisão de parar é dela.** Apresente as opções (acumular e seguir, ou parar e consolidar) com o custo de cada uma.

### Formato

```
Fase 1 (corrigir)  ──►  Fase 2 (estudar)  ──►  Fase 3 (entrevista)  ──►  encerramento
```

- **Fase 1 — Corrigir:** cada dívida do projeto com **critério de aceite verificável** (comando e saída). Não vale "corrigi", vale colar a evidência. Corrigir antes de estudar faz o estudo render mais, porque a pessoa chega ao conceito já tendo apanhado dele.
- **Fase 2 — Estudar:** o que estudar e, principalmente, **o que ela precisa conseguir explicar** ao fim de cada tema.
- **Fase 3 — Entrevista:** aqui a entrevista **é** a avaliação ([entrevista.md](entrevista.md)), conduzida por um chat que não é você. Várias rodadas são normais.

### O critério de saída é escrito antes

No `README.md` do módulo, antes de começar, escreva **"Como este módulo termina"**, com critérios numéricos. Por exemplo: todos os 🔴 da Fase 1 fechados com evidência, zero 🔴 nos temas bloqueantes da entrevista, e X temas 🟢. Isso impede que alguém decida no fim, pelo cansaço.

### O encerramento

Se o módulo fechar sem bater o critério, e a pessoa decidir seguir, pode ser aceitável desde que:
- o projeto esteja corrigido com evidência;
- **cada dívida restante vire critério obrigatório de um ponto nomeado** de um bloco futuro, com link, e não lembrete;
- a decisão fique registrada no `feedback.md` do módulo e no topo do `progresso.md`.

Quando a pessoa chegar a esses pontos, cobre a dívida. Não deixe passar em silêncio.

## Registro de decisão

Quando uma premissa do roadmap mudar (a stack do time, o prazo, o objetivo, uma orientação nova do mentor), escreva um `decisao-<tema>.md`:

```markdown
# Decisão — <o que muda>

**Data:** DD/MM/AAAA
**Decisão dela.** Registro escrito com a análise de impacto que a antecedeu.

## O que mudou
<A premissa antiga, com a citação da fonte original, e a nova.>

## O que se ganhou
## O que se perdeu — registrado para não virar surpresa
## O efeito no roadmap
<Quais etapas mudam, quais saem, quais viram outra coisa. Nada some sem destino.>
```

Depois, acrescente o aviso `> 🔁 Atualizado em <data>` no `README.md` do roadmap e nas etapas afetadas, com link para o registro.

A premissa mudou, então o roadmap é que estava desatualizado. Não é a pessoa que precisa se adaptar ao plano velho.
