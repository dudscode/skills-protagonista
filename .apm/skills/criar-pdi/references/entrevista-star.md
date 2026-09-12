# Entrevista para montar cases STAR

Use quando a pessoa não tem cases escritos, ou tem cases sem número. Pergunte **uma categoria por vez**, com duas ou três perguntas no máximo. Espere a resposta, escreva o case e mostre antes de passar à próxima.

## As categorias

Cubra pelo menos quatro. As duas últimas costumam ser esquecidas, e são as que mais mostram maturidade.

| Categoria | O que mostra | Pergunta de abertura |
|---|---|---|
| Realização mais significativa | Impacto e escala | Qual entrega você colocaria primeiro se só pudesse contar uma? |
| Iniciativa liderada | Protagonismo além do escopo | O que você começou sem ninguém pedir, e que outras pessoas adotaram? |
| Negociação | Influência | Quando você convenceu alguém a mudar uma decisão técnica ou de prioridade? |
| Resolução de conflito | Liderança de pessoas | Houve um conflito no time em que você foi ponte? |
| Repasse de conhecimento | Escala por meio de outros | Que conhecimento seu passou a existir sem você por perto? |
| Negociação perdida | Leitura de contexto | Qual proposta sua foi recusada, e por quê? |
| O que não funcionou | Trade-off e humildade técnica | Qual solução você propôs, descobriu que era errada e trocou? |

## Aprofundando cada letra

**S · Situação:** qual era o problema, para quem, e em que escala? Quantas squads, clientes ou transações?

**T · Tarefa:** o que era responsabilidade **sua**, e não do time?

**A · Ação:** o que você decidiu e que alternativa descartou? Com quem negociou? O que delegou?

**R · Resultado:** o que mudou, em número? Qual era o antes e qual é o depois?

## Caçando o número

Se o resultado vier só em palavras ("melhorou muito"), ofereça métricas candidatas e pergunte qual dá para levantar:

| Tipo de entrega | Métricas candidatas |
|---|---|
| Biblioteca ou componente reutilizável | Squads ou apps consumidores, tempo para usar, horas economizadas (usos × tempo poupado) |
| Modernização ou migração | % de telas ou jornadas migradas, custo desligado, incidentes antes e depois, tempo de build e deploy |
| Nova plataforma ou POC | Time to market antes e depois, áreas que adotaram, entregas em produção |
| Performance | LCP, INP e CLS no p75, taxa de erro, tempo de resposta |
| Regulatório | % de projetos adequados, antecedência em relação ao prazo |
| Conhecimento e comunidade | Participantes, recorrência, acessos à documentação, práticas adotadas depois |
| Pessoas | Mentorados promovidos ou reconhecidos, autonomia (antes precisava de ajuda para X, hoje não) |

Se não houver número disponível, escreva o case assim mesmo e registre em "Para fortalecer" qual número levantar e onde buscar.

## Sinais de alerta no resultado

Aponte quando aparecer, sem descartar o case:
- **Previsão apresentada como resultado:** "economia prevista de R$ X". Pergunte quanto já se realizou.
- **Percentual sem método:** "80% da área entende". Pergunte como foi medido.
- **Elo causal não medido:** "reduziu TTM, logo aumentou NPS". O TTM é fato, o NPS é hipótese.
- **Resultado do time atribuído só à pessoa:** pergunte qual parte foi dela.

## Formato do case no `cases.md`

```markdown
## <Categoria> · <Título curto>

**Números:** <até 3 métricas curtas, ex.: "3 h → 10 min", "12 squads">

- **S:** ...
- **T:** ...
- **A:** ...
- **R:** ...

**Para fortalecer:** <o número que falta ou o elo a medir>
```
