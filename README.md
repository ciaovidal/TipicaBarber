# Típica Barbearia | Landing page

Landing page da **Típica Barbearia** (Gravataí, RS). A página apresenta a barbearia e leva o cliente para o **WhatsApp** e o **Instagram**.

- Instagram: [@tipicabarbearia](https://www.instagram.com/tipicabarbearia/)
- WhatsApp: (51) 99418-4893
- Endereço: Avenida dos Estados, 520, sala 524, Vera Cruz, Gravataí

HTML e CSS puros, sem framework e sem etapa de build. Basta publicar a pasta como está.

## Estrutura

```
tipica-barbearia/
├── index.html        Página completa (HTML, CSS e um pequeno script)
├── vercel.json       Configuração de cache das imagens na Vercel
├── README.md
└── assets/
    ├── logo.png            Logo com fundo transparente (cabeçalho e rodapé)
    ├── favicon.png         Ícone da aba do navegador
    ├── og.jpg              Imagem de prévia ao compartilhar o link (1200x630)
    ├── hero-primo.webp     Foto principal (abertura)
    ├── salao-cadeira.webp  Galeria "Barbearia raiz"
    ├── parede-sofa.webp    Galeria "Barbearia raiz"
    ├── ferramentas.webp    Galeria "Barbearia raiz"
    ├── cantinho.webp       Galeria "Barbearia raiz"
    ├── painel-estilos.webp Seção "Não sabe o que pedir?"
    ├── catalogo.webp       Seção "Não sabe o que pedir?" (foto menor sobreposta)
    ├── cera-matte.webp     Produtos
    ├── cera-brilho.webp    Produtos
    ├── gel-cera.webp       Produtos
    ├── open-balm.webp      Produtos
    └── interior.webp       Seção "Onde estamos"
```

## Publicar na Vercel

1. Suba esta pasta para um repositório no GitHub.
2. Na Vercel: **Add New > Project**, importe o repositório.
3. Em **Framework Preset**, escolha **Other**. Não precisa de build command nem output directory.
4. Clique em **Deploy**.

A cada novo commit na branch principal, a Vercel publica a versão nova sozinha.

## Depois do primeiro deploy

### Imagem de prévia no WhatsApp
O WhatsApp e o Instagram só mostram a prévia se a imagem tiver endereço completo. No `index.html`, troque:

```html
<meta property="og:image" content="assets/og.jpg">
```

pelo endereço final do site, por exemplo:

```html
<meta property="og:image" content="https://tipica-barbearia.vercel.app/assets/og.jpg">
```

### Domínio próprio
Na Vercel: **Settings > Domains**. A própria Vercel mostra os registros DNS que precisam ser configurados.

## Como trocar uma foto

1. Substitua o arquivo dentro de `assets/` **mantendo o mesmo nome**.
2. Prefira fotos verticais, com cerca de 1000 a 1400 px no lado maior.
3. Formato recomendado: `.webp` (mais leve). Para converter um JPG: [squoosh.app](https://squoosh.app).
4. Se usar outro nome ou formato, atualize o `src` correspondente no `index.html`.

O enquadramento da foto principal é controlado por `object-position` em `.hero-media img` no CSS (há um valor para computador e outro para celular).

## Como editar textos e preços

Tudo está no `index.html`:

- **Preços:** procure por `class="row"` na seção `id="valores"`.
- **Horários:** seção `class="hours"` e também a seção `id="onde"`.
- **Link do WhatsApp:** procure por `wa.me/5551994184893`. A mensagem pronta vem depois de `?text=`.

## Detalhes técnicos

- Fontes: Bodoni Moda (títulos) e Manrope (texto), via Google Fonts.
- Ícones: Phosphor Icons, embutidos como SVG.
- O dia atual é destacado automaticamente na faixa de horários.
- As animações de entrada respeitam a configuração de movimento reduzido do sistema.
- Layout responsivo, com botão fixo de WhatsApp no celular.
