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

## Publicar (Hostinger)

Hospedagem: Hostinger, site `wellboss.com.br`, pasta `public_html`.

1. hPanel → Sites → wellboss.com.br → **Avançado → Git**.
2. Repositório `https://github.com/luizfernando-sc/wellboss-site.git`, branch `main`, diretório vazio (vai direto em `public_html`).
3. Repositório privado: copie a chave SSH que o hPanel mostra e cadastre em GitHub → repositório → Settings → Deploy keys (só leitura). Nesse caso use a URL `git@github.com:luizfernando-sc/wellboss-site.git`.
4. Clique em **Deploy**. Para atualizar depois: commit na `main` e Deploy de novo (ou ative o deploy automático com o webhook que o hPanel gera).

### Domínio: não derrubar o app

`app.wellboss.com.br` aponta para o Base44. Se os nameservers do domínio forem trocados para os da Hostinger, **recrie o registro DNS do `app` antes** (mesmo tipo e valor que está hoje no provedor atual), senão o app sai do ar. Anote o registro atual antes de mexer.

## Capturas de tela (pendente)

Coloque em `assets/telas/`, com estes nomes:

- `inicio.webp` — Início (aparece no topo e na seção "Como funciona")
- `clientes.webp` — Clientes
- `indicadores.webp` — Indicadores

Enquanto o arquivo não existir, a página mostra uma moldura neutra no lugar.

Regras: **só conta de demonstração** (nada de cliente real: é dado pessoal, LGPD), tema claro, ~1440×900, sem a barra do navegador (a página já desenha a moldura), nada de tela montada.
