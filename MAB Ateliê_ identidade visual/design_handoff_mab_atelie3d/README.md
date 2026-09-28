# Handoff: MAB Atelie3D — marca, produção e site

## Overview

MAB Atelie3D é uma marca de peças e acessórios de bicicleta impressos em 3D
(suportes, adaptadores, protetores, porta-bidom, guarda-lama e acessórios sob
medida), produzida por um ateliê individual no Brasil. Este pacote contém a
identidade visual completa, os arquivos de produção (gravação a laser,
etiquetas impressas), o kit de redes sociais e a landing page "em breve" que
hoje é o site.

> **Reposicionamento (2026-09):** a marca era focada em artigos para casa e
> lembranças/peças devocionais. O foco agora é só bicicleta — peças
> funcionais (encaixe sob medida) e acessórios. O tom de ateliê artesanal, a
> identidade visual (cores, tipografia, direção visual abaixo) e o site em
> `site/index.html` já foram atualizados. Os demais documentos de design
> deste pacote (`Etiquetas A4.dc.html`, `Instagram — configuração
> inicial.dc.html`, `Kit de divulgação.dc.html`, `Site — em breve.dc.html`)
> ainda descrevem a linha antiga e precisam de uma passada de conteúdo —
> não foram reescritos neste turno.

O objetivo do handoff é permitir que um desenvolvedor: (a) reimplemente a
landing page no ambiente do projeto real, e (b) evolua essa página para uma
loja online, mantendo a identidade visual intacta.

## About the Design Files

Os arquivos deste pacote são **referências de design feitas em HTML** —
protótipos que mostram a aparência e o comportamento pretendidos, **não código
de produção para copiar direto**. A tarefa é **recriar esses designs no
ambiente do codebase de destino** (React, Next.js, Vue, etc.), usando os
padrões e bibliotecas já estabelecidos nele. Se ainda não existe ambiente, o
desenvolvedor deve escolher o framework mais adequado — para este caso, Next.js
estático (ou Astro) é a escolha natural, já que o site é publicado na Vercel.

Exceção importante: `site/index.html` **é** HTML estático de produção,
autossuficiente, sem dependências além do Google Fonts. Ele pode ser publicado
como está. Os arquivos `.dc.html` são os documentos de design.

## Fidelity

**Alta fidelidade (hifi).** Cores, tipografia, espaçamentos e estados finais
estão definidos. A UI deve ser recriada fielmente. As medidas dos arquivos de
produção (etiquetas em mm, vetores de laser em mm) são medidas físicas reais e
não podem ser alteradas.

---

## Design Tokens

Derivados do design system "Organic". Todos os valores abaixo são os usados.

### Cores

| Papel | Hex | Uso |
| --- | --- | --- |
| bg | `#f5ead8` | fundo da página (creme areia) |
| surface | `#ebddc5` | superfícies |
| text | `#201e1d` | texto principal |
| neutral-100 | `#f9f4ed` | cartões claros, texto sobre fundo escuro |
| neutral-200 | `#eee7db` | fundo de cartão |
| neutral-300 | `#dcd3c4` | bordas suaves |
| neutral-400 | `#c0b6a5` | linhas de corte |
| neutral-700 | `#645c50` | texto secundário (mínimo para corpo de texto) |
| neutral-800 | `#474238` | texto secundário escuro |
| accent (terracota) | `#c67139` | acento — **não usar em texto pequeno** |
| accent-200 | `#ffe1d0` | texto claro sobre terracota escuro |
| accent-300 | `#ffc6a5` | "3D" sobre fundos escuros |
| accent-700 | `#8c491a` | terracota para texto, botões e fundos com texto |
| accent-900 | `#402310` | terracota profundo |
| accent-2 (sage) | `#7a8a5e` | segundo acento |
| accent-2-200 | `#e1eecc` | fundo tintado sage |
| accent-2-700 | `#56633f` | sage escuro para fundos com texto |
| accent-2-900 | `#272e1b` | texto sobre fundo sage claro |

Regra de contraste aplicada: texto de corpo (≤17px) nunca em `accent` ou
`neutral-600`; usar `accent-700`+ e `neutral-700`+. Sobre fundo terracota,
usar `accent-700` como fundo (não `accent`) para o texto claro passar 4.5:1.

