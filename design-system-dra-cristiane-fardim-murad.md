# Design System — Dra. Cristiane Fardim Murad
### Base visual para a landing page · Odontologia · Lavras/MG

**O que foi lido nas referências:** rosewood/mauve empoeirado sobre fundos creme quentes, tipografia serifada com uma linha em itálico dentro do título, cards de cantos generosos com sombra quase invisível, botões em formato pílula e blocos escuros (espresso/carvão) usados para dar peso e autoridade. O sistema abaixo consolida isso numa base única: **calor e acolhimento no corpo da página, autoridade nos blocos escuros, e um único caminho visual claro até o WhatsApp.**

---

## 1. Cores

### 1.1 Paleta principal — Rosewood (identidade e ação)

A cor da marca. Usada em CTAs, títulos de destaque, overlays de imagem e detalhes. É um rosé dessaturado e escurecido — não é rosa "clínica de estética", é rosé amadeirado, que é o que sustenta autoridade.

| Token | Hex | Onde usar |
|---|---|---|
| `--rosewood-900` | `#4E3036` | Texto sobre fundos claros quando precisa de máximo peso; rodapé escuro alternativo |
| `--rosewood-700` | `#8B5C64` | **Cor de ação principal.** Fundo de botão primário, ícones ativos, links |
| `--rosewood-500` | `#A97A81` | Overlays sobre foto, hover de estados escuros, bordas ativas |
| `--rosewood-300` | `#C9A3A7` | Eyebrows (rótulos acima dos títulos), ícones decorativos, divisores |
| `--rosewood-100` | `#F0E1E2` | Fundos de badge, estados selecionados, faixas suaves |

> **Contraste:** `#8B5C64` sobre branco = **5,5:1** (aprova AA para texto normal e para texto branco dentro do botão). `#4E3036` sobre creme = **~10:1**. Nunca use `--rosewood-300` como cor de texto em fundo claro — é decorativa.

### 1.2 Paleta secundária — Neutros quentes (a base da página)

| Token | Hex | Onde usar |
|---|---|---|
| `--cream-50` | `#FDFBF6` | Fundo padrão da página |
| `--sand-100` | `#F6EDE4` | Fundo de seção alternada (quebra o ritmo entre blocos) |
| `--sand-200` | `#E7DACD` | Bordas de card, linhas divisórias, contorno de input |
| `--ink-600` | `#6B5F5A` | Corpo de texto secundário, legendas |
| `--ink-800` | `#3B322F` | **Corpo de texto principal** |
| `--espresso-900` | `#241D1B` | Fundo dos blocos escuros (hero e CTA final) |

> Nunca use preto puro (`#000`) nem cinza frio (`#666`, `#999`). O sistema inteiro é quente — um cinza neutro no meio disso denuncia template.

### 1.3 Paleta de suporte (semântica e conversão)

| Token | Hex | Onde usar |
|---|---|---|
| `--whatsapp` | `#25D366` | **Exclusivo** do botão flutuante e do ícone dentro dos CTAs. Nunca como cor de fundo de seção |
| `--whatsapp-dark` | `#128C7E` | Hover do botão flutuante |
| `--gold-400` | `#B9955F` | Estrelas de avaliação, selo "5.0 no Google", detalhes de credibilidade |
| `--jade-700` | `#2E6B52` | Confirmações, selos de segurança/CRO, "resposta rápida" |
| `--alert-600` | `#A5463C` | Erro de formulário (vermelho quente, não vermelho puro) |

### 1.4 Regra de proporção (60 / 30 / 10)

- **60%** neutros quentes (`--cream-50`, `--sand-100`) — respiro.
- **30%** escuros (`--espresso-900`, `--ink-800`) — texto e blocos de autoridade.
- **10%** rosewood — e dentro desses 10%, **a maior mancha de cor da página é sempre um botão.** Se o rosewood aparecer em decoração mais do que em CTA, a cor perdeu a função e a conversão cai.

---

## 2. Tipografia

### 2.1 Famílias

**Display / títulos — `Fraunces`** (Google Fonts)
Serifada de contraste alto, com itálico expressivo e eixo variável de peso. É o que dá o ar de "consultório particular, não convênio". Sugestões similares caso queira trocar: `Newsreader`, `Prata`, `Instrument Serif`, `Playfair Display`.

**Corpo / interface — `Figtree`** (Google Fonts)
Sans geométrica-humanista, muito legível em telas pequenas e com acentuação de português bem desenhada (ã, õ, ç, á). Similares: `Jost`, `Be Vietnam Pro`, `Poppins`.

