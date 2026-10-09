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
  publicacoes/       → fotos de capa das publicações (artigos, notas, eventos)
```

`index.html` referencia as imagens com caminho relativo (`assets/...`), então
**mantenha a pasta `assets` do lado do `index.html`** sempre que mover,
publicar ou copiar o projeto.

## Como editar

É um arquivo único, então é só abrir `index.html` em qualquer editor (VS Code,
ou o próprio Claude Code) e mexer. Está tudo comentado por seção com blocos
tipo `<!-- HERO -->`, `<!-- SOBRE -->`, `<!-- ÁREAS -->`, `<!-- EQUIPE -->`,
`<!-- FAQ -->`, `<!-- PUBLICAÇÕES -->`, `<!-- CONTATO -->`, `<!-- FOOTER -->` — procure pelo comentário
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
- Publicações: destaques, painel "Ver todas as publicações" (com filtro por
  tipo) e janela de leitura

## Publicações (artigos, notas e eventos)

A seção fica depois do FAQ. As 2 publicações mais recentes aparecem em
destaque; todas ficam no painel "Ver todas as publicações". Ao clicar, abre a
leitura com a foto de capa em cima, o texto e, no fim, quem escreveu (com foto
pequena à esquerda).

Os cartões são gerados a partir da lista `PUBLICACOES`, no `<script>` do fim do
`index.html`. Para publicar:
1. Coloque a foto de capa em `assets/publicacoes/` (ex.: `meu-artigo.jpg`,
   horizontal, de preferência ~1600×900). Sem capa, usa-se uma capa padrão na
   cor do site com o tipo da publicação.
2. Acrescente um item em `PUBLICACOES` seguindo o MODELO que está comentado
   lá (id, tipo, data, título, resumo, capa, autor, texto).
3. Autores ficam em `AUTORES` (logo acima) — para um novo autor, acrescente
   nome, cargo e foto.

Enquanto a lista estiver vazia, a seção e os links "Publicações" do menu e do
rodapé ficam escondidos automaticamente.

Cada publicação tem um link direto para compartilhar:
`https://fnblaw.com.br/#pub-<id>`.

## Publicar no ar

Esse projeto não depende de Node, build, nem framework — é só HTML estático.
Pra publicar:
1. Suba `index.html` e a pasta `assets/` (do jeito que estão aqui) para a
   raiz pública do domínio (`public_html`, `www`, ou o que a hospedagem usar)
   — por FTP, painel do registro.br, GitHub Pages, Vercel/Netlify (arrastando
   a pasta), etc. Qualquer hospedagem de arquivo estático serve.
2. Não precisa de `npm install`, build step nem servidor próprio.

## Pendências / próximos passos

- **Publicações**: a estrutura está pronta; falta cadastrar as primeiras
  publicações reais.
- Qualquer alteração de texto, cor, foto ou seção nova: só pedir pro Claude
  Code continuar a partir daqui, usando este README como contexto do projeto.