### Tipografia

- Display/títulos: **Caprasimo** (Google Fonts), weight 400, `font-family: "Caprasimo", Georgia, serif`
- Texto: **Figtree** (Google Fonts), weights 400/600/700
- A marca "MAB" é sempre Caprasimo. O subtítulo "atelie3D" é Figtree 600,
  uppercase, `letter-spacing: 0.3em`.
- Escala usada na landing: h1 `clamp(38px, 7vw, 72px)` / line-height 1.02;
  h2 `clamp(24px, 3.4vw, 34px)`; lead `clamp(17px, 2.2vw, 21px)`;
  corpo 15–17px / line-height 1.6.

### Espaçamento, raio, sombra

- Escala de espaço: 4.4 / 8.8 / 13.2 / 17.6 / 26.4 / 35.2 px (densidade 1.10×)
- Raios: sm 8px, md 16px, lg 28px; botões e pílulas `border-radius: 999px`
- Sombras: sm `0 1px 2px rgba(46,43,37,.14)`, md `0 3px 10px rgba(46,43,37,.16)`,
  lg `0 12px 32px rgba(46,43,37,.22)`

### Direção visual

Alinhamento à esquerda, layouts assimétricos, formas arredondadas ("over-round"),
fotos com o tratamento `.washed` (`filter: saturate(.6) contrast(.85) brightness(1.1) opacity(.94)`),
sem cantos vivos, sem geometria de fio de cabelo, sem cinzas dessaturados.

---

## A marca

- Nome: **MAB Atelie3D**. MAB são as iniciais do proprietário; "Atelie" comunica
  autoria; "3D" comunica a técnica.
- Logo é **puramente tipográfico**: "MAB" em Caprasimo, "atelie3D" em Figtree 600
  uppercase com `letter-spacing: 0.3em` abaixo.
- **Regra obrigatória:** o "3D" sempre em cor diferente de "atelie" —
  `accent-700` sobre fundo claro, `accent-300` ou `neutral-100` sobre fundo
  escuro. Em gravação monocromática, a diferença vira profundidade (gravar o
  "3D" mais fundo).
- Respiro mínimo em volta da marca: a altura da letra "M".
- Nunca inclinar, esticar, sombrear ou trocar a fonte do "MAB".
- **Não usar o nome pessoal do proprietário em nenhum material voltado ao
  cliente.** A fórmula aprovada é "desenhadas e produzidas no nosso ateliê".

### Faixas de redução

| Tamanho da gravação | O que usar |
| --- | --- |
| 25 mm ou mais | lockup completo (MAB + atelie3D) |
| 12 a 25 mm | só "MAB" |
| abaixo de 12 mm | "MAB" em contorno, traço mínimo 0,3 mm |

---

## Screens / Views

### 1. Landing "em breve" (`site/index.html`)

**Propósito:** anunciar que a loja abre em breve, explicar a linha de trabalho e
captar encomendas por e-mail e Instagram. Vai virar loja depois.

**Layout:** coluna única (`body { display:flex; flex-direction:column; min-height:100vh }`)
com header, main flexível e footer colado embaixo.

- **Header** — `padding: clamp(24px,5vw,44px) clamp(20px,6vw,72px)`, flex,
  `justify-content: space-between`, `flex-wrap: wrap`.
  - Esquerda: marca em duas linhas ("MAB" Caprasimo `clamp(26px,4vw,34px)`,
    line-height .95; "atelie3D" Figtree 600 `clamp(9px,1.4vw,11px)`,
    `letter-spacing:.3em`, uppercase, cor `neutral-700`, o "3D" em `accent-700`).
  - Direita: pílula "A loja abre em breve" — `padding:8px 18px`,
    `border-radius:999px`, fundo `accent-200` (`#ffe1d0`), texto `#643312`,
    13px/600.
