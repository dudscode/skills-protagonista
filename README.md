# skills-protagonista

Skills do [Claude Code](https://claude.com/claude-code) para quem quer **conduzir a própria carreira em tecnologia**, em vez de esperar que ela aconteça. Cada skill transforma material bruto (feedback, PDI, orientação de mentor, LinkedIn, cases) num plano com evidência, e depois ajuda a executar esse plano.

Elas não entregam plano genérico. Partem do seu contexto, perguntam quando falta informação e marcam como hipótese o que não tem fonte.

---

## Skills disponíveis

| Skill | Para quê | Entrega |
|---|---|---|
| [`criar-pdi`](.apm/skills/criar-pdi/) | Montar ou revisar o seu PDI a partir do feedback formal, do LinkedIn e dos seus cases | Uma página `index.html` com balanço, três espelhos, SWOT, eixos com sinal mensurável, roadmap de 12 meses e cases STAR |
| [`criar-roadmap`](.apm/skills/criar-roadmap/) | Montar e conduzir um roadmap de estudos validado por mentor | Uma pasta com etapas, blocos (conteúdo, avaliação, entrevista, feedback), projeto integrador e Modo Sabotagem |

### Como elas se conectam

```
feedback formal ─┐
LinkedIn ────────┼──►  criar-pdi  ──►  eixos com sinal mensurável
cases ───────────┘                             │
                                               ▼
orientação do mentor ───────────────►  criar-roadmap  ──►  estudo, avaliação, sabotagem
                                               │
                                               ▼
                                   evidência para o próximo PDI
```

O PDI diz **o que** desenvolver. O roadmap diz **como** estudar e **como provar** que aprendeu. As evidências do roadmap alimentam o balanço do PDI seguinte.

---

## Instalação

### Com o apm (recomendado)

O [apm](https://github.com/microsoft/apm), o Agent Package Manager, instala e atualiza as skills sem você copiar pasta nenhuma. Este repositório é um pacote apm: tem `apm.yml` na raiz e as skills em `.apm/skills/`.

Instale o apm, se ainda não tiver:

```bash
brew install apm                        # macOS
curl -sSL https://aka.ms/apm-unix | sh  # Linux, ou macOS sem Homebrew
irm https://aka.ms/apm-windows | iex    # Windows, no PowerShell
```

Depois, na pasta do projeto onde você quer as skills:

```bash
# as duas skills
apm install dudscode/skills-protagonista --target claude

# uma skill só
apm install dudscode/skills-protagonista --skill criar-pdi --target claude
```

O apm baixa o pacote em `apm_modules/` e publica as skills em `.claude/skills/`, que é de onde o Claude Code as lê. Ele também cria um `apm.yml` e um `apm.lock.yaml` no seu projeto, para a instalação ser reproduzível, e acrescenta `apm_modules/` ao seu `.gitignore`.

Para fixar uma versão, aponte para a tag: `dudscode/skills-protagonista#v1.0.0`.

Se o seu projeto já tem um `apm.yml`, declare como dependência e rode `apm install`:

```yaml
dependencies:
  apm:
    - dudscode/skills-protagonista
```

**Atualizar:** `apm install --update`. **Remover:** `apm uninstall skills-protagonista`.

> A opção `--skill` existe nas versões novas do apm. Se o seu reclamar dela, rode `apm update` antes.

### Sem o apm, copiando as pastas

As skills do Claude Code ficam em `~/.claude/skills/` (para você, em qualquer projeto) ou em `.claude/skills/` dentro de um projeto.

```bash
git clone https://github.com/dudscode/skills-protagonista.git

# as duas, para você
mkdir -p ~/.claude/skills
cp -R skills-protagonista/.apm/skills/criar-* ~/.claude/skills/

# uma só
cp -R skills-protagonista/.apm/skills/criar-pdi ~/.claude/skills/

# ou só num projeto
mkdir -p .claude/skills
cp -R skills-protagonista/.apm/skills/criar-roadmap .claude/skills/
```

**Atualizar:** `git pull` no clone e copie de novo.

Para conferir, de qualquer uma das formas: abra o Claude Code e digite `/`. As skills aparecem na lista.

### Requisitos

| Requisito | Quando |
|---|---|
| [Claude Code](https://claude.com/claude-code) | Sempre |
| [`apm`](https://github.com/microsoft/apm) | Opcional: instalar e atualizar as skills sem copiar pasta |
| Extensão Claude in Chrome, logada na sua conta do LinkedIn | `criar-pdi`, para ler o seu perfil |
| `python3` | Para extrair texto de `.pptx` e servir a página localmente |
| `pandoc` e Google Chrome | `criar-roadmap`, só se quiser apostilas em PDF |
| `git` e `gh` | Se quiser versionar o PDI ou o roadmap no GitHub |

---

## Uso

No Claude Code, dentro da pasta onde quer o resultado:

```
/criar-pdi
/criar-roadmap
```

Ou peça em linguagem natural: *"quero montar meu PDI com o feedback da minha banca"*, *"me ajuda a montar um roadmap para virar backend em 6 meses"*. A skill certa é acionada pela descrição.

---

## Glossário

Os termos que aparecem nas skills e nos arquivos que elas geram.

### Carreira e PDI

| Termo | O que é |
|---|---|
| **PDI** | Plano de Desenvolvimento Individual: onde você está, onde quer chegar, e como vai provar a evolução |
| **Banca / avaliação formal** | O processo em que outras pessoas avaliam você para uma promoção ou nível. O feedback dela é o insumo mais forte do PDI |
| **Balanço** | A seção que confronta o PDI anterior com o que aconteceu, item a item, com evidência |
| **Três espelhos** | Autoavaliação, visão dos pares e avaliação formal lado a lado. O que aparece nos três é padrão, não percepção |
| **Ponto cego** | O que você via como força e a avaliação separou ou contradisse |
| **SWOT** | Forças e fraquezas (internas), oportunidades e ameaças (do contexto) |
| **TOWS** | O cruzamento dos quadrantes do SWOT em ações: atacar (S×O), defender (S×T), evoluir (W×O) e proteger (W×T) |
| **Eixo** | Uma frente do plano de ação, ligada a um pedido do feedback |
| **Sinal mensurável** | Um resultado que outra pessoa consegue verificar. "Estudar X" não é sinal; "3 decisões registradas e revisadas por um arquiteto" é |
| **STAR** | Situação, Tarefa, Ação e Resultado: o formato para contar um case com impacto |
| **Para fortalecer** | O número ou o elo que falta para um case mostrar impacto medido, e não estimado |
| **Hipótese** | Uma leitura sem fonte registrada. Aparece marcada, para você validar |
| **A confirmar** | Um dado sem fonte. Nunca vira "feito" por suposição |
| **ADR** | Architecture Decision Record: um registro curto de uma decisão técnica, com contexto, opções, trade-offs e como reverter |

### Roadmap e estudo

| Termo | O que é |
|---|---|
| **Etapa** | Um mês do roadmap, com um foco verbal (entender, rodar, diagnosticar, operar, defender) |
| **Bloco** | Duas semanas dentro de uma etapa, com os mesmos arquivos: conteúdo, anotações, resumo, avaliação, code review, entrevista e feedback |
| **Contrato do conteúdo** | A ordem obrigatória de cada seção de estudo: 🧠 Conceito → 📚 Para aprofundar → 🔨 No projeto → ✅ Você entendeu se |
| **Nome depois do problema** | Nenhuma ferramenta entra pelo nome: entra pelo problema que a fez existir, e sai com o custo de usá-la |
| **🔬 Prove** | Um comando mais a saída esperada: evidência de que o sistema funciona, e não só de que você sabe explicar |
| **⚠️ Onde isto encosta** | A interação entre uma peça nova e uma que já existe. Os bugs moram aí |
| **🚧 Esqueleto / ✅ Completo** | Marca se um código do conteúdo pode ser colado como está ou está incompleto de propósito |
| **Reconhecer × produzir** | Marcar a resposta certa é diferente de explicar do zero para alguém que faz follow-up. A entrevista mede o segundo |
| **Entrevista** | Um prompt que você cola num chat novo para ser entrevistada sem consulta. Gera um relatório com placar por tema |
| **Nome sem mecanismo** | Usar o termo técnico certo sem saber explicar como funciona |
| **Mecanismo sem nome** | Explicar certo como algo funciona sem saber o termo técnico. É o gap mais barato de fechar |
| **🔴 🟡 🟢** | Blocker (não avança sem corrigir), warning (corrigir antes de produção) e sugestão |
| **Dívida** | Algo que ficou para trás. Nunca some: é paga com evidência, cancelada com motivo ou amarrada a um critério futuro |
| **Projeto integrador** | Um projeto que atravessa várias etapas, com restrições reais que obrigam a decidir e justificar |
| **Avaliação final de defesa** | Você sustenta as decisões do seu projeto, em vez de produzir mais código |

### War room e diagnóstico

| Termo | O que é |
|---|---|
| **War room** | A sala, real ou virtual, onde um incidente de produção é investigado sob pressão |
| **Plantão** | A escala de quem responde aos incidentes fora do horário |
| **Game day** | Quebrar o sistema de propósito, **sabendo** o que quebrou, para aprender a assinatura de cada sintoma |
| **Modo Sabotagem** | O Claude injeta de 1 a 3 falhas escondidas no seu projeto e entrega só o alerta. Você diagnostica às cegas, dentro de um timebox |
| **Níveis de sabotagem** | 1 = código, 2 = configuração e infraestrutura local, 3 = plataforma |
| **War-room-log** | O arquivo em que você escreve o relatório do incidente antes de ver o gabarito |
| **Gabarito** | O `git diff` da branch sabotada. Olhar antes do relatório anula o exercício |
| **Diagnóstico por hipótese** | *"Se X for verdade, eu veria Y. Se não vir Y, descarto X."* O contrário de listar lugares onde olhar |
| **Post-mortem** | A revisão do incidente depois de resolvido: as evidências sustentam a causa raiz? |

### Checkpoints

| Termo | O que é |
|---|---|
| **Diagnóstico** | Um relatório periódico de evolução, com evidência em ordem de data, o que está sólido e os gaps recorrentes |
| **Módulo de consolidação** | Uma parada para corrigir, estudar e ser entrevistada antes de avançar, com o critério de saída escrito antes |
| **Registro de decisão** | Um arquivo que documenta por que uma premissa do roadmap mudou, o que se ganhou e o que se perdeu |

---

## Princípios comuns

Todas as skills do repositório seguem:

1. **Contexto real, nunca plano genérico.** Sem insumo, a skill pergunta.
2. **Não inventa.** Número, status ou data sem fonte vira "a confirmar".
3. **Hipótese é marcada.** O que é leitura da skill aparece identificado.
4. **Evidência, não relato.** O que conta é o que dá para verificar.
5. **O que é seu não é formulário.** Resumo e anotações pessoais nunca viram critério.
6. **Informação interna fica fora.** Nome de sistema e arquitetura fechada da sua empresa não entram no que a skill gera.
7. **Pergunta antes de publicar.** Nada vai para um repositório sem você confirmar, e feedback interno só vai para repositório privado.

---

## Contribuindo

Sugestões e novas skills de carreira são bem-vindas: abra uma issue ou um PR.

O repositório é um pacote apm:

```
skills-protagonista/
├── apm.yml                  # o manifesto do pacote
└── .apm/skills/
    ├── criar-pdi/
    │   ├── SKILL.md         # frontmatter com name e description
    │   ├── README.md        # para humanos
    │   ├── references/      # o que a skill lê conforme avança
    │   └── template.html
    └── criar-roadmap/
        ├── SKILL.md
        ├── README.md
        ├── references/
        └── templates/
```

Uma skill nova entra em `.apm/skills/<nome>/`, com o `SKILL.md` cujo `name` é igual ao nome da pasta. Suba a `version` do `apm.yml` e acrescente a skill à tabela e ao glossário deste README.

Criado por [@dudscode](https://github.com/dudscode).
