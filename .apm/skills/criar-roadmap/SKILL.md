---
name: criar-roadmap
description: Cria e conduz um roadmap de estudos de carreira em tecnologia, feito a partir do contexto real da pessoa e validado por um mentor. Monta etapas mensais com blocos de estudo (conteúdo, avaliação, code review, entrevista, feedback), projeto integrador com restrições reais, Modo Sabotagem (falhas injetadas às cegas para treinar war room), diagnósticos periódicos e módulos de consolidação. Use quando alguém pedir para montar um roadmap ou plano de estudos, planejar uma transição de área, preparar-se para plantão ou war room, avaliar um bloco estudado, rodar uma sabotagem ou revisar o progresso de um roadmap.
---

# Criar roadmap

Esta skill tem dois modos. Descubra qual é antes de agir:

| Modo | Quando | Por onde começar |
|---|---|---|
| **Criar** | Não existe roadmap ainda | [Fluxo de criação](#fluxo-de-criação) |
| **Conduzir** | O roadmap existe e a pessoa quer estudar, ser avaliada, rodar sabotagem ou revisar o rumo | [Fluxo de condução](#fluxo-de-condução) |

No modo Conduzir, leia antes o `README.md`, o `progresso.md` e o `feedback.md` mais recente do roadmap. As decisões registradas ali valem mais do que as regras gerais desta skill.

## Referências

Leia a referência do passo em que estiver, não todas de uma vez:

| Referência | Para quê |
|---|---|
| [references/insumos.md](references/insumos.md) | O que perguntar antes de montar e o que levar ao mentor |
| [references/estrutura.md](references/estrutura.md) | Árvore de pastas e o papel de cada arquivo |
| [references/conteudo.md](references/conteudo.md) | O contrato do `conteudo.md` |
| [references/avaliacao-e-feedback.md](references/avaliacao-e-feedback.md) | Avaliação, code review e feedback |
| [references/entrevista.md](references/entrevista.md) | Como escrever o prompt de entrevista e o relatório |
| [references/projeto-integrador.md](references/projeto-integrador.md) | Projeto com restrições que forçam decisão |
| [references/modo-sabotagem.md](references/modo-sabotagem.md) | Protocolo das falhas às cegas e o war-room-log |
| [references/checkpoints.md](references/checkpoints.md) | Diagnóstico, módulo de consolidação e registro de decisão |
| [references/apoio.md](references/apoio.md) | Apostila e plano dia a dia |
| [templates/](templates/) | Esqueletos dos arquivos de cada bloco |

## Princípios

Valem para tudo o que a skill gera. Eles vêm de erros reais de roadmaps anteriores.

1. **Contexto real, nunca roadmap genérico.** Tudo parte dos insumos da pessoa. Se faltar insumo, pergunte. Não preencha com o que "normalmente se estuda".
2. **Validação com mentor antes da primeira linha de estudo.** É o que separa um plano bonito de um plano que faz sentido.
3. **Teoria antes da prática.** O `conteudo.md` explica o que a peça é e por que existe antes de mandar instalar. Quem estuda para entender trava quando o conteúdo só manda executar.
4. **Nome depois do problema.** Nenhum padrão ou ferramenta entra pelo nome: entra pelo problema que o fez existir e sai com o custo de usá-lo.
5. **Resposta certa sem justificativa não passa.** A avaliação cobra raciocínio.
6. **Evidência, não relato.** "Funcionou" não fecha nada: fecha o comando e a saída colados (🔬 Prove). Dá para passar em todo checkpoint de compreensão com o sistema quebrado.
7. **O que é da pessoa não é critério.** `resumo.md` e `anotacoes.md` são instrumentos dela. Nunca liste seção vazia como pendência. O que precisa ser medido vira pergunta na `avaliacao.md` ou na entrevista.
8. **Reconhecer não é produzir.** Marcar a alternativa certa e explicar do zero para alguém que faz follow-up são habilidades diferentes. A entrevista mede a segunda.
9. **Feedback mostra o que já está sólido.** Um feedback que só lista falhas faz a pessoa sentir que não evolui, mesmo quando evolui rápido. Diga também o que ela pode parar de estudar.
10. **O que você corrige explicitamente sobe, e o que você não corrige cai.** Não deixe erro conceitual passar em silêncio para ser gentil.
11. **Discordar com argumento conta como acerto.** Quando a pessoa contestar e estiver certa, aceite explicitamente e diga o que muda. Não recue em silêncio.
12. **Buscar por fora é lacuna do conteúdo.** Se a pessoa precisou pesquisar fora para entender, a correção começa no `conteudo.md`, não no feedback dela.
13. **Premissa mudou, roadmap muda.** Se a stack, o prazo ou o objetivo mudarem, registre a decisão e ajuste. Não force a pessoa a seguir um plano desatualizado.
14. **Informação interna fica com o mentor.** Nome de sistema, arquitetura fechada e biblioteca proprietária não entram no roadmap, que é compartilhável: viram categoria genérica.

## Fluxo de criação

### 1. Coletar os insumos
Use o questionário de [references/insumos.md](references/insumos.md). Peça numa mensagem só, agrupado. Os indispensáveis são:
- papel atual, objetivo concreto e o motivo (vaga, promoção, mudança de área, plantão);
- o que domina, o que conhece raso e o que nunca viu;
- **a orientação do mentor, colada literalmente**, sem reescrever;
- os gaps já conhecidos: feedback de avaliação, banca, nivelamento, entrevista. Se houver um PDI feito com a skill `criar-pdi`, os eixos dele são insumo direto;
- tempo por semana, prazo, orçamento e se há ambiente para praticar (local ou nuvem);
- como a pessoa aprende melhor (praticando, lendo, ditando).

### 2. Calibrar com perguntas
Antes de gerar qualquer arquivo, faça as perguntas de calibragem da referência: o nível real em cada tópico, o que priorizar e o que cortar. Não presuma.

### 3. Montar a v1
Siga [references/estrutura.md](references/estrutura.md):
- **Etapas mensais dependentes**, cada uma com um **foco verbal progressivo**, por exemplo: *entender → rodar e modificar → diagnosticar → operar → decidir e defender*. A última etapa é a de decidir e defender, e fica por último de propósito: ela cobra decisões sobre o que as anteriores construíram.
- **Blocos de duas semanas** dentro de cada etapa, com os arquivos de [templates/](templates/).
- **Projeto integrador** se o objetivo envolver construir algo ([references/projeto-integrador.md](references/projeto-integrador.md)).
- **Calendário do Modo Sabotagem** se houver projeto ([references/modo-sabotagem.md](references/modo-sabotagem.md)).
- **Avaliação final de defesa**, não de produzir mais código.
- **Fora do escopo explícito:** o que a pessoa não vai aprender, e por quê.
- **Checklist final** de competências observáveis ("sabe diagnosticar X pelo sintoma Y"), no `README.md`.

Gere primeiro o `README.md`, o `progresso.md` e a Etapa 1 completa. As etapas seguintes podem nascer com o `README.md` da etapa e os blocos só com o `conteudo.md` esboçado, e ser detalhadas quando a pessoa chegar nelas: o que ela aprender na Etapa 1 muda a Etapa 3.

### 4. Preparar a validação
Gere a lista de perguntas para o mentor ([references/insumos.md](references/insumos.md#perguntas-para-o-mentor)). Quando a pessoa voltar com o retorno, ajuste. Onde discordar do mentor, diga e explique o porquê, sem aceitar tudo automaticamente.

## Fluxo de condução

Identifique o pedido e siga a referência correspondente:

| A pessoa diz | O que fazer | Referência |
|---|---|---|
| "Terminei o bloco X", "me avalie" | Avaliar pela `avaliacao.md` do bloco, fazer o code review e escrever o `feedback.md` | [avaliacao-e-feedback.md](references/avaliacao-e-feedback.md) |
| Responde uma pergunta em aberto do feedback | Registrar como bloco datado no `feedback.md` e seguir, sem pedir licença a cada resposta | [avaliacao-e-feedback.md](references/avaliacao-e-feedback.md) |
| Cola um relatório de entrevista | Colar em *Rodadas* da `entrevista.md` e avaliar o placar | [entrevista.md](references/entrevista.md) |
| "Aplique uma sabotagem nível N" | Seguir o protocolo à risca, sem revelar as falhas | [modo-sabotagem.md](references/modo-sabotagem.md) |
| Entrega um relatório de war room | Revisar como post-mortem: a evidência sustenta a causa raiz? | [modo-sabotagem.md](references/modo-sabotagem.md) |
| "Acho que não estou evoluindo", ou fim de uma etapa com muitas dívidas | Fazer um diagnóstico e, se preciso, propor um módulo de consolidação | [checkpoints.md](references/checkpoints.md) |
| "Mudou a stack", "mudou o prazo" | Escrever o registro de decisão e ajustar o roadmap | [checkpoints.md](references/checkpoints.md) |
| "O conteúdo não explicou X" | Reescrever a seção do `conteudo.md` pelo contrato | [conteudo.md](references/conteudo.md) |
| "Quero uma apostila", "quero um plano dia a dia" | Gerar o material de apoio | [apoio.md](references/apoio.md) |

Ao fechar qualquer entrega, atualize o `progresso.md`, com as decisões novas datadas no topo.

## Git

Se o roadmap for um repositório, faça um commit por entrega, com mensagem que diga o porquê. Nunca reescreva histórico (amend em commit publicado, rebase, force push) sem a pessoa pedir essa operação especificamente. Pergunte uma vez como ela prefere o fluxo de push e PR, e siga isso.
