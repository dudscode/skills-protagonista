# Coleta de insumos

Cada fonte vira um Markdown na pasta do PDI. Transcreva com fidelidade: a análise vem depois, e a pessoa precisa conseguir conferir o que você leu.

## PDI anterior em `.pptx`

Não precisa de LibreOffice. Um `.pptx` é um zip de XML:

```bash
mkdir -p /tmp/pdi-pptx && cd /tmp/pdi-pptx && unzip -o -q "/caminho/PDI.pptx"
for f in $(ls ppt/slides/slide*.xml | sort -V); do
  echo "=== $f ==="
  python3 -c "
import re,sys
x=open('$f',encoding='utf8').read()
for p in re.findall(r'<a:p>.*?</a:p>',x,re.S):
    t=''.join(re.findall(r'<a:t>(.*?)</a:t>',p))
    if t.strip(): print(t)
"
done
```

Para manter a identidade visual, veja as cores mais usadas e o fundo:

```bash
grep -o '<a:srgbClr val="[^"]*"' ppt/slides/*.xml | sort | uniq -c | sort -rn | head
grep -o '<p:bg>.*</p:bg>' ppt/slides/slide1.xml | head -c 400
```

Tabelas de plano de ação ("Passo / O que preciso fazer / Quem pode me ajudar / Status") costumam vir com células vazias. Registre o vazio como vazio: status não preenchido é `A confirmar`, não `Em progresso`.

## PDF

Use a ferramenta de leitura de arquivos do seu agente. Para PDFs longos, leia em blocos de até 20 páginas.

## Fotos do feedback (HEIC, PNG, JPG)

Leia cada imagem com a ferramenta de leitura do seu agente, que precisa enxergar imagens, e transcreva **literalmente**, por dimensão. Mantenha a ordem do documento original. No topo do `feedback.md`, registre quem enviou, a data e de quais arquivos veio a transcrição.

Estrutura esperada de um feedback de banca ou calibração:

```markdown
# Feedback da banca

> Enviado por <papel> em <data>. Transcrito de <arquivos>.

## <Dimensão>
**Destaques:**
- ...
**Oportunidades:**
- ...

## Parecer final
...

## Plano de ação
### 1. <Tema>
- ...
```

## LinkedIn

Acesso anônimo é bloqueado (HTTP 999), então buscar a URL direto não funciona. Use a automação de navegador do seu agente, com a pessoa logada na conta **dela**, e só para o perfil **dela**.

1. Abra `https://www.linkedin.com/in/<slug>/` e extraia o texto da página: headline, sobre, destaques, atividades.
2. As seções completas ficam em páginas de detalhe. Abra cada uma, **espere uns 3 segundos** (o conteúdo carrega depois do HTML) e só então extraia o texto:
   - `/details/experience/`
   - `/details/education/`
   - `/details/certifications/`
   - `/details/skills/`
   - `/details/honors/`
   - `/details/languages/`
3. Se uma página vier só com o rodapé, ela não terminou de carregar. Espere e extraia de novo.
4. Feche a aba ao terminar.

O que levar para o `perfil-publico.md`: headline, localização, cargo atual, trajetória com datas, formação, certificações com data e emissor, seguidores, destaques com números de alcance, e competências.

Não colete dados de terceiros (visitantes do perfil, sugestões de conexão) nem mensagens.

Cuidados:
- A headline pode divergir das seções: "1x AWS Certified" sem certificado cadastrado. Pergunte.
- Seguidores de outras redes (Instagram, YouTube) não aparecem. Pergunte se ela quer incluir.
- Reconhecimentos internos (programas de alto desempenho, prêmios) às vezes aparecem só dentro da descrição das experiências.

## Cases já escritos

Se a pessoa tiver cases em HTML, Markdown ou documento, extraia o texto e mantenha a categoria original de cada um. Em HTML, remova `<script>` e `<style>` antes de tirar as tags:

```bash
python3 - <<'EOF'
import re, html
x = open('cases.html', encoding='utf8').read()
x = re.sub(r'<(script|style)[^>]*>.*?</\1>', '', x, flags=re.S)
x = re.sub(r'<br\s*/?>|</(p|div|li|h\d|tr|section|article)>', '\n', x)
t = html.unescape(re.sub(r'<[^>]+>', '', x))
print(re.sub(r'\n\s*\n+', '\n', re.sub(r'[ \t]+', ' ', t)))
EOF
```

Cases de negociação **perdida** e de "o que não funcionou" são tão valiosos quanto os de sucesso: viram material de ADR, de trade-off e de lição aprendida nos eixos.
