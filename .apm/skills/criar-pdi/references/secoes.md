# As 11 seções do PDI

A página conta uma história: **quem sou → de onde vim → como me veem → o que isso significa → para onde vou → como vou provar**. Cada seção tem um `id` no template. Mantenha a ordem.

## Legenda de status

| Classe | Rótulo | Quando usar |
|---|---|---|
| `s-ok` | Finalizado | Há evidência de conclusão |
| `s-wip` | Em progresso | Começou e há evidência parcial |
| `s-hold` | Em espera | Planejado, sem começar |
| `s-open` | Em aberto | O feedback formal repetiu um ponto que já estava no plano anterior |
| `s-check` | A confirmar | Sem fonte para decidir |

Tire da legenda os status que não aparecem na página.

---

## 1. Capa (`#capa`)
- Título "PDI <ano>", nome, e a transição de cargo: `<s>cargo anterior</s> → <b>cargo atual ou alvo</b>`.
- Uma frase que diga o modo do PDI: "Esta versão tem como objetivo chegar à cadeira" ou "...sustentá-la".

## 2. Quem sou (`#quem-sou`)
- Título: uma frase de identidade profissional, não o cargo. Ex.: "Engenheira de dados, indo do pipeline para a plataforma".
- Lista `kv`: Área, Formação, Destaque (reconhecimentos), Cases (os 3 ou 4 principais **com o número**), Pessoas (mentorias), Comunidade, Stack.
- Linha do tempo com o marcador `now` no cargo atual.
- Stack: só o que ela usa no dia a dia.

## 3. Balanço do PDI anterior (`#balanco`)
- Uma linha por item do plano antigo: objetivo, gaps, passos do plano de ação, itens do roadmap.
- Coluna Evidência: sempre uma fonte concreta (certificado, case, data, feedback). Sem fonte, o status é `A confirmar`.
- A frase de abertura resume o saldo, ex.: "O objetivo foi atingido. Os gaps que não andaram são os que a banca apontou".
- Sem PDI anterior, troque por "Ponto de partida": os gaps que a pessoa já reconhece, com o mesmo formato.

## 4. Três espelhos (`#espelhos`)
- Três colunas: **Como me vejo** (autoavaliação), **Como os pares me veem** e **Como a avaliação me viu** (banca ou calibração). A terceira tem destaque visual (`mirror banca`).
- Marque com `✦ repete` o que aparece em dois ou mais espelhos.
- Dois cards embaixo:
  - **O que se repete:** o padrão. Se aparece nos três, não é percepção.
  - **O ponto cego:** o que a pessoa via como força e a avaliação separou ou contradisse. É o insight mais valioso da página. Se não houver, remova o card, sem forçar.
- Com só dois espelhos, use `g2` e mantenha os cards.

## 5. Análise SWOT (`#swot`)
- Título: a tese da análise em uma frase.
- **Forças e Fraquezas** são internas. **Oportunidades e Ameaças** vêm do contexto: empresa, mercado, área, tecnologia.
- De 4 a 5 itens por quadrante, cada um com **evidência** (número, citação, fato). Item sem fonte leva `<span class="hyp">hipótese</span>`.
- Não repita a mesma coisa em dois quadrantes. Uma fraqueza pode virar ameaça só se o contexto a agravar (ex.: dependência de framework × IA barateando framework).
- **Cruzamento TOWS**, quatro cards, uma ação concreta cada:
  - S × O · **Atacar:** usar a força para pegar a oportunidade.
  - S × T · **Defender:** usar a força para neutralizar a ameaça.
  - W × O · **Evoluir:** usar a oportunidade para fechar a fraqueza.
  - W × T · **Proteger:** o que evitar ou limitar enquanto a fraqueza existe.

## 6. Parecer da avaliação (`#banca`)
- Um card por dimensão avaliada: ↑ destaque resumido e → oportunidade resumida.
- Parecer final parafraseado **sem suavizar nem agravar**.
- Sem avaliação formal, remova a seção e use os espelhos.

## 7. Objetivo (`#objetivo`)
- Uma frase grande, com as palavras-chave destacadas em `<em>`.
- Três perguntas: resultados que espero colher, alinhamento com o escopo e o que muda em relação ao PDI anterior.

## 8. Plano de ação (`#plano`)
- Um eixo por item do plano de ação do feedback formal. Mais um eixo "Impacto e influência" se as oportunidades comportamentais se repetirem nos espelhos.
- Cada eixo tem:
  - **Citação** do que a avaliação pediu (`.ask`).
  - **Três ações** concretas, de preferência ancoradas em cases reais (ex.: "ADR retroativo da proposta que não funcionou").
  - **Sinal** mensurável e verificável por outra pessoa. "Estudar X" não é sinal. "3 ADRs revisados por arquiteto" é.
  - **Quem ajuda**, por papel.
  - **Onde no plano de estudos**, se existir um.
  - **Status**.

## 9. Roadmap (`#roadmap`)
- Três fases com datas reais: até o próximo checkpoint, profundidade e decidir e defender (ou equivalente).
- Cada fase tem: onde quero chegar, sinais que consegui e quem pode me ajudar.
- Se houver checkpoint marcado pela avaliação, a fase 1 termina nele.

## 10. Entregas de sucesso (`#entregas`)
- Quatro cases principais em `star-card`, com `.nums` (até 3 métricas), S/T/A/R curtos e **Para fortalecer**.
- Três cards laterais, se houver material:
  - **Negociações:** ✓ ganhas e ✗ perdidas, com a lição da perdida.
  - **O que não funcionou:** vira ADR em um eixo.
  - **Pessoas:** conflitos mediados e mentorias com resultado.
- Link para o documento completo de cases, se existir.

## 11. Acompanhamento (`#acompanhamento`)
- Três cards de cadência: checkpoint (data), 1:1 (frequência) e mentoria técnica (quem, ou "A definir").
- Próximos passos numerados. Os primeiros são sempre os itens `A confirmar` e os números "Para fortalecer".

## Rodapé
Liste as fontes usadas.
