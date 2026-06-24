# cais estúdio — site institucional

Site one-page estático da **cais estúdio**, produtora de produção audiovisual em Volta Redonda / RJ.
Marca comercial: **cais**. Autoridade criativa: **Ferreira** (Hudson Ferreira, fundador).

## Stack
- HTML + CSS + JavaScript puro (vanilla). **Sem framework, sem build, sem dependências.**
- É um único `index.html` com o CSS no `<head>` e um `<script>` pequeno no fim do `<body>`.
- Fontes e imagens são arquivos locais em `assets/`.
- Para ver localmente: abrir `index.html` no navegador, ou rodar um servidor estático
  (`python3 -m http.server` e abrir http://localhost:8000).

## Estrutura
```
index.html              # página inteira (HTML + CSS + JS)
assets/fonts/           # Grytle.woff (títulos), Gcgatuzo-*.woff (corpo)
                        # + originais .otf/.ttf (para gerar woff2, ver "Otimizações")
assets/img/             # lockup-cream.png (logo) e symbol-cream.png (favicon)
```

## Identidade (NÃO alterar sem pedido explícito)
- Cores: fundo `#0C1A15`, verde-marca `#183830`, creme `#E8E0D0`. Tokens no `:root` do CSS.
- Tipografia: **Grytle** (display/títulos, só peso Black) e **Gcgatuzo** (corpo: 400/500/700).
- Símbolo da marca = setas convergentes (conceito de "travessia"). É o motivo gráfico do site.
- Produto = **somente produção audiovisual**. NÃO mencionar campanhas pontuais nem identidade
  visual/design como serviço.

## Seções (ordem) e referências de animação
Hero (vídeo de fundo, ref. Abdala Brothers) → Sobre (manifesto 2 colunas, ref. Sand) →
Trabalhos (painéis que expandem em ciclo automático, ref. Rabbit) → Showreel → Travessia (processo) →
Por que a cais (título outline, ref. Sand) → Direção/Ferreira → Contato (form que abre o WhatsApp, ref. Sand).

## TODO — antes de publicar
**Já feito:** logos oficiais (header = logo-site horizontal com "estúdio"; rodapé = logo-rodape empilhado; favicon), 5 capas de case reais e foto do Ferreira na seção Direção.

**Falta (preencher/pedir ao Code):**
1. **WhatsApp:** trocar `55SEUNUMERO` por `5524999813004`. 3 ocorrências (botão de contato, rodapé e o `window.open` do formulário no script).
2. **E-mail e Instagram:** ainda não existem. Remover o botão "E-mail" da seção de contato e os links "E-mail"/"Instagram" do rodapé (deixar o WhatsApp como único canal); manter o trecho comentado pra reativar depois.
3. **Vídeo do hero:** colocar `cais_30s.mp4` em `assets/video/` e usar como fundo do hero (autoplay, muted, loop, playsinline, object-fit cover); remover o fundo provisório `.hero-fallback` e o aviso `.media-flag`. Depois comprimir com ffmpeg (H.264, faststart, mirando 3–8 MB).
4. **Showreel:** substituir o `.reel` placeholder por um player real (YouTube/Vimeo embed ou `<video>`); remover o `.reel-note`.
5. **Cases — vídeos:** as capas já estão no ar (em `assets/img/case-1..5.jpg`). Falta linkar cada painel ao vídeo correspondente (YouTube/Vimeo) e revisar título/categoria. Hoje os títulos são descritivos (Manifesto; Comercial ×3; Conteúdo educacional) — trocar pelos nomes reais dos projetos se desejado.

## Otimizações sugeridas (opcionais)
- Converter as fontes para **woff2** (menor) com fonttools+brotli e atualizar os `@font-face`.
  Os arquivos originais `.otf/.ttf` estão em `assets/fonts/` para isso.
- Adicionar tags Open Graph / favicon variants para compartilhamento.

## Acessibilidade / comportamento
- O ciclo automático dos painéis de Trabalhos roda em qualquer tela (inclusive toque); o hover assume no desktop.
- Há fallback para os reveals (nada fica invisível se o IntersectionObserver não disparar).
- `prefers-reduced-motion` reduz o movimento decorativo (hero), mas o ciclo de Trabalhos é navegação e segue ativo.
