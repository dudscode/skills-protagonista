# Estrutura do roadmap

## A árvore

```
roadmap/
├── README.md                  # objetivo, arquitetura-alvo, etapas, contrato do conteúdo, checklist final
├── progresso.md               # checkboxes + decisões datadas no topo
├── modo-sabotagem.md          # protocolo (se houver projeto)
├── decisao-<tema>.md          # registro de cada premissa que mudou
├── diagnostico-<periodo>.md   # checkpoints de evolução
│
├── etapa-1-<tema>/
│   ├── README.md              # objetivo da etapa, por que ela é crítica, o que muda a partir dela
│   ├── PLANO.md               # opcional: execução dia a dia com critério de aceite
│   ├── apostila-*.md/.pdf     # opcional: aprender e revisar
│   └── bloco-1-2-<tema>/      # semanas 1–2
│       ├── conteudo.md        # o que estudar, pelo contrato
│       ├── anotacoes.md       # espaço livre da pessoa
│       ├── resumo.md          # da pessoa, nunca critério
│       ├── avaliacao.md       # o freio: perguntas com critério
│       ├── code-review.md     # critérios 🔴🟡🟢 (se houver código)
│       ├── entrevista.md      # prompt para chat novo + rodadas
│       ├── feedback.md        # correção + blocos datados
│       └── war-room-log.md    # relatórios de sabotagem, quando houver
│
├── etapa-N-<tema>/ …
├── modulo-consolidacao/       # quando for preciso parar e consolidar
│
└── projeto-integrador/
    ├── README.md              # cenário, restrições, fases
    ├── code-review-regras.md
    ├── fase-N.md
    ├── fase-N-code-review.md
    ├── fase-N-feedback.md
    └── avaliacao-final.md     # a defesa
```

Nomeie as pastas pelo tema (`mes-3-cache-observabilidade`, `semana-3-4-logs`), não só pelo número: fica navegável no GitHub.

## O `README.md` do roadmap

1. **Objetivo:** uma frase com o papel-alvo e o que a pessoa vai conseguir fazer.
2. **Arquitetura que você vai encontrar:** um diagrama ASCII do caminho real (ex.: `borda → gateway → balanceador → contêiner → serviço → cache`), com os timeouts ou limites relevantes. Genérico se for interno.
3. **Tabela de etapas:** etapa, tema e **foco verbal**.
4. **Projeto integrador:** fases e em que etapa cada uma acontece.
5. **Como usar:** a ordem, quais etapas são independentes, quando começa a sabotagem.
6. **O contrato do `conteudo.md`** (ver [conteudo.md](conteudo.md)).
7. **Checklist final:** competências **observáveis**. Ruim: "sabe Redis". Bom: "sabe quando um dado veio do cache e como forçar atualização".
8. **Fora do escopo:** o que não entra, e por quê.

Quando uma premissa mudar, acrescente um aviso datado no topo (`> 🔁 Atualizado em <data>: ...`) com link para o registro da decisão.

## O `README.md` de cada etapa

- **Objetivo da etapa** e **por que ela é crítica**, com as perguntas reais que ela responde (ex.: "o que os logs estão dizendo?").
- **O que muda a partir desta etapa**, se o formato evoluiu (novos marcadores, novas regras).
- **Interações já mapeadas:** os pontos onde o conteúdo novo encosta no que já existe. Os bugs moram aí.
- **Dívidas herdadas:** as que viraram critério obrigatório desta etapa, com link.
- **Tabela dos blocos** e **o que você vai conseguir fazer ao final**.

## O `progresso.md`

```markdown
# Progresso

Use [ ] para pendente e [x] para concluído.

> 🔁 **Decisão de <data>:** <o que mudou no plano e por quê, com link>

## Etapa 1 — <tema>

### Bloco 1–2: <tema>
- [ ] Estudou o conteúdo
- [ ] Fez os exercícios práticos
- [ ] Avaliação concluída — <aprovada em DD/MM/AAAA | aprovada com ressalvas>

**Pendências carregadas** (ver `feedback.md`):
- [ ] <pendência> → <onde ela vai ser cobrada>
- [x] <pendência> → **pago em DD/MM** por <evidência>
- ⛔ <item> → **cancelado**: <motivo e data>
```

Três regras:
- Pendência nunca some: é paga (com evidência), cancelada (com motivo) ou amarrada a um critério futuro nomeado.
- Decisão que muda o plano entra no topo, datada, e não reescreve o histórico abaixo.
- Um item "aprovado com ressalvas" aponta para as ressalvas.

## Quando detalhar cada etapa

Gere a Etapa 1 completa na criação. As seguintes nascem com o `README.md` e o esboço do conteúdo, e são detalhadas quando a pessoa estiver a um bloco de chegar. O que ela aprender e errar nas primeiras etapas deve mudar as últimas: é para isso que existem o feedback e o diagnóstico.