- **Hero** — grid `repeat(auto-fit, minmax(300px,1fr))`, `gap: clamp(32px,5vw,64px)`,
  `align-items:center`, `max-width:1180px`.
  - Coluna de texto (flex column, `gap: clamp(20px,3vw,30px)`):
    - h1: "Peças e acessórios de bicicleta, impressos sob medida"
    - lead (`max-width:44ch`): "Suportes, adaptadores e acessórios desenhados e produzidos no nosso ateliê — sob medida pro seu quadro, guidão ou componente, na cor que você escolher."
    - sub (cor `neutral-700`): "Estamos terminando a primeira linha de peças e testando encaixe em bikes de verdade. Em breve esta página vira a loja. Até lá, as encomendas são pelo e-mail ou pelo Instagram."
    - Dois botões, flex `gap:12px`, `flex-wrap:wrap`:
      - primário: "Fazer uma encomenda" → `mailto:mab.atelie@mabatelie3d.com.br`.
        `padding:14px 26px`, `border-radius:999px`, fundo `accent-700`, texto `neutral-100`, 15px/600. Hover: fundo `#643312`.
      - secundário: "Ver no Instagram" → `https://instagram.com/mabatelie3d`.
        Fundo transparente, texto `accent-700`, borda 2px `accent-700`. Hover: fundo `accent-200`.
      - Foco: `outline: 2px solid accent-700; outline-offset: 3px`.
  - Coluna visual: painel `aspect-ratio: 4/3`, `border-radius:28px`, fundo
    `accent-700`, sombra lg, com o ícone de bicicleta (mesmo desenho do
    `mab-selo-bike-30mm.svg`, em `stroke: creme`) acima da marca centralizada
    em creme ("MAB" `clamp(54px,9vw,96px)`). **Este painel é um placeholder** —
    quando as fotos das peças existirem, substituir por foto de produto com o
    tratamento `.washed` e `border-radius:28px`.
- **"Nossa linha de trabalho"** — `margin-top: clamp(56px,9vw,104px)`;
  h2 + grid `repeat(auto-fit, minmax(240px,1fr))`, `gap:20px`. Três cartões:
  fundo `neutral-200`, `border-radius:16px`, `padding:26px`, flex column `gap:10px`.
  Cada um com um kicker (11px/700, `letter-spacing:.14em`, uppercase, cor `accent-700`)
  e um parágrafo 16px/1.6:
  - **peças funcionais** — "Suportes, adaptadores e protetores com encaixe testado pro seu quadro, guidão ou componente. Mais precisão que peça genérica de loja."
  - **acessórios** — "Porta-bidom, guarda-lama, enfeites de guidão e pequenos acabamentos. Praticidade do dia a dia com a identidade da sua bike."
  - **sob encomenda** — "Cor, encaixe e medida exata da sua bike. Você manda a referência e a peça é impressa depois do pedido."
- **Footer** — fundo `accent-700`, `padding: clamp(32px,6vw,56px) clamp(20px,6vw,72px)`,
  flex wrap, `justify-content:space-between`, `align-items:flex-end`,
  `gap: clamp(24px,4vw,48px)`. Três blocos: marca em creme; contato
  (kicker "contato" em `accent-200`, e-mail `mab.atelie@mabatelie3d.com.br` em
  creme 600 sublinhado com `word-break:break-word`, `@mabatelie3d` em `accent-200`);
  e a linha "mabatelie3d.com.br · peças desenhadas e produzidas no nosso ateliê".

**Responsivo:** sem largura fixa em nenhum elemento; todo texto em `clamp()`;
grids com `auto-fit`/`minmax`. Verificado sem overflow horizontal a 375px.

**Meta tags obrigatórias:** title, description, og:title, og:description,
og:type, og:url — todas sem o nome pessoal do proprietário.

### 2. Folha de etiquetas A4 (`Etiquetas A4.dc.html`)

Documento para imprimir, três páginas, **medidas físicas reais em mm**:

- Páginas 1 e 2: A4 retrato, `padding: 21mm 22.5mm`, grid 3 × 3 de células de
  **55 × 85 mm** (a etiqueta pendurada de produto).
- Página 1 (frentes): 3 etiquetas terracota (`accent-700`), 3 sage
  (`accent-2-700`), 3 creme (`neutral-200`). Cada uma: `border-radius: 6mm`,
  borda `0.25mm dashed neutral-400` (linha de corte), `padding: 7mm 6mm`;
  círculo de 5mm centralizado no topo marcando o furo de 4 mm; "MAB" em
  Caprasimo 14mm; "atelie3D" Figtree 600 3.2mm `letter-spacing:1mm`; rodapé
  "peças impressas em 3d" 2.6mm.
