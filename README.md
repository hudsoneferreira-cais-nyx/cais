# Site cais estúdio — como finalizar e publicar

Este pacote é o site pronto para a reta final: preencher o conteúdo real e publicar num domínio.

## O que tem aqui
- `index.html` — o site inteiro.
- `assets/` — fontes e logo.
- `CLAUDE.md` — contexto do projeto (o Claude Code lê isso automaticamente).
- `README.md` — este arquivo.

## Ver o site agora (sem instalar nada)
Abra o `index.html` no navegador (dois cliques). Tudo funciona localmente.

## Finalizar no Claude Code

### 1. Abrir o projeto
- **Mais fácil (sem terminal):** instale o **app de desktop do Claude** (macOS/Windows), que já traz o
  Claude Code com interface gráfica. Abra a pasta `cais-site` por lá.
- **Terminal:** instale pelo instalador nativo (não precisa de Node.js) e rode `claude` dentro da pasta.
- Você já tem **Claude Pro**, que dá acesso ao Claude Code — é só entrar com a sua conta.

### 2. O que pedir (em português mesmo)
Exemplos de comandos para o Code:
- "Troca o número de WhatsApp `55SEUNUMERO` por `5524999999999` em todo o site."
- "Coloca o e-mail real `contato@caisestudio.com.br` no lugar do placeholder."
- "Põe o link do nosso Instagram no rodapé."
- "Insere este vídeo de showreel como fundo do hero e remove o fundo provisório."
- "Substitui os 5 cases de exemplo por estes projetos reais (nome, categoria e imagem)."
- "Converte as fontes para woff2 para o site carregar mais rápido."

> Dica: a lista completa de placeholders a preencher está no `CLAUDE.md`, seção **TODO**.

### 3. Publicar (deploy)
Site estático publica em minutos e de graça. Peça ao Code, por exemplo:
- "Cria um repositório git e publica este site na **Vercel**." (ou Netlify / Cloudflare Pages)
- O Code configura o deploy e te dá uma URL provisória (ex.: `cais.vercel.app`).

### 4. Domínio próprio
- Registre o domínio (ex.: `caisestudio.com.br` no registro.br).
- Peça ao Code: "Aponta o domínio `caisestudio.com.br` para este deploy" — ele te passa os
  registros de DNS para configurar no painel do registrador.

A partir daí, toda mudança que você pedir ao Code e publicar atualiza o site no ar **na hora** —
sem o vai-e-volta de link que a gente teve aqui.
