# Modo Sabotagem

## Por que existe

Os exercícios do roadmap ensinam a **construir**. Numa war room ninguém entrega o bug: chega um sintoma ("saldo desatualizado", "erro 503 intermitente") e é preciso montar a história pelas evidências. Diagnosticar um problema **que você não sabe qual é** usa um músculo diferente de consertar um bug que você mesma escreveu.

No Modo Sabotagem, a skill atua como mentora: injeta falhas escondidas no projeto da pessoa, e ela diagnostica como se estivesse de plantão.

Só faz sentido se o roadmap tiver um projeto prático. Gere o `modo-sabotagem.md` do roadmap a partir desta referência, com o calendário adaptado.

## Regra de ouro

Primeiro a pessoa **quebra sabendo o que quebrou** (game days guiados no `conteudo.md`) para aprender a assinatura de cada sintoma. Só depois vem a sabotagem às cegas. Aprender a assinatura, depois reconhecer a assinatura.

## O protocolo

### 1. Preparação
O projeto precisa estar **funcionando e commitado** na branch principal. Se não estiver, recuse e diga por quê: sabotar um sistema já quebrado mistura as falhas e anula o exercício.

### 2. O pedido
A pessoa pede: *"Aplique uma sabotagem nível N. Não me diga o que fez."*

O que a skill faz:
1. Cria a branch `sabotagem/<tema-neutro>` a partir da principal.
2. Injeta **de 1 a 3 falhas realistas** do nível pedido: coisas que acontecem em produção de verdade e produzem **sintomas observáveis**. Nada de pegadinha esotérica.
3. Commita com **mensagem neutra**, que não revela a falha (ex.: "ajustes de configuração").
4. Deixa a stack de pé com os sintomas ativos, se for possível.
5. Entrega **só o alerta**, como num plantão real, no topo do `war-room-log.md`.
6. **Nunca revela as falhas**, nem por insinuação, até o relatório estar escrito.

### 3. O alerta

```markdown
## 🚨 Plantão — Sabotagem NN

**Alerta HHhMM — <N> reclamações na fila de atendimento.**

<O sintoma do ponto de vista do usuário ou do monitor. Pode ser parcial: "não é todo mundo e não é sempre".>

<Um detalhe de contexto que parece pista e pode ou não ser: "a monitoração está toda verde", "ninguém subiu deploy hoje".>

<A pressão real: "o atendimento quer saber se pode dizer que o app está fora do ar".>

### Setup (isto não é o enigma, é o ambiente)
- Branch, como subir, portas, o que já está rodando.
- **Ruído pré-existente que NÃO é sabotagem:** declare qualquer defeito que já existia na branch limpa.
- "Não vou dizer quantas falhas são. Entre 1 e 3, como sempre."

### Regras do jogo
- **Permitido:** <as ferramentas do nível: logs, curl, health, cliente do cache, CLI da nuvem>, e ler o código-fonte (numa war room real se lê código).
- **Proibido até fechar o diagnóstico:** `git diff`, `git log -p`, `git show` ou qualquer comparação com outra branch. É o gabarito.
- **Timebox:** 30 a 45 minutos.
- **Gabarito, só depois do relatório escrito:** `git diff <principal>`.
```

### 4. O relatório (obrigatório antes do gabarito)

A pessoa escreve no `war-room-log.md`:

```markdown
## Incidente <data> — <título curto>
- **Sintoma:** o que foi reportado
- **Hipóteses levantadas:** em ordem, inclusive as descartadas
- **Evidências:** logs e comandos que confirmaram ou descartaram cada hipótese
- **Causa raiz:** o que estava errado, e em qual camada
- **Correção:** o que mudou
- **Prevenção:** o que impediria isso de chegar em produção (teste, alerta, validação)
- **Dicas usadas:** nenhuma / 1 / 2 / 3
- **Tempo:** <minutos>
```

### 5. Se ela travar: dicas em estágios

Uma de cada vez, só quando pedida. Cada dica usada entra no relatório.
1. **Em qual camada** está o problema (código, configuração, infraestrutura).
2. **Qual ferramenta** revelaria a evidência.
3. **Qual componente** olhar.

### 6. A revisão, como post-mortem

Depois do relatório e do gabarito:
- **As evidências sustentam a causa raiz?** Achar o bug por sorte não conta.
- **As hipóteses foram testáveis?** "Se X, eu veria Y" é hipótese. "Olhei o log, depois o cache" é lista de lugares, e é o achado mais comum a corrigir.
- Ela achou **todas** as falhas? Uma correção que mascara a segunda falha conta como não achada.
- A correção introduziu regressão? Rode os cenários de aceite de novo.
- A prevenção é concreta (qual teste, qual alerta) ou genérica?
- Registre a revisão no `feedback.md` do bloco.

## Níveis

| Nível | Camada | Categorias de falha (exemplos) | Quando usar |
|---|---|---|---|
| 1 | Código | Bug de lógica, status code errado, header não propagado, exceção engolida, ordem errada entre dois componentes | Depois da primeira etapa com código |
| 2 | Configuração e infra local | Variável de ambiente, porta, profile, hostname de dependência, chave ou TTL de cache, timeout do proxy | Depois de o projeto rodar em contêiner |
| 3 | Plataforma | Health check errado, limite de memória, permissão da tarefa, service discovery, tag de imagem inexistente, rollout que não completa | Depois da etapa de infraestrutura |

Ajuste as categorias à stack do roadmap. Escolha o que a pessoa **vai** encontrar na vida real, não o que é difícil só por ser difícil.

## Calendário

Monte uma tabela no `modo-sabotagem.md` do roadmap, com: momento, nível, projeto-alvo e, opcionalmente, o foco da rodada (ex.: "diagnóstico só por logs"). O padrão:

| Momento | Nível |
|---|---|
| Fim da etapa em que o projeto passa a rodar localmente | 1 e 2 |
| Depois do cache ou da camada de dados | 2, com foco no tema |
| Depois da observabilidade | 2, diagnóstico só por logs |
| Durante a etapa de infraestrutura | 3 |
| Exame final do projeto integrador | 3, às cegas, **três war rooms consecutivas dentro do timebox** |