- Página 2 (versos): fundo branco, campo "PEÇA" com linha para escrever à mão,
  texto de cuidado ("Impressa em PLA, camada de 0,2 mm. Desenhada e produzida no
  nosso ateliê, uma peça por vez." / "Lavar com água morna e sabão neutro." /
  "Não expor ao calor direto nem ao sol.") e assinatura "MAB Atelie3D" +
  "@mabatelie3d".
- Página 3: instruções de impressão e corte (papel kraft/offset 250–300 g,
  imprimir em "Tamanho real"/100%, ativar cores de fundo).

Se isso for reimplementado, **preserve as unidades em mm e o comportamento de
página fixa** — é um documento de impressão, não uma tela.

### 3. Vetores de gravação a laser (`laser/*.svg`)

Seis SVGs em tamanho real, `width`/`height` em mm, `viewBox` em unidades de mm,
fill `#000000`:

| Arquivo | Conteúdo |
| --- | --- |
| `mab-lockup-30mm.svg` | 30 × 14.1 mm — MAB (font-size 9) + ATELIE3D (2.34, letter-spacing .8) |
| `mab-lockup-20mm.svg` | 20 × 9.4 mm — mesmo lockup reduzido |
| `mab-solo-12mm.svg` | 12 × 4.4 mm — só "MAB" preenchido |
| `mab-solo-12mm-contorno.svg` | idem, `fill:none; stroke-width:0.3` |
| `mab-selo-redondo-20mm.svg` | 20 × 20 mm — círculo `stroke-width:.6` + MAB + ATELIE3D |
| `mab-selo-bike-30mm.svg` | 30 × 30 mm — selo redondo com ícone de bicicleta (roda+quadro em linha, `stroke-width:.6`, `stroke-linecap/linejoin:round`) acima de MAB + ATELIE3D. Ver "Referência de bicicleta" abaixo. |

**Limitação conhecida e documentada:** as letras são `<text>` com
`font-family="Caprasimo"`; a fonte **não está embutida**. Quem abrir sem a
Caprasimo instalada vê outra fonte. O fluxo correto (descrito em
`laser/LEIA-ME.txt`) é instalar Caprasimo e Figtree, abrir no Inkscape e
converter texto em caminho (Ctrl+Shift+C) antes de gravar. Se alguém for
melhorar isso, o caminho é embutir a woff2 via `@font-face` dentro do SVG ou
gerar os caminhos vetoriais definitivos uma única vez.

**Referência de bicicleta (2026-09):** com o reposicionamento pra peças de
bike, a marca ganhou um ícone — uma bicicleta de perfil desenhada só com
linha (roda dianteira, roda traseira, quadro em triângulo, selim e guidão
simplificados), sempre em `stroke-width:.6` com pontas e junções
arredondadas (`stroke-linecap/linejoin:round`), a mesma espessura da borda
do selo. **De propósito sem raios/detalhe fino na roda** — é a lição que já
aprendemos gravando o logo da Saboaria Lindoya: traço fino demais derrete e
mancha no diodo azul sobre PLA (ver decisão equivalente em
`mab-solo-12mm-contorno.svg`, `stroke-width:0.3` mínimo documentado). O
ícone fica só em `mab-selo-bike-30mm.svg` por enquanto; os lockups
retangulares (`mab-lockup-*mm.svg`) continuam só tipográficos — se for
usar o ícone fora do selo redondo, redesenhe o lockup em vez de espremer a
bicicleta numa caixa 30×14.1mm pensada só pra texto.

### 4. Kit de Instagram (`Instagram — configuração inicial.dc.html`)

Especificação do perfil e das peças gráficas. Os PNGs já exportados estão em
`imagens/`:

- `perfil-terracota-1000.png`, `perfil-creme-1000.png` — 1000 × 1000
- `post-1-marca-1160.png`, `post-2-produto-1160.png`, `post-3-processo-1160.png` — 1160 × 1160
- `destaque-pecas-520.png`, `destaque-encomendar-520.png`, `destaque-cores-520.png`, `destaque-sobre-520.png` — 520 × 520

