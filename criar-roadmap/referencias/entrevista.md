# Entrevista

A avaliação escrita mede se a pessoa **reconhece** a resposta certa, com o editor aberto e tempo para pensar. A entrevista mede se ela **produz** a explicação do zero, para alguém que faz follow-up. É a habilidade de plantão e de banca.

## O que é o arquivo

O `entrevista.md` é um **prompt autocontido**: a pessoa cola num chat novo (outra sessão, outro modelo ou uma pessoa da área) e é entrevistada. Quem conduz não é você, e é isso que dá valor à medição.

Por padrão, é **instrumento de treino**: não entra no critério do bloco. A exceção é o módulo de consolidação ([checkpoints.md](checkpoints.md)), em que a entrevista **é** a avaliação, com o critério escrito antes.

## Estrutura

```markdown
# Entrevista — <Bloco>: <temas>

> ⚪ Este arquivo não é critério de avaliação. É instrumento de treino: um prompt para colar num chat novo.

## Como usar
1. Abra um chat novo, em outra sessão ou outro modelo. Pode ser também uma pessoa da área.
2. Cole tudo o que está dentro do bloco PROMPT.
3. Responda do zero, falando ou escrevendo, sem consultar nada.
4. Cole o relatório final na seção Rodadas.

### Três regras que só dependem de você
- Não cole nenhum arquivo do roadmap nesse chat.
- Não consulte nada durante.
- 🔴 Faça depois de <marco prático do bloco>. Antes disso mede leitura, não prática.

**Duração esperada:** 40 a 50 minutos, <N> temas.

## PROMPT — copie daqui até o fim do arquivo
<o prompt, ver abaixo>

## Rodadas
### ⬜ Rodada 1 — pendente
```

## O prompt

### Papel
Uma pessoa sênior da área entrevistando para a vaga-alvo, com o contexto do time descrito de forma **genérica** (tipo de sistema, plataforma, se há plantão). Diga de onde a pessoa candidata vem e **"não presuma nada além disso: descubra"**.

### Regras de condução (inclua todas)
1. **Uma pergunta por vez.** Espere a resposta. Nunca despeje uma lista.
2. **Nunca dê a resposta durante.** Nem confirme, nem corrija, nem diga "isso mesmo". Todo o feedback vem no relatório.
3. **Cave o "e daí".** Quando a resposta descrever o quê e onde mas não a consequência: *"e daí? o que isso muda para quem está de plantão às três da manhã?"*.
4. **Não aceite nome sem mecanismo.** Se ela citar um termo, peça para explicar como funciona por baixo.
5. 🔴 **Registre o inverso: mecanismo sem nome.** Se ela descrever certo sem o termo técnico, não corrija e não entregue o nome. Anote com a citação literal.
6. **No máximo 2 follow-ups por tema**, e até 4 no tema de diagnóstico.
7. 🔴 **Cubra todos os temas.** Se o tempo apertar, encurte os não bloqueantes, nunca os bloqueantes.
8. **Tema não perguntado é ⬜ NÃO MEDIDO, jamais 🔴.**
9. **Se ela travar**, siga com naturalidade, registre e não dê dica.
10. **Se ela discordar com argumento**, explore e registre.
11. **Tom profissional e cordial, sem elogios.**

### Os temas
De 6 a 8 temas por bloco. Marque com ⚠️ os **bloqueantes**. Para cada tema:
- a pergunta de abertura;
- **"Procure por:"** o que uma resposta sólida contém (mecanismo **e** consequência);
- **o caso que separa:** uma situação em que a resposta decorada falha;
- **o follow-up que mede.**

Se o bloco tiver diagnóstico, inclua um tema de **diagnóstico ao vivo**: um sintoma, e a pessoa conduz. O que se mede é o **método por hipótese**:

> *"Se **X** for verdade, eu veria **Y**. Se eu não vir **Y**, descarto **X**."*

Se ela listar lugares ("olharia o log, o cache, a API"), o entrevistador faz **uma** intervenção: *"escolha um e me diga o que espera encontrar se a suspeita estiver certa, e o que veria se estiver errada."* Se ela continuar listando, esse é o achado do tema.

### O relatório final (obrigatório, formato fixo)

```markdown
# Relatório da entrevista — <tema> — <data>

**Duração aproximada:**
**Impressão geral em 3 linhas:** <sem elogio genérico>

## Placar por tema
| # | Tema | Nível | Justificativa em uma linha |
|---|------|-------|----------------------------|

- 🟢 **Sólido** — explicou o mecanismo e a consequência, sem ajuda
- 🟡 **Reconhece** — sabe o nome e quando usar, travou no porquê ou no efeito
- 🔴 **Frágil** — não soube, ou a resposta está conceitualmente errada
- ⬜ **Não medido** — não chegou a ser perguntado

## Nome sem mecanismo
## Mecanismo sem nome  ← a seção mais importante
## O teste da hipótese
## Citações literais que valem registro
## Erros conceituais  ← só aqui o entrevistador corrige
## Discordâncias com argumento
## Se eu fosse contratar
## Os 3 pontos para estudar antes da próxima conversa
```

## Quando a pessoa colar o relatório

1. Cole o relatório inteiro em *Rodadas*, com a data.
2. Compare com as rodadas anteriores: o que subiu, o que caiu, o que ficou.
3. **"Mecanismo sem nome"** é o achado mais barato de corrigir: dê o nome no `feedback.md`.
4. Um tema 🟡 que se repete em várias rodadas é dívida: amarre-o a um critério nomeado de um bloco futuro.
5. Padrão comum: o que foi corrigido explicitamente num feedback sobe na rodada seguinte, e o que não foi corrigido cai.
