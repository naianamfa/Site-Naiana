# Design System — Naiana Façanha Psicóloga

> **Tom visual:** _Um espaço de escuta suave — onde a delicadeza da aquarela e o calor humano se encontram para acolher quem chega._

---

## 1. Paleta de Cores

| Nome | Hex | Uso principal |
|---|---|---|
| **Violeta Névoa** | `#7B6CA8` | Cor primária — títulos, links, destaques de marca |
| **Lavanda Suave** | `#C9C0E3` | Backgrounds de seções, hover states, bordas leves |
| **Creme Acolhedor** | `#F9F4EF` | Background geral das páginas |
| **Rosa Aquarela** | `#EEB5C8` | Acentos, ícones, elementos decorativos |
| **Terracota Rosê** | `#C97A82` | CTAs (botões de ação), underlines em títulos |
| **Grafite Quente** | `#3D3351` | Textos corridos e corpo — alta legibilidade sobre o creme |

### Notas de uso
- O **Creme Acolhedor** deve ser o fundo dominante (≥ 60% da área visual).
- O **Violeta Névoa** e o **Terracota Rosê** formam o par de contraste — evite usá-los juntos no mesmo elemento.
- Use o **Rosa Aquarela** apenas como toque decorativo (máx. 10% da composição).
- Nunca coloque texto sobre o **Lavanda Suave** sem verificar contraste (ratio mín. 4.5:1).

---

## 2. Tipografia

Ambas as fontes são do **Google Fonts** e gratuitas.

### Títulos — `Cormorant Garamond`
```
font-family: 'Cormorant Garamond', serif;
font-weight: 300 | 400 | 600
```
Serif elegante e humanista. Evoca sensibilidade literária e acolhimento — alinhado ao estilo aquarela do cartão e ao tom narrativo do site de referência.

### Corpo — `DM Sans`
```
font-family: 'DM Sans', sans-serif;
font-weight: 300 | 400 | 500
```
Sans-serif geométrico com personalidade suave. Extremamente legível em tamanhos pequenos, sem frieza corporativa.

### Escala tipográfica (base 16px)

| Token | Tamanho | Peso | Uso |
|---|---|---|---|
| `--text-hero` | 52–64px | 300 (light) | Título principal da home |
| `--text-h1` | 40px | 400 | Títulos de seção |
| `--text-h2` | 28px | 400 | Subtítulos |
| `--text-h3` | 20px | 600 | Títulos de card |
| `--text-body` | 16px | 300 | Parágrafos corridos |
| `--text-small` | 13px | 400 | Notas, legendas, labels |

```html
<!-- Importação no <head> -->
<link rel="preconnect" href="https://fonts.googleapis.com">
<link href="https://fonts.googleapis.com/css2?family=Cormorant+Garamond:wght@300;400;600&family=DM+Sans:wght@300;400;500&display=swap" rel="stylesheet">
```

---

## 3. Espaçamento & Grid

### Unidade base
Todos os espaçamentos derivam de um **módulo de 8px**.

```
4px  → espaço mínimo (entre ícone e label)
8px  → xs
16px → sm
24px → md
32px → lg
48px → xl
64px → 2xl
96px → 3xl (respiro entre grandes seções)
```

### Grid de página

| Breakpoint | Colunas | Gutter | Margem lateral |
|---|---|---|---|
| Mobile (< 640px) | 4 | 16px | 20px |
| Tablet (640–1024px) | 8 | 24px | 32px |
| Desktop (> 1024px) | 12 | 32px | auto |

- **Max-width do conteúdo:** `1100px`
- **Max-width de texto corrido (legibilidade):** `640px` (~70 caracteres por linha)
- Seções de hero e fundos coloridos podem ser **full-bleed** (largura total), com o conteúdo interno respeitando o grid acima.

### Princípios de espaçamento
1. **Respiro generoso** — use `3xl` (96px) como separador padrão entre seções, nunca menos de `2xl` (64px).
2. **Hierarquia pelo espaço** — títulos têm `margin-top` maior que parágrafos; o vazio comunica calma.
3. **Consistência interna de cards** — padding interno mínimo de `24px` em todos os lados.

---

## 4. Bordas & Formas

- **Border-radius padrão:** `12px` (cards, botões, imagens)
- **Border-radius generoso:** `999px` (pílulas, chips, avatares circulares)
- Evite cantos completamente retos — a identidade é orgânica, não corporativa.
- Imagens de pessoas: sempre com `border-radius: 12px` ou formato orgânico recortado.

---

## 5. Sombras

```css
--shadow-sm: 0 2px 8px rgba(61, 51, 81, 0.06);   /* cards em repouso */
--shadow-md: 0 6px 24px rgba(61, 51, 81, 0.10);  /* cards em hover */
--shadow-lg: 0 12px 40px rgba(61, 51, 81, 0.14); /* modais, popovers */
```

Sombras usam o **Grafite Quente** (`#3D3351`) como base — nunca preto puro — para manter o calor visual.

---

## 6. Componentes-chave (guidelines)

### Botão primário (CTA)
```css
background: #C97A82;        /* Terracota Rosê */
color: #F9F4EF;
font-family: 'DM Sans', sans-serif;
font-weight: 500;
font-size: 15px;
padding: 14px 32px;
border-radius: 999px;
letter-spacing: 0.03em;
```

### Botão secundário (outline)
```css
background: transparent;
color: #7B6CA8;             /* Violeta Névoa */
border: 1.5px solid #7B6CA8;
/* demais propriedades iguais ao primário */
```

### Link de texto
```css
color: #7B6CA8;
text-decoration: underline;
text-decoration-color: #EEB5C8;  /* Rosa Aquarela */
text-underline-offset: 3px;
```

---

## 7. Rastreabilidade — extraído das imagens de referência

| Elemento | Observado nas referências | Aplicação |
|---|---|---|
| Aquarela/manchas | Cartão de visita da Naiana | SVG/PNG decorativos de fundo com transparência |
| Tons terrosos quentes | Site de terapia (ocre, blush) | Terracota Rosê e Rosa Aquarela |
| Violeta do logotipo | Cartão "Naiana Façanha Psicóloga" | Cor primária da marca (Violeta Névoa) |
| Tipografia serif expressiva | Títulos do site de referência | Cormorant Garamond nos títulos |
| Fundo creme limpo | Cartão branco + fundo do site | Creme Acolhedor como cor dominante |
| Pássaro em aquarela | Logo da Naiana | Referência para ilustrações: orgânicas, pintadas à mão |
