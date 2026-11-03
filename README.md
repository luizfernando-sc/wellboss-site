# Landing page WellBoss (site de venda)

Site estático em `https://wellboss.com.br`, **fora do app Base44** (o app fica em `https://app.wellboss.com.br`).
Um arquivo (`index.html`) + `assets/`. Não tem build, não tem dependência.

| Arquivo | Para quê |
|---|---|
| `index.html` | A página (textos, estilo e o script da barra do celular) |
| `assets/` | Logos, favicon e capturas de tela |
| `.htaccess` | HTTPS obrigatório, sem www, cache, atalhos `/entrar` e `/cadastro` |
| `robots.txt`, `sitemap.xml` | Google |

- Base de texto: `WellBoss_Landing_Page_Estrutura_e_Textos.docx` (02/11/2026).
- Todo CTA leva ao cadastro do app: `https://app.wellboss.com.br/register`. Se o endereço mudar, troque em todos os `href` que começam com `https://app.wellboss.com.br`.
- Parâmetros `utm_*` da URL da landing são repassados ao link de cadastro.

## Publicar (Base44, app separado)

O site roda no Base44, num app **separado** do app da WellBoss:

- App: **WellBoss Site** (`6aea5fab1d59da037d4f0bdb`), endereço interno `https://well-boss-site-7d4f0bdb.base44.app`.
- Domínio `wellboss.com.br` vinculado a esse app. DNS fica no Registro.br, sem trocar nameservers:

| Tipo | Nome | Valor |
|---|---|---|
| A | `wellboss.com.br` (raiz) | `216.24.57.1` |
| CNAME | `www` | `base44.onrender.com` |
| (o que já existe) | `app` | **não mexer**: é o app da WellBoss |

No Base44 o `index.html` fica na raiz do app e as imagens em `public/assets/` (caminhos começam com `/assets/`).
O `.htaccess` deste repositório só vale para hospedagem Apache (Hostinger); no Base44 ele é ignorado.

## Capturas de tela (pendente)

Coloque em `assets/telas/`, com estes nomes:

- `inicio.webp` — Início (aparece no topo e na seção "Como funciona")
- `clientes.webp` — Clientes
- `indicadores.webp` — Indicadores

Enquanto o arquivo não existir, a página mostra uma moldura neutra no lugar.

Regras: **só conta de demonstração** (nada de cliente real: é dado pessoal, LGPD), tema claro, ~1440×900, sem a barra do navegador (a página já desenha a moldura), nada de tela montada.
