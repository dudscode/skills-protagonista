# Material de apoio

Material de apoio ajuda a pessoa a estudar. **Nunca vira critério de avaliação**, nem na `avaliacao.md` nem no `feedback.md`. Não pergunte se ela leu a apostila.

## Apostilas, opcionais

Úteis para quem estuda no celular ou em pedaços. Duas por etapa:

| | Para quê | Formato |
|---|---|---|
| **Apostila da etapa** | **Aprender** | Blocos ⏱ de 5 a 12 min. Cada bloco: analogia → o que é tecnicamente → exemplo do próprio código da pessoa → quadro 🗣 *"Explique em voz alta"* |
| **Apostila de revisão** | **Verificar** | Só as perguntas e as respostas modelo, para conferir **depois** de cada bloco, falando em voz alta |

Os temas da apostila acompanham os blocos do `PLANO.md` da etapa, com uma tabela de correspondência.

### Gerar o PDF

Com `pandoc` (Markdown → HTML) e um navegador headless (HTML → PDF), sem precisar de LaTeX. O exemplo usa o Chrome no macOS; Chromium e Edge aceitam as mesmas opções:

```bash
pandoc apostila.md --from=gfm --to=html5 --standalone --self-contained \
  --metadata title="Apostila — Etapa N" --css=estilo.css -o /tmp/apostila.html
"/Applications/Google Chrome.app/Contents/MacOS/Google Chrome" \
  --headless --disable-gpu --no-pdf-header-footer \
  --print-to-pdf=apostila.pdf "file:///tmp/apostila.html"
```

Em versões novas do pandoc, `--self-contained` virou `--embed-resources`. O PDF sai autocontido. Pergunte se a pessoa quer o CSS e o HTML intermediário no repositório: muitas preferem só o `.md` e o `.pdf`.

## `PLANO.md`, execução dia a dia (opcional)

Útil quando a etapa junta conteúdo e fases do projeto integrador, ou quando há atraso a recuperar.

- **Onde você está:** tabela do que já está pronto (✅) e do que falta (🔴), com evidência.
- **O material de estudo:** a apostila e a correspondência com os blocos.
- **A sequência, e por que ela é essa:**
  ```
  Bloco 0  <o que destrava o resto>   3 dias   ← por quê
  Bloco 1  <tema>                     4 dias
  ...
  ```
- **Cada dia** com o que fazer, **🔬 Aceite** (comando e saída esperada) e, quando houver, **🔴 a decisão a justificar**.
- **Alvo de conclusão** baseado no ritmo **medido** da pessoa (quantos dias ela levou nas etapas anteriores), não no ideal.
