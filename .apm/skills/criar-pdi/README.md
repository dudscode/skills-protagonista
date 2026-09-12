# Skill `criar-pdi`

Uma skill de agente, para qualquer harness que leia skills, para montar o seu PDI (Plano de Desenvolvimento Individual) como uma página `index.html` navegável. Ela parte do seu material bruto e chega a um plano com evidência:

- **Balanço** do PDI anterior: o que andou, o que travou e com qual evidência.
- **Três espelhos:** autoavaliação, pares e avaliação formal, com o que se repete e o ponto cego.
- **Análise SWOT** com cruzamento TOWS (atacar, defender, evoluir, proteger).
- **Eixos de ação**, cada um com um sinal de sucesso mensurável.
- **Roadmap** de 12 meses em três fases.
- **Cases no método STAR**, com os números e o que falta medir.

## O que você precisa ter

Nada é obrigatório, mas quanto mais, melhor:

| Insumo | Formato |
|---|---|
| PDI anterior | `.pptx`, `.pdf` ou texto |
| Feedback formal (banca de promoção, avaliação, calibração) | Texto, PDF ou fotos |
| Perfil do LinkedIn | URL. Precisa de automação de navegador no seu agente, com você logado |
| Cases que você já escreveu | Qualquer formato. Se não tiver, a skill entrevista você |
| Plano de estudos em andamento | Opcional, para ancorar os eixos |

## Instalação

Com o [apm](https://github.com/microsoft/apm):

```bash
apm install dudscode/skills-protagonista --skill criar-pdi
```

Ou copiando a pasta para onde o seu agente lê skills (`.agents/skills/` na maioria, `.claude/skills/` no Claude Code):

```bash
mkdir -p .agents/skills && cp -R criar-pdi .agents/skills/
```

O [README do repositório](../../../README.md) tem as duas formas em detalhe.

## Uso

No seu agente, dentro da pasta onde quer o PDI:

```
/criar-pdi
```

Ou peça em linguagem natural: "quero montar meu PDI com base no feedback da minha banca".

A skill pergunta o seu momento (chegar à cadeira ou sustentá-la), coleta e transcreve as fontes para você revisar, completa os cases, mostra a análise antes de gerar a página e, no fim, lista o que ficou **a confirmar**.

## O que ela promete não fazer

- **Não inventa números, status nem datas.** O que não tem fonte vira "A confirmar".
- **Marca como hipótese** toda leitura que não está registrada numa fonte.
- **Não coleta dados de terceiros** no LinkedIn, só o seu próprio perfil.
- **Não sobe nada** para repositório sem perguntar, e verifica se o repositório é privado antes.

## Estrutura

```
criar-pdi/
├── SKILL.md                   # o fluxo e as regras
├── template.html              # esqueleto visual (11 seções, responsivo, exporta PDF)
└── references/
    ├── coleta.md              # extrair pptx, pdf, fotos e LinkedIn
    ├── entrevista-star.md     # perguntas para montar cases com número
    └── secoes.md              # o que vai em cada seção
```

## Navegando no PDI gerado

- **←/→:** avança ou volta uma seção.
- **Bolinhas na lateral:** pulam direto para uma seção.
- **Cmd+P (ou Ctrl+P):** exporta PDF, uma seção por página.
- **Celular:** tudo vira uma coluna só.
