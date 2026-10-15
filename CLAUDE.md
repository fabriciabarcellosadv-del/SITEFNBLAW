# Site FNB Advocacia (fnblaw.com.br)

Site estático: `index.html` + imagens em `assets/`. Sem build.

## Publicação

- O Netlify (projeto `fnblaw`) publica automaticamente tudo o que chega ao ramo `main`.
  Só o que está no `main` vai ao ar.
- Ao terminar qualquer alteração pedida, publique: faça commit e leve a alteração
  para o `main` (`git push origin HEAD:main`, ou merge do ramo de trabalho no `main`
  seguido de `git push origin main`). Não deixe a alteração só num ramo `claude/...`.
- Antes de publicar, confira que toda imagem referenciada no `index.html` existe em `assets/`.
- Depois de publicar, avise que o site atualiza em cerca de 1 minuto em https://fnblaw.com.br.

## Conteúdo

- Imagens ficam em `assets/` (capas de artigos em `assets/publicacoes/`), nunca embutidas
  em base64 no `index.html`.
- As publicações (artigos, notas, eventos) são definidas na lista em JavaScript dentro do
  `index.html`; siga o modelo comentado ali.