```html
<link href="https://fonts.googleapis.com/css2?family=Fraunces:ital,opsz,wght@0,9..144,300..700;1,9..144,300..600&family=Figtree:wght@400;500;600;700&display=swap" rel="stylesheet">
```

```css
--font-display: 'Fraunces', Georgia, 'Times New Roman', serif;
--font-body: 'Figtree', -apple-system, 'Segoe UI', Roboto, sans-serif;
```

### 2.2 Hierarquia

| Nível | Fonte | Tamanho (desktop → mobile) | Peso | Entrelinha | Espaçamento |
|---|---|---|---|---|---|
| **H1** | Fraunces | 64px → 38px | 400 | 1.08 | -0.02em |
| **H2** | Fraunces | 42px → 30px | 400 | 1.15 | -0.015em |
| **H3** | Fraunces | 28px → 24px | 500 | 1.25 | -0.01em |
| **H4 / título de card** | Figtree | 20px → 18px | 600 | 1.35 | 0 |
| **Lead** (subtítulo do hero) | Figtree | 19px → 17px | 400 | 1.65 | 0 |
| **Corpo** | Figtree | 17px → 16px | 400 | 1.7 | 0 |
| **Corpo pequeno / legenda** | Figtree | 14px | 400 | 1.6 | 0 |
| **Eyebrow** (rótulo acima do H2) | Figtree | 12px | 600 | 1 | 0.14em, caixa alta |
| **Botão** | Figtree | 16px | 600 | 1 | 0.01em |

```css
--step-h1: clamp(2.375rem, 1.6rem + 3.4vw, 4rem);
--step-h2: clamp(1.875rem, 1.4rem + 2vw, 2.625rem);
--step-h3: clamp(1.5rem, 1.3rem + 0.8vw, 1.75rem);
--step-body: clamp(1rem, 0.97rem + 0.15vw, 1.0625rem);
```

### 2.3 Regras de uso

- **A assinatura tipográfica da marca:** o H1 e cada H2 terminam com **uma linha inteira em itálico**, em `--rosewood-500`. Linha inteira, nunca uma palavra solta no meio da frase.
  > Cuidado, técnica e o<br>*sorriso que você merece.*
- **Largura máxima de leitura: 68 caracteres** (`max-width: 62ch`). Texto corrido que atravessa a tela inteira cansa e derruba a leitura até o CTA.
- **Números grandes** (anos de atuação, pacientes atendidos) em Fraunces peso 400, nunca em negrito sans — é o contraste serif/sans que faz eles parecerem dado, e não anúncio.
- **Eyebrow com barra vertical à esquerda** (`border-left: 2px solid var(--rosewood-500)`), como nas referências. É o único uso de caixa alta permitido no sistema.

---

## 3. Componentes

### 3.1 Botões

Formato **pílula** (`border-radius: 999px`) em todos os níveis — é a assinatura das referências e dá o ar de acolhimento.

**Primário — leva ao WhatsApp**
```css
background: var(--rosewood-700);
color: #fff;
height: 56px;            /* 52px no mobile, nunca menos que 48 */
padding: 0 34px;
font: 600 16px/1 var(--font-body);
border-radius: 999px;
box-shadow: 0 6px 18px rgba(78,48,54,.18);
transition: transform .18s ease, box-shadow .18s ease, background .18s ease;
```
- **Hover:** `background: #7A4F56`, `transform: translateY(-2px)`, sombra `0 10px 26px rgba(78,48,54,.26)`.
- **Focus:** `outline: 3px solid var(--rosewood-300); outline-offset: 3px`.
- **Ícone do WhatsApp em branco antes do texto**, 20px. É o que transforma o botão de "genérico" em "eu sei exatamente o que vai acontecer quando eu clicar".

**Secundário — navegação interna ("Conhecer os tratamentos")**
Fundo transparente, borda `1.5px solid var(--sand-200)` no claro (ou `rgba(255,255,255,.35)` no escuro), texto `--ink-800`. Hover: borda vira `--rosewood-500`.

**Terciário / link** — texto `--rosewood-700`, sublinhado com `text-underline-offset: 4px`.

**Flutuante do WhatsApp** — círculo 60px, fundo `--whatsapp`, ícone branco, `position: fixed; right: 20px; bottom: 20px`, sombra `0 8px 24px rgba(37,211,102,.35)`. Este é o único lugar onde o verde do WhatsApp aparece — e aparece porque ali o reconhecimento instantâneo vale mais do que a harmonia da paleta.

**Regra de conversão:** **um único botão primário por dobra da tela.** Dois primários competindo dividem o clique. Se a seção precisa de duas ações, a segunda é sempre secundária.

### 3.2 Inputs de formulário