Campos do perfil: nome "MAB Atelie3D · impressão 3D" (27/30 caracteres);
categoria "Loja de artigos para casa"; conta do tipo Empresa; bio de 141/150
caracteres com quebras de linha.

---

## Interactions & Behavior

A landing atual é estática: nenhum estado, nenhum fetch. Os únicos
comportamentos são:

- Hover e `:focus-visible` nos dois botões (valores acima). Nunca deixar o anel
  de foco azul padrão do browser.
- Transições: `background .15s ease, color .15s ease` nos botões. Nada mais
  animado.
- Links externos: e-mail via `mailto:`, Instagram em link absoluto.

## State Management

Nenhum no estado atual. Para a evolução em loja, o mínimo previsto:

- catálogo de produtos (nome, descrição, cores disponíveis, preço, fotos)
- seleção de cor e quantidade por item
- carrinho persistente
- checkout (o cliente hoje pede por e-mail/WhatsApp — a transição precisa
  decidir entre gateway de pagamento e pedido por mensagem)

## Assets

- `laser/` — cinco SVG + LEIA-ME.txt (produção, gerados neste projeto)
- `imagens/` — nove PNG do Instagram (exportados dos designs deste projeto)
- Fotos das peças: fornecidas pelo proprietário (`uploads/`), são fotos
  provisórias tiradas por ele. **Fotos definitivas de produto ainda não existem** —
  é o principal bloqueio para a galeria e para a loja.
- Fontes: Caprasimo e Figtree, ambas Google Fonts (licença OFL, uso livre,
  inclusive embutir).
- Não há ícones. Se precisar, o padrão definido é Lucide com `stroke-width: 2.75`.

## Files

| Arquivo | O que é |
| --- | --- |
| `site/index.html` | **A landing, em HTML estático de produção.** Autossuficiente. |
| `site/COMO-PUBLICAR.md` | Passo a passo de publicação na Vercel e configuração de DNS |
| `Site — em breve.dc.html` | Documento de design da landing (versão com foto no hero) |
| `Marca MAB Atelie3D.dc.html` | Folha da marca: lockups, variações, redução, regras de uso |
| `Guia de gravação a laser.dc.html` | Guia dos vetores e do processo de gravação |
| `Etiquetas A4.dc.html` | Folha de etiquetas para impressão (3 páginas, mm) |
| `Kit de divulgação.dc.html` | Peças de redes sociais e textos prontos |
| `Instagram — configuração inicial.dc.html` | Configuração do perfil e primeiros posts |
| `laser/` | Vetores de gravação + LEIA-ME |
| `imagens/` | PNGs exportados para o Instagram |
| `styles.css` | Tokens e classes do design system Organic (referência) |
| `screenshots/` | Capturas de cada documento de design, para conferência visual |

### screenshots/

| Arquivo | Documento |
| --- | --- |
| `01-marca.png` | folha da marca completa |
| `02-site-em-breve.png` | a landing |
| `03-guia-laser.png` | guia de gravação |
| `04-instagram.png` | configuração do perfil |
| `05-etiquetas-a4.png` | as três páginas da folha de etiquetas |
| `06-kit-divulgacao.png` | kit de redes sociais |

As capturas foram tiradas a 845px de largura — são referência de aparência, não
de medida. As medidas valem as do texto acima.

Os arquivos `.dc.html` abrem direto no navegador.

## Estado da publicação

- Domínio `mabatelie3d.com.br` já adquirido; e-mail
  `mab.atelie@mabatelie3d.com.br` já em funcionamento.
- Repositório GitHub `gutobaddini-create/mabatelie3d` criado, ainda vazio.
- Projeto na Vercel **ainda não criado** — a conta pertence à equipe
  "Manuel Baddini's projects" (plano hobby).
- **Atenção ao configurar o DNS:** não remover os registros MX/TXT do domínio,
  ou o e-mail de contato para de funcionar.

## Próximos passos sugeridos

1. Publicar `site/index.html` (upload no repo → importar na Vercel → ligar o domínio).
2. Fotografar a primeira linha de peças. Sem foto de produto, a loja não avança.
3. Trocar o painel terracota do hero pela foto definitiva.
4. Construir a galeria de produtos e depois o checkout.
