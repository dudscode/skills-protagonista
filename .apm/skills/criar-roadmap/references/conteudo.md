# O contrato do `conteudo.md`

O `conteudo.md` **não é um roteiro de implementação**. É a base de estudo: o conceito e a aplicação no mesmo lugar. Se ele só diz *o que fazer*, falhou. Quem estuda para entender e evoluir, e não para executar passo a passo, trava quando a teoria falta, busca por fora, e o resumo vira a investigação do que o conteúdo omitiu.

## Os quatro blocos, nesta ordem

| Ordem | Bloco | O que tem que responder |
|---|---|---|
| 1 | 🧠 **Conceito** | **O que a peça é**, que papel ocupa num sistema maior, **por que existe** e o que quebraria sem ela. De onde vem o nome, quando o nome confunde. Trade-offs reais, com os nomes próprios (o padrão, o princípio, a patologia). |
| 2 | 📚 **Para aprofundar** | Documentação oficial e material externo, para ir além. Nunca para substituir o que devia estar no bloco 1. |
| 3 | 🔨 **No projeto** | A prática, apresentada como **consequência** da teoria. O código fica aqui, e agora se sabe por que ele é assim. |
| 4 | ✅ **Você entendeu se** | Cobra **raciocínio conceitual**, não execução. Ruim: *"sabe rodar com o profile de produção"*. Bom: *"sabe apontar qual linha faz o papel X e qual faz o papel Y, e por que nenhuma faz o papel Z"*. |

O 🧠 Conceito não pode ser uma frase justificando o passo seguinte. Se a seção manda adicionar uma dependência, o conceito explica o que ela é, que papel ocupa e quem faz o papel vizinho.

## Três regras que vêm junto

1. **Nome depois do problema.** Nenhum padrão, serviço ou ferramenta entra pelo nome. Entra pelo problema que o fez existir, e sai com o custo de usá-lo.
2. **Ponte com o que já se sabe.** Com a área de origem da pessoa, e depois cada etapa com a anterior. Nomear a repetição (o health check que reaparece como probe, o loop de reconciliação que reaparece no GitOps) vale mais que a peça isolada.
3. **Buscar por fora é lacuna do conteúdo, não falha de quem estuda.** Quando acontecer, reconheça o que a pessoa trouxe de certo e corrija o `conteudo.md` primeiro.

## Os marcadores

Use-os a partir do momento em que o conteúdo passar a ter código para colar:

| Marcador | O que significa |
|---|---|
| 🚧 **ESQUELETO** | O bloco está incompleto **de propósito**, e o que falta está dito logo abaixo. Colar como está produz defeito. |
| ✅ **COMPLETO** | Pode colar: é a forma que vai para produção. |
| 🔬 **Prove** | Comando mais saída esperada. Vem ao lado do ✅ *Você entendeu se*, não no lugar dele: um mede a explicação, o outro mede o sistema. |
| ⚠️ **Onde isto encosta em…** | A interação com algo que a pessoa já construiu. **Os bugs moram aqui**, não dentro de cada tópico isolado. |

Por que existem: se o conteúdo traz código incompleto sem avisar, a pessoa copia o defeito para o projeto e o defeito "vem pronto". E sem 🔬 dá para passar em todos os checkpoints de compreensão com o sistema quebrado.

## Esqueleto de uma seção

```markdown
### N. <O conceito, formulado como ideia, não como tarefa>

🧠 **Conceito** — <A pergunta anterior: o que é isso? Que problema existia antes? Quem faz o quê?>

#### <Subtópico que o conceito precisa para ficar de pé>
<Explicação com analogia se ajudar, e o termo técnico depois do comportamento.>

📚 **Para aprofundar** — [Documentação oficial](...) · [Artigo](...)

🔨 **No projeto** — <O que construir, como consequência do que foi explicado.>

<Código marcado como 🚧 ESQUELETO ou ✅ COMPLETO>

✅ **Você entendeu se** <consegue explicar X, e por que não Y>.

🔬 **Prove** — <comando>
Esperado: <saída>

#### ⚠️ Onde isto encosta em <peça anterior>
<A interação e o sintoma que ela produz quando dá errado.>
```

## Cabeçalho do arquivo

Todo `conteudo.md` abre com:
1. **Como este bloco funciona:** a tabela dos quatro blocos, em uma linha cada.
2. **Objetivo:** o que a pessoa vai conseguir fazer ao final.
3. **Mapa do bloco:** tabela com # | 🧠 Conceito | 🔨 Praticar | 📚 Estudar em.

## Material de estudo externo

Indique material real: documentação oficial, artigos, vídeos, cursos. Diga a ordem, e o que ler de cada um. Quando o material bom só existir em inglês e a pessoa preferir português, diga isso em vez de indicar material fraco em português.

## Game days guiados

Antes de a pessoa diagnosticar falhas às cegas (Modo Sabotagem), o conteúdo deve fazê-la **quebrar sabendo o que quebrou**: derrubar o cache, errar a porta, trocar o timeout, e observar o sintoma. Aprender a assinatura vem antes de reconhecer a assinatura.