Mesmo que o foco seja WhatsApp, o formulário existe (agendamento fora do horário, contato por e-mail).

```css
height: 52px;
padding: 0 18px;
background: #fff;
border: 1.5px solid var(--sand-200);
border-radius: 12px;          /* input NÃO é pílula — só botão é */
font: 400 16px var(--font-body);   /* 16px evita o zoom automático no iOS */
color: var(--ink-800);
```
- **Label sempre acima do campo**, 14px peso 500, `--ink-600`. Nunca placeholder como label.
- **Foco:** `border-color: var(--rosewood-700)` + `box-shadow: 0 0 0 4px rgba(139,92,100,.14)`.
- **Erro:** borda `--alert-600` + mensagem embaixo em 13px dizendo **o que fazer**, não o que falhou: "Informe um WhatsApp com DDD (ex: 35 99999-0000)".
- **Textarea:** mesmas regras, `min-height: 130px`, `padding: 14px 18px`.
- **Botão de envio ocupa 100% da largura do formulário** no mobile.

### 3.3 Cards

Três variantes, cada uma com uma função — não use a mesma para tudo:

**a) Card de tratamento com imagem** (destaque, 1–3 por página)
`border-radius: 20px`, imagem no topo, faixa inferior em `--rosewood-500` com texto branco, sem borda. Sombra `--shadow-md`. É o card que vende.

**b) Card de tratamento com ícone** (a grade completa de procedimentos)
Fundo `--cream-50`, borda `1px solid var(--sand-200)`, `border-radius: 16px`, padding 28px, e uma **barra de 3px × 44px em `--rosewood-700` no topo** (detalhe direto da referência). Ícone de linha 28px em `--rosewood-500`, título H4, descrição 15px.

**c) Card de depoimento**
Fundo branco, `border-radius: 16px`, estrelas em `--gold-400`, texto em Fraunces itálico 18px, assinatura em 14px `--ink-600`. Sem aspas gigantes decorativas.

**Card de credibilidade da Dra.** — variante do (a) com retrato em proporção 4:5 e o CRO-MG visível. Credencial visível é conversão: em saúde, o paciente procura registro profissional antes de clicar.

---

## 4. Estética

### 4.1 Arredondamento (border-radius)

| Token | Valor | Aplicação |
|---|---|---|
| `--radius-sm` | 8px | Badges, tags, selos |
| `--radius-md` | 12px | Inputs, select, textarea |
| `--radius-lg` | 16px | Cards padrão |
| `--radius-xl` | 20px | Cards com imagem, blocos de destaque |
| `--radius-2xl` | 28px | Blocos de seção inteiros, container de vídeo |
| `--radius-full` | 999px | Botões, avatares, pílulas |

**Regra:** o raio cresce com o tamanho do elemento. Um card de 400px com raio 8px parece rígido; um input com raio 28px parece brinquedo.

### 4.2 Sombras

Todas as sombras são **tingidas de rosewood**, nunca pretas. Sombra preta sobre fundo creme fica cinza-sujo.

```css
--shadow-sm: 0 1px 2px rgba(78,48,54,.06);
--shadow-md: 0 4px 16px rgba(78,48,54,.08);
--shadow-lg: 0 12px 34px rgba(78,48,54,.12);
--shadow-cta: 0 6px 18px rgba(78,48,54,.18);
--shadow-float: 0 8px 24px rgba(37,211,102,.35);  /* só no botão do WhatsApp */
```
Cards em repouso usam `--shadow-sm` ou só borda. **A sombra mais forte da página pertence ao CTA** — é assim que o olho encontra o botão sem precisar de seta.

### 4.3 Espaçamentos

Escala base **4px**:
`4 · 8 · 12 · 16 · 24 · 32 · 48 · 64 · 96 · 128`

```css
--space-1:4px; --space-2:8px;  --space-3:12px; --space-4:16px; --space-5:24px;
--space-6:32px; --space-7:48px; --space-8:64px; --space-9:96px; --space-10:128px;
```

| Contexto | Valor |
|---|---|
| Padding vertical de seção | `clamp(64px, 9vw, 128px)` |
| Padding lateral do container | 24px mobile · 40px tablet · 80px desktop |
| Largura máxima do container | 1200px |
| Gap entre cards da grade | 24px mobile · 32px desktop |
| Padding interno de card | 24px mobile · 28–32px desktop |
| Título → parágrafo | 16px |
| Parágrafo → botão | 32px |
| Bloco → bloco dentro da seção | 48px |

**Ritmo da página:** alterne `--cream-50` e `--sand-100` entre seções, e coloque **um** bloco `--espresso-900` no hero e **um** no CTA final. O escuro é o que fecha a página com peso — se aparecer em quatro seções, vira ruído e deixa de significar autoridade.

