# Site FNB Advocacia — Fabrícia Novaes Barcellos

Site institucional em página única (one-page), feito em HTML/CSS/JS puro — sem
build, sem dependências de pacote. Abra `index.html` direto no navegador pra
ver, ou suba os arquivos num servidor/hospedagem.

## Estrutura

```
index.html          → o site inteiro (estrutura, estilo e interações)
assets/
  fabricia.jpg       → foto da Fabrícia (hero não usa foto; aparece na seção Equipe)
  edilania.jpg       → foto da Edilania (seção Equipe)
  vitoria.jpg        → foto da Terceira Ponte/Vitória, fundo do primeiro slide (hero)
  footer-logo.png    → logo "Fabrícia Novaes Barcellos — Advocacia", usada no
                       menu (topo) e no rodapé
extras/
  artigos-section-backup.html → seção "Artigos & publicações" completa (HTML +
                       CSS + JS), removida por enquanto porque só tinha textos
                       de exemplo. Tem instruções dentro do arquivo de como
                       recolocar quando houver artigos reais.
```

`index.html` referencia as imagens com caminho relativo (`assets/...`), então
**mantenha a pasta `assets` do lado do `index.html`** sempre que mover,
publicar ou copiar o projeto.

## Como editar

É um arquivo único, então é só abrir `index.html` em qualquer editor (VS Code,
ou o próprio Claude Code) e mexer. Está tudo comentado por seção com blocos
tipo `<!-- HERO -->`, `<!-- SOBRE -->`, `<!-- ÁREAS -->`, `<!-- EQUIPE -->`,
`<!-- FAQ -->`, `<!-- CONTATO -->`, `<!-- FOOTER -->` — procure pelo comentário
da seção que quer mudar.

O CSS fica todo dentro da tag `<style>` no `<head>`, organizado nos mesmos
blocos (`/* ── HERO ── */`, `/* ── EQUIPE ── */` etc.). O JS fica no final do
arquivo, antes de `</body>`.

### Paleta de cores (definida no topo do `<style>`, em `:root`)

| Variável | Cor | Uso |
|---|---|---|
| `--mauve` | marrom-malva médio | acentos, botões, textos de destaque |
| `--mauve-2` | malva claro | detalhes sobre fundo escuro |
| `--wine` | vinho/ameixa escuro | seção de Contato (bloco de destaque) |
| `--cream` | creme claro | fundo principal do site |
| `--paper` | quase branco | fundo de cards/seções alternadas |
| `--beige` | bege | fundo de seções alternadas |
| `--ink` | marrom bem escuro | texto principal |

Essa paleta foi tirada da identidade visual real da Fabrícia (cartão de
visita e posts do Canva dela) — qualquer cor nova que for usada, tente
manter dentro dessa família (tons de malva/vinho/creme), em vez de cores
fora da identidade.

### Fontes
`Playfair Display` (serifada, títulos) + `Inter` (texto). Carregadas via
Google Fonts no `<head>` — precisa de internet pra carregar; sem internet,
cai numa fonte padrão do sistema.

### Formulário de contato
Usa o serviço gratuito **FormSubmit** (`action="https://formsubmit.co/..."`),
sem precisar de backend. Na primeira mensagem enviada pelo site, quem
configurou o e-mail recebe um e-mail de confirmação do FormSubmit que precisa
aprovar uma vez — depois disso funciona liso.

### Seções com interação (JS)
- Menu mobile (hambúrguer)
- Scroll reveal (elementos aparecem suavemente ao rolar a página)
- Botão "voltar ao topo" e barra de progresso de leitura
- Acordeão em "Áreas de atuação" (clique pra abrir cada área)
- Acordeão do FAQ
- Cursor customizado (bolinha que segue o mouse — só em desktop)

## Publicar no ar

Esse projeto não depende de Node, build, nem framework — é só HTML estático.
Pra publicar:
1. Suba `index.html` e a pasta `assets/` (do jeito que estão aqui) para a
   raiz pública do domínio (`public_html`, `www`, ou o que a hospedagem usar)
   — por FTP, painel do registro.br, GitHub Pages, Vercel/Netlify (arrastando
   a pasta), etc. Qualquer hospedagem de arquivo estático serve.
2. Não precisa de `npm install`, build step nem servidor próprio.

## Pendências / próximos passos

- **Artigos**: a seção foi removida por enquanto (só tinha exemplos). Quando
  tiver textos reais, usar `extras/artigos-section-backup.html` como base —
  tem instruções de onde colar cada pedaço de volta no `index.html`.
- Qualquer alteração de texto, cor, foto ou seção nova: só pedir pro Claude
  Code continuar a partir daqui, usando este README como contexto do projeto.
