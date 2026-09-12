# Skill `criar-roadmap`

Uma skill do [Claude Code](https://claude.com/claude-code) para montar **e conduzir** um roadmap de estudos de carreira. O roadmap não é genérico: parte do seu contexto real, é validado por um mentor e tem critérios que impedem você de se enganar sobre o próprio progresso.

## O que ela faz

**Na criação:**
- pede os insumos certos, inclusive a orientação do seu mentor, colada literalmente;
- faz perguntas de calibragem antes de montar qualquer coisa;
- monta etapas mensais com foco progressivo (*entender → rodar → diagnosticar → operar → decidir e defender*), em blocos de duas semanas;
- desenha um projeto integrador com restrições reais, que obrigam a decidir;
- gera as perguntas para você levar ao mentor antes de começar.

**Na condução:**
- avalia cada bloco, faz o code review e escreve o feedback, mostrando o que já está sólido e não só o que falta;
- gera um prompt de **entrevista** para você colar num chat novo e treinar explicar do zero;
- roda o **Modo Sabotagem**: injeta falhas às cegas no seu projeto e revisa o seu relatório como um post-mortem;
- faz **diagnósticos** de evolução, propõe **módulos de consolidação** quando o chão não está firme e registra as **decisões** quando a premissa muda.

## O que você precisa ter

| Insumo | Obrigatório? |
|---|---|
| Seu papel atual e o objetivo concreto | Sim |
| O que você domina, conhece raso e nunca viu | Sim |
| A orientação de alguém que vive o contexto-alvo (mentor, especialista, liderança) | Muito recomendado |
| Gaps conhecidos: feedback, avaliação, banca, PDI | Recomendado |
| Horas por semana, prazo e onde praticar | Sim |
| Um projeto seu que possa evoluir | Opcional |

Se você fez o seu PDI com a skill [`criar-pdi`](../criar-pdi/), os eixos dele entram direto como gaps.

## Instalação

Com o [apm](https://github.com/microsoft/apm):

```bash
apm install dudscode/skills-protagonista --skill criar-roadmap --target claude
```

Ou copie a pasta `criar-roadmap` para `~/.claude/skills/`. O [README do repositório](../../../README.md) tem as duas formas em detalhe.

## Uso

```
/criar-roadmap
```

Ou em linguagem natural: *"quero montar um roadmap para migrar de frontend para backend em 6 meses"*.

Depois, no dia a dia:

| Você diz | A skill faz |
|---|---|
| "Terminei o bloco X, me avalie" | Avaliação, code review e feedback |
| "Aplique uma sabotagem nível 2" | Injeta de 1 a 3 falhas às cegas e entrega só o alerta |
| "Acho que não estou evoluindo" | Diagnóstico com evidência em ordem de data |
| "O time trocou de plataforma" | Registro de decisão e ajuste do roadmap |

## Estrutura

```
criar-roadmap/
├── SKILL.md                        # os dois modos, os princípios e os fluxos
├── references/
│   ├── insumos.md                  # questionário, calibragem, perguntas para o mentor
│   ├── estrutura.md                # árvore do roadmap, README, progresso
│   ├── conteudo.md                 # o contrato: 🧠 📚 🔨 ✅ + 🔬 ⚠️ 🚧
│   ├── avaliacao-e-feedback.md
│   ├── entrevista.md
│   ├── projeto-integrador.md
│   ├── modo-sabotagem.md
│   ├── checkpoints.md              # diagnóstico, consolidação, registro de decisão
│   └── apoio.md                    # apostilas e plano dia a dia
└── templates/bloco/                # os arquivos de cada bloco
```

## O que ela promete

- Não monta roadmap genérico: sem insumo, ela pergunta.
- Não trata o seu `resumo.md` e as suas anotações como formulário.
- Não revela as falhas da sabotagem antes do seu relatório.
- Não coloca informação interna da sua empresa no roadmap: isso fica com o mentor.
