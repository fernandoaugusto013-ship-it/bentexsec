# BentexSEC — protótipo

Plataforma de conscientização em segurança da informação: aulas curtas, prova, certificado, prova prática de phishing com marcas fictícias, reforço e painel da gestão.

Este repositório guarda o **protótipo visual clicável**. É uma página HTML única, com dados fictícios guardados no navegador. Ele **não envia e-mails** e **não tem login, banco de dados nem servidor reais**.

## Como abrir

Abra o `index.html` no navegador (o `logo.webp` precisa ficar na mesma pasta). Para publicar como site, ative o GitHub Pages em *Settings → Pages*, com a branch `main` e a pasta raiz.

O botão **Reiniciar demonstração**, no topo, volta os dados ao estado inicial.

## Contas de demonstração (fictícias)

| Perfil | E-mail | Senha |
|---|---|---|
| Administrador | `admin@bentexsec.exemplo` | `Admin#2026` |
| Gestão (Marina Costa) | `marina.costa@horizonteazul.exemplo` | `Gestao#2026` |
| Colaboradores ativos | ex.: `elisa.prado@horizonteazul.exemplo`, `hugo.lima@…`, `joao.pedro.silva@…`, `ursula.pires@…`, `felipe.nogueira@…` | `Horizonte#2026` |

São senhas de demonstração, sem valor fora do protótipo.

## O que já está pronto

1. **Acesso:** senha provisória única, com troca obrigatória no primeiro acesso.
2. **Trilha de aulas:** vídeo, imagem e leitura, com "lido" obrigatório; trilha extra por setor; níveis, pontos e medalhas.
3. **Prova e certificado:** prova com perguntas sorteadas; certificado com código e QR; verificação pública (sem a nota); prévia para o LinkedIn; ranking por setor.
4. **Painel da gestão:** progresso e notas; risco por pessoa e setor; lembretes automáticos (simulados); relatório de evidências para auditoria (ISO/IEC 27001 e LGPD).
5. **Administração:** acessos da gestão e editor de conteúdo (aulas, perguntas e e-mails de phishing), com rascunho, pré-visualização, versões e bloqueio de marcas reais.
6. **Reforço:** revisão e verificação rápida dos temas errados antes da nova tentativa, com acompanhamento da gestão.
7. **Phishing:** prova prática dentro da plataforma. O disparo de e-mails reais é a próxima etapa, a planejar.

## Arquivos

- `index.html`: o protótipo completo (HTML, CSS e JavaScript num arquivo só).
- `logo.webp`: o logotipo.
- `docs/DESIGN.md`: as decisões de design (cores, fontes e animações aprovadas).

Dependências externas, carregadas por CDN: Google Fonts (Squada One, Rubik e JetBrains Mono) e qrcodejs 1.0.0.
