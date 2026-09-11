---
name: criar-pdi
description: Monta um PDI (Plano de Desenvolvimento Individual) de carreira em tecnologia como página index.html navegável, a partir do PDI anterior, do feedback formal (banca, avaliação, calibração), do perfil do LinkedIn e dos cases da pessoa. Gera balanço do plano anterior, três espelhos, análise SWOT com cruzamento TOWS, eixos com sinal de sucesso mensurável, roadmap de 12 meses e cases no método STAR. Use quando alguém pedir para criar, revisar ou atualizar um PDI, montar cases STAR, fazer SWOT de carreira ou transformar feedback de promoção em plano de ação.
---

# Criar PDI

Esta skill conduz a pessoa do material bruto (PDI antigo, feedback, LinkedIn, cases) até um `index.html` com 11 seções, no formato de apresentação. O PDI resultante é dela: o seu papel é organizar, cruzar e apontar lacunas, **nunca inventar evidência**.

Leia as referências conforme avança:
- [referencias/coleta.md](referencias/coleta.md): como extrair texto de pptx, pdf, fotos e LinkedIn.
- [referencias/entrevista-star.md](referencias/entrevista-star.md): perguntas para montar cases quando a pessoa não tem.
- [referencias/secoes.md](referencias/secoes.md): o que vai em cada seção e as regras de cada uma.
- [template.html](template.html): o esqueleto visual. Copie, não reescreva o CSS.

## Regras que valem para tudo

1. **Não invente.** Número, status, data ou nome que não veio de uma fonte vira `A confirmar` e entra na lista de perguntas do final. Um PDI com lacuna honesta vale mais que um PDI bonito e falso: quem avalia vai perguntar.
2. **Hipótese é marcada como hipótese.** Toda leitura sua que não está registrada em uma fonte (ex.: "risco de ser vista como evangelista") leva a etiqueta `hipótese` na página.
3. **Pessoas por papel.** Em "quem pode me ajudar", use papéis (gestor, arquiteto, principal engineer). Só use nomes que a própria pessoa escreveu, e pergunte antes.
4. **Stack é o que a pessoa usa no dia a dia.** Ferramenta que ela só estudou ou certificou vai em Certificações, não em Stack.
5. **Certificação ambígua se pergunta.** "1x AWS Certified" não diz qual. Pergunte o nome exato antes de marcar como feito.
6. **Previsto não é realizado.** Economia "prevista", resultado sem método de medição ou elo causal não medido (ex.: TTM → NPS) vira um "Para fortalecer" no case.
7. **Feedback formal é citado, não parafraseado para mais forte.** Use as palavras de quem avaliou nas citações de cada eixo.
8. **Escreva em português do Brasil**, com acentuação correta, frases curtas e voz ativa.

## Fluxo

### 1. Entender o momento

Pergunte, numa mensagem só:
- Cargo atual e cargo alvo. O PDI é para **chegar** à cadeira ou para **sustentar** uma cadeira recém-conquistada? Isso muda o objetivo e o tom da capa.
- Quais insumos existem: PDI anterior, feedback formal, URL do LinkedIn, cases já escritos, plano de estudos em andamento.
- Onde salvar a pasta do PDI.

Não bloqueie esperando todos os insumos. Com o feedback e o LinkedIn já dá para começar; o resto entra como `A confirmar`.

### 2. Coletar e transcrever

Siga [referencias/coleta.md](referencias/coleta.md). Salve cada fonte como Markdown na pasta do PDI, para que a pessoa revise o que você leu antes de você analisar:

| Arquivo | Conteúdo |
|---|---|
| `feedback.md` | Transcrição fiel do feedback formal, por dimensão, com destaques, oportunidades, parecer e plano de ação |
| `perfil-publico.md` | Headline, cargo, trajetória, formação, certificações, comunidade, stack |
| `pdi-anterior.md` | Texto do PDI antigo, slide a slide (se existir) |
| `cases.md` | Cases STAR (os que ela trouxe ou os da entrevista do passo 3) |

Mostre um resumo curto do que encontrou e do que faltou antes de seguir.

### 3. Completar os cases

Se a pessoa não tem cases STAR, ou tem sem números, conduza a entrevista de [referencias/entrevista-star.md](referencias/entrevista-star.md). Faça poucas perguntas por vez. Cases são a matéria-prima das seções 3, 6 e 10, então vale o tempo.

### 4. Analisar

Antes de escrever HTML, monte a análise em texto e mostre à pessoa:
- **Balanço:** cada item do PDI anterior com status e evidência.
- **Três espelhos:** o que se repete entre autoavaliação, pares e avaliação formal (padrão), e o ponto cego (o que ela via como força e a avaliação separou).
- **SWOT com TOWS:** quatro quadrantes com evidência e o cruzamento em quatro movimentos.
- **Eixos:** um por pedido do feedback formal, mais um para as oportunidades comportamentais repetidas.

Pergunte se ela discorda de alguma hipótese. Ajuste e só então gere a página.

### 5. Gerar o `index.html`

Copie [template.html](template.html) para a pasta do PDI como `index.html` e preencha seção a seção, seguindo [referencias/secoes.md](referencias/secoes.md). Os comentários `<!-- REPETIR -->` marcam blocos que se duplicam por item. Remova seções sem conteúdo em vez de deixá-las vazias, e remova da legenda de status os que não forem usados.

Mantenha o CSS e o script do template. A paleta pode mudar (as variáveis estão no `:root`) se a pessoa quiser a identidade visual dela.

### 6. Verificar

A extensão do Chrome não abre `file://`. Sirva a pasta e confira as seções mais densas (balanço, espelhos, SWOT, eixos, STAR):

```bash
python3 -m http.server 8765 --bind 127.0.0.1   # em background
```

Navegue com ←/→. Confira também a largura de celular: tudo deve virar uma coluna. Derrube o servidor ao terminar.

### 7. Fechar

Entregue:
- O caminho do `index.html` e como navegar (←/→, bolinhas, Cmd+P para PDF).
- A lista do que ficou `A confirmar` e das hipóteses, para ela validar com o gestor.
- Os "Para fortalecer" dos cases: quais números levantar antes da próxima avaliação.

Se a pasta for um repositório git, pergunte antes de subir. O feedback formal e as fotos costumam ser informação interna: confirme que o repositório é **privado** (`gh repo view --json visibility`) antes de qualquer push.