---

## 5. Aplicação para autoridade e conversão

### 5.1 O que constrói autoridade neste layout

1. **Foto profissional real e grande no hero.** A referência acerta nisso: consultório individual vende pela pessoa. Foto de banco de imagem destrói a confiança em saúde.
2. **CRO-MG visível** no bloco da especialista e no rodapé — em odontologia, isso é obrigação do CFO e também prova social.
3. **Serifada + espaço em branco generoso** = percepção de atendimento particular. Página apertada parece consultório de volume.
4. **Números em Fraunces** (anos, pacientes, avaliação no Google) na barra logo abaixo do hero.
5. **Nada de "melhor dentista da cidade"** — o Código de Ética Odontológica proíbe promessa de resultado e autopromoção comparativa. Autoridade aqui vem de credencial, formação e depoimento, não de superlativo.

### 5.2 O caminho até o WhatsApp

- **5 pontos de conversão** ao longo da página: hero, fim da seção de tratamentos, fim dos diferenciais, seção de localização, CTA final. Mais que isso vira insistência.
- **Botão flutuante sempre visível** no mobile (é onde vai vir quase todo o tráfego).
- **Microcopy embaixo do botão primário**, 13px `--ink-600`: *"Atendimento particular · Resposta no mesmo dia"*. Reduz o atrito de "será que vão me responder?".
- **Texto do CTA em primeira pessoa e ação concreta:** "Agendar minha avaliação" converte mais que "Saiba mais" ou "Entre em contato".
- **Link com mensagem pré-preenchida:** `https://wa.me/55DDDNUMERO?text=Ol%C3%A1%2C%20vim%20pelo%20site%20e%20quero%20agendar%20uma%20avalia%C3%A7%C3%A3o` — tira do paciente o trabalho de saber o que escrever, que é onde muito lead desiste.
- **Área de toque mínima de 48×48px** em qualquer elemento clicável no mobile.

### 5.3 Piso de qualidade

- Foco de teclado visível em todos os interativos (`outline` rosewood, nunca `outline: none`).
- `prefers-reduced-motion` respeitado.
- Contraste mínimo 4.5:1 em texto — a paleta já está calibrada para isso.
- Animação: **um** momento orquestrado na entrada do hero. Card que sobe a cada scroll é o tique visual mais comum de site genérico.

---

## 6. Tokens prontos (CSS)

```css
:root{
  /* Rosewood */
  --rosewood-900:#4E3036; --rosewood-700:#8B5C64; --rosewood-500:#A97A81;
  --rosewood-300:#C9A3A7; --rosewood-100:#F0E1E2;
  /* Neutros quentes */
  --cream-50:#FDFBF6; --sand-100:#F6EDE4; --sand-200:#E7DACD;
  --ink-600:#6B5F5A; --ink-800:#3B322F; --espresso-900:#241D1B;
  /* Suporte */
  --whatsapp:#25D366; --whatsapp-dark:#128C7E; --gold-400:#B9955F;
  --jade-700:#2E6B52; --alert-600:#A5463C;
  /* Tipografia */
  --font-display:'Fraunces',Georgia,serif;
  --font-body:'Figtree',-apple-system,'Segoe UI',sans-serif;
  /* Raios */
  --radius-sm:8px; --radius-md:12px; --radius-lg:16px;
  --radius-xl:20px; --radius-2xl:28px; --radius-full:999px;
  /* Sombras */
  --shadow-sm:0 1px 2px rgba(78,48,54,.06);
  --shadow-md:0 4px 16px rgba(78,48,54,.08);
  --shadow-lg:0 12px 34px rgba(78,48,54,.12);
  --shadow-cta:0 6px 18px rgba(78,48,54,.18);
  /* Espaçamento */
  --space-1:4px; --space-2:8px; --space-3:12px; --space-4:16px; --space-5:24px;
  --space-6:32px; --space-7:48px; --space-8:64px; --space-9:96px; --space-10:128px;
  --container:1200px;
}
```

---

## Tom visual em 3 linhas

1. **Rosé amadeirado sobre creme quente**, com blocos espresso pontuais — feminino e sofisticado sem cair no clichê de clínica de estética.
2. **Serifada de contraste alto com uma linha em itálico** dentro de cada título, apoiada numa sans geométrica limpa: passa atendimento particular, cuidadoso e caro-no-bom-sentido.
3. **Formas arredondadas, sombras quentes e muito respiro**, com a única mancha forte de cor da tela sendo sempre o botão que leva ao WhatsApp.
