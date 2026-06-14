# Protocolo Joelho Blindado

Produto pago (€19) do personal trainer Lucas Lima, hospedado 100% no **GitHub Pages** (nada no Netlify).

- **LP de vendas:** https://lucaslimaef.github.io/protocolo-joelho-blindado/
- **Acesso de quem comprou:** https://lucaslimaef.github.io/protocolo-joelho-blindado/acesso/
  - Senha: `forcanaodesgaste`
  - Redirect pós-compra do Stripe deve apontar pra: `…/acesso/?k=forcanaodesgaste` (destrava sozinho)

## O que tem no repo

- `index.html` — landing page de vendas (Pixel Performix + preços multimoeda EUR/USD/BRL).
- `acesso/index.html` — conteúdo do produto **criptografado** (AES-256-GCM). Só abre com a senha.
- `assets/` — imagens (avatar, provas, og-image, favicon).

> O conteúdo legível do produto **não** fica neste repo (o GitHub Pages publicaria tudo). A fonte privada está em `Desktop\Protocolo-Joelho-Blindado\protocolo-joelho-blindado-12-semanas.html`.

## Como atualizar o produto

1. Edite a fonte: `Desktop\Protocolo-Joelho-Blindado\protocolo-joelho-blindado-12-semanas.html`
2. Rode o gerador: `node "Desktop\Protocolo-Joelho-Blindado\gerar-protocolo-trancado.js"` (recria `acesso/index.html` criptografado)
3. `git add . && git commit -m "atualiza produto" && git push`

## Pendente

- Colar o link de pagamento do Stripe na `index.html` (procure por `STRIPE_LINK`). Enquanto vazio, o botão manda pro WhatsApp.
- Configurar no painel do Stripe o redirect pós-compra pra `…/acesso/?k=forcanaodesgaste`.
