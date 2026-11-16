# K SKIN: site-catálogo

Site da K SKIN, loja de skincare coreano de Belo Horizonte (MG). Publicado em **https://kskinbr.com.br** pelo GitHub Pages.

Responda sempre em **português do Brasil**, com linguagem simples: a dona da loja não é programadora. Explique o que mudou em termos do site, sem jargão técnico.

## Como o site funciona

- É uma página estática: um único `index.html`, com o HTML, o CSS e o JavaScript juntos. Não tem build, framework, servidor nem banco de dados.
- O GitHub Pages publica a partir do branch **`main`**, na raiz. Uma mudança só vai ao ar depois que estiver no `main`, e leva de 1 a 2 minutos.
- Não há checkout nem pagamento no site. O cliente monta o pedido, e o botão "Enviar pedido pelo WhatsApp" abre a conversa com a lista, o frete e o total já escritos.

## Arquivos

- `index.html`: o site inteiro
- `CNAME`: contém `kskinbr.com.br`. **Nunca apagar nem alterar**, ou o domínio para de funcionar.
- `img/`: `capa-m.jpg` (foto da capa) e uma foto por produto, cada uma com o `id` do produto no nome (ex.: `centella-toner.jpg`). As fotos são JPG quadrados de 480×480.

## Onde editar o conteúdo

Quase tudo fica no `<script>` do `index.html`, entre `/* ===== Edite aqui ===== */` e `/* ===== Fim da edição ===== */`:

- `WHATSAPP`: número da loja (`5531975632275`) e `MSG_GERAL`
- `ORIGEM_UF` e `FRETE`: tabela de frete por região, saindo de MG. `eco` = PAC, `exp` = SEDEX, no formato `[preço, "prazo em dias úteis"]`. `local` vale para dentro de MG.
- `FRETE_GRATIS_ACIMA`: valor mínimo para PAC grátis (`0` = desligado)
- `SECTIONS`: as 9 seções, na ordem da rotina coreana (01 Limpeza, 02 Tônico, 03 Pads, 04 Séruns, 05 Hidratantes, 06 Protetor solar, 07 Máscaras, 08 Patches, 09 Aparelhos)
- `PRODUCTS`: cada produto com `id`, `sec`, `brand`, `name`, `vol`, `price` e `desc`. A ordem dentro de cada seção é do mais vendido para o menos vendido.
- `KIT`: produtos do botão "Adicionar uma rotina da manhã"

Para incluir um produto: adicione-o em `PRODUCTS` e a foto em `img/<id>.jpg`. O índice e a navegação são gerados sozinhos a partir de `SECTIONS` e `PRODUCTS`.

Textos fixos (capa, boas-vindas, rotina sugerida, frete, "Como comprar", rodapé) ficam no HTML.

## Identidade visual

- Sempre no **tema claro**: fundo creme `#FEFAF0`, texto `#2B2723`, dourado `#A97C2E`, amarelo-manteiga `#F8EEC9`. As cores ficam como variáveis no `:root`.
- Fontes: Source Serif 4 nos títulos e preços, Inter nos textos (Google Fonts).
- Selo redondo amarelo-manteiga com a letra "K" e uma estrela dourada de 4 pontas.
- Produtos em linha: foto à esquerda; marca, nome, volume e descrição; "VALOR" com linha pontilhada até o preço.
- Tom dos textos: próximo e carinhoso, sem exageros.

## Cuidados

- Teste no tamanho de celular (cerca de 390 px de largura): a maioria das clientes acessa pelo celular. Nada pode rolar para os lados.
- Depois de editar o JavaScript, confira que ele continua sem erros (por exemplo, extraia o `<script>` e rode `node --check`).
- Não mexa no DNS nem no domínio. Eles ficam na Hostinger e já estão corretos (4 registros A para o GitHub e `www` como CNAME para `jvmmsalles-cmd.github.io`).
- Os valores de frete são estimativas dos Correios. O site avisa que o valor exato é confirmado no WhatsApp.
- Não adicione pagamento com cartão no site. Se a dona pedir, explique que precisa de um provedor (Mercado Pago, PagBank) ou de uma plataforma de loja.
