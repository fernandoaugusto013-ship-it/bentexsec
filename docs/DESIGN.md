# BentexSEC — DESIGN.md

Referência visual: hackerrangers.com (cores e fontes medidas na página em 17/11/2026). Aproveitamos a família de cores (azul-marinho profundo, ação em ciano) e o par de fontes; o laranja da chama vem do logotipo BentexSEC. Não copiamos ilustrações, textos, marca nem layout.

Dois temas escuros: azul-marinho (padrão) e escuro neon (botão da lua).

## Cor
| Token | Valor | Papel |
|---|---|---|
| `--navy-950` | `#0F1B33` | Faixas mais profundas, rodapé |
| `--navy-900` | `#192846` | Fundo da página |
| `--navy-800` | `#203A61` | Superfícies (cards, formulários) |
| `--navy-700` | `#274A78` | Superfície elevada, hover |
| `--line` | `#2F4B73` | Bordas e divisórias |
| `--text` | `#FAF8F6` | Texto principal (contraste > 12:1 no fundo) |
| `--text-muted` | `#A9B8CE` | Texto secundário (contraste ≈ 7:1) |
| `--primary` | `#32AFFF` | Ação principal: botões, links, foco |
| `--primary-ink` | `#0F1B33` | Texto sobre o primário |
| `--neon` | `#22D8FF` (lua: `#00F0FF`) | Azul neon tecnológico com brilho: palavras-chave nos títulos, rótulos de seção, seção atual no menu, barra de progresso, indicadores das rolagens contadas. Usar com moderação |
| `--flame` | `#FF7A1A` | Acento único (do logo): números de destaque, marcadores de etapa. Nunca em botões |
| `--ok` | `#3DDC84` | Sucesso, ativo |
| `--warn` | `#FFC83D` | Atenção, expirado |
| `--crit` | `#FF5A4E` | Erro, bloqueado |

Sem degradê multicolorido em botões e títulos (só variação sutil do mesmo tom).

**Modo escuro neon (botão da lua no menu):** troca os azuis-marinho por quase-preto (`#04060B` → `#142036`), o primário e o neon para `#00E1FF`/`#00F0FF` e aumenta o brilho (`--glow`). O tema azul é o padrão; a escolha fica salva no navegador da pessoa.

## Tipografia
- **Display:** Squada One 400, sempre em MAIÚSCULAS, para títulos e números grandes. Fallback: "Arial Narrow", sans-serif.
- **Texto:** Rubik 400/500/600. Fallback: system-ui, sans-serif.
- **Código e rótulos técnicos:** JetBrains Mono 400/500 (códigos de certificado, senhas provisórias, rótulos "ETAPA 02").
- Escala: 13 / 15 / 17 / 20 / 26 / 34 / 48 / 64 px. Texto corrido 17px, linha 1,6, até 65 caracteres.

## Espaçamento
Escala de 4: 4, 8, 12, 16, 24, 32, 48, 72, 112. Seções com 112px de respiro no desktop e 72px no celular. Largura de conteúdo 1160px; texto corrido 640px.

## Forma e profundidade
- Raio: 4px (botões e campos, como a referência), 8px (cards). Nada arredondado em pílula, exceto indicadores de estado.
- Sem sombras difusas. Profundidade por camadas de azul (950 → 900 → 800 → 700) e borda de 1px `--line`.
- Sem desfoque de vidro.

## Componentes
- **Botão primário (3D neon):** fundo `--primary` com leve variação do mesmo tom, base em `--primary-deep` (4px) que dá profundidade, brilho neon. Hover: sobe 2px, brilho aumenta e um reflexo atravessa o botão. Clique: afunda. O botão principal do banner pulsa devagar.
- **Botão secundário (neon):** contorno em `--neon`, fundo quase transparente, mesma profundidade e reflexo; no hover o texto e a borda acendem.
- **Botão discreto:** só texto `--primary`, sublinha no hover.
- **Campo:** fundo `--navy-950`, borda `--line`, raio 4px, rótulo acima. Erro só após interação.
- **Card:** fundo `--navy-800`, borda `--line`, raio 8px.
- **Estado:** ponto colorido + texto (ok, warn, crit). Metadados estáticos são texto simples, sem pílula.
- **Navegação:** barra sólida `--navy-950`; logo à esquerda; links em Rubik 15px; ação primária à direita.
- **Barra de demonstração:** faixa fina acima da navegação, em mono, separada do produto.

## Imagens e movimento
- Sem fotos de banco de imagens e sem personagens em vetor. As imagens são **telas do próprio produto montadas como mockup** (aula, e-mail suspeito, certificado) e um **fundo em canvas** com malha de rede e pacotes em movimento.
- Animações curtas (200–600 ms), apenas transform e opacity; tudo visível em repouso; desligadas com `prefers-reduced-motion`.
- **Menu:** fixo, transparente sobre o banner e sólido (`--navy-950` + borda) depois de 160px de rolagem; sublinhado em `--flame` no hover, em `--primary` na seção atual; barra de progresso de leitura em `--flame`. No celular, gaveta lateral que abre deslizando.
- **Banner "O cadeado se fecha" (aprovado para teste em 17/11/2026):** o banner fica preso na tela por cerca de 3 telas de rolagem. Fase 01 "As ameaças chegam todos os dias": cadeado aberto, ataques acertam o cadeado. Fase 02 "Pessoas treinadas reconhecem o golpe": o escudo se monta peça por peça e bloqueia os ataques. Fase 03 "E a empresa fica protegida": a haste desce, o cadeado fecha com brilho laranja e vira o logotipo. Imagens do Canva (cadeado aberto, fechado e fundo) vão substituir o cadeado desenhado quando chegarem.
- **Rolagem:** títulos sobem ou entram da esquerda, itens de lista aparecem um a um, a linha do tempo se desenha, a aula de phishing destaca um sinal de golpe por passo, números contam até o valor final. Sem animação de rolagem quando o navegador não suporta ou quando a pessoa pede menos movimento; o conteúdo fica sempre visível.
- **PADRÃO APROVADO — "Rolagem contada" (aprovado pelo Fernando em 17/11/2026):** usado em "02 · Na prática", "03 · Como funciona" e "06 · Etapas do projeto". Duas colunas: à esquerda, uma tela do produto fica fixa (sticky) enquanto se rola; à direita, passos numerados (01, 02…) com cerca de 62% da altura da tela cada, borda esquerda que acende em `--flame` no passo ativo. Cada passo, ao chegar ao centro da tela, muda a tela fixa (destaca um detalhe ou troca a tela com subida e esmaecimento). Indicador de progresso em tracinhos no topo da janela. No celular, a tela de cada passo aparece logo abaixo do texto. Usar este padrão sempre que uma seção explicar uma sequência.
- **PADRÃO APROVADO — "Cadeado protegido" (aprovado pelo Fernando em 17/11/2026):** globo pontilhado girando com o cadeado do logo no centro, anel-escudo hexagonal em `--primary` e ataques em `--crit` que se desfazem em faíscas `--flame` ao bater no escudo. É um componente reutilizável (`canvas.globe` + `.core`). Uso atual: tela de login do colaborador; a mesma lógica de escudo e ataques é usada no banner.
- Ícones: traço de 2px, monocromáticos, desenhados em SVG.
