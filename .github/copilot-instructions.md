<!-- .github/copilot-instructions.md -->
# Instruções rápidas para agentes de IA

Objetivo: ajudar um agente a ser imediatamente produtivo neste repositório pequeno e estático.

- **Visão geral do projeto:** este repositório é um site estático mínimo cujo comportamento principal está em `index.html`. Ele roda inteiramente no navegador e apenas faz redirecionamento rotativo para uma lista de URLs usando `localStorage` para lembrar a posição atual.

- **Arquivos-chave:**
  - `index.html` — contém a lista `urls`, o uso de `localStorage` e a lógica de redirecionamento. Alterações funcionais devem ser feitas aqui por padrão.
  - `index.js` — atualmente vazio; se o agente precisar refatorar a lógica JS para um arquivo separado, mova o código daqui e atualize `index.html` para carregar `index.js`.
  - `README.md` — arquivo mínimo; atualize se você mudar o comportamento do site ou adicionar instruções de execução.

- **Por que a estrutura é assim:** o projeto é propositalmente simples (única página). Mantém o redirecionamento no HTML para ser servido como arquivo estático sem backend.

- **Padrões e convenções do repositório:**
  - Comentários e texto de interface estão em português (ex.: `lang="pt-BR"`). Mantenha o idioma Português-BR nas mudanças de conteúdo a menos que solicitem internacionalização.
  - Mensagens de commit preferidas em português, forma imperativa curta. Ex.: `Atualiza redirecionamento: altera lista de URLs`.
  - Não introduza dependências ou build tools sem justificativa clara — o projeto foi feito para ser simples e sem dependências.

- **Como testar localmente (rápido):**
  - Método mínimo: abra `index.html` em um navegador (arrastar/soltar ou `file://`).
  - Servidor HTTP (recomendado para testes mais realistas):
    - `python3 -m http.server 8000` e abra `http://localhost:8000`.
  - Verificações úteis:
    - Abra DevTools → Console para ver erros JS.
    - Verifique em Application → Storage → Local Storage a chave `redirect_index` para confirmar o comportamento rotativo.

- **Exemplos de alterações comuns e como fazê-las:**
  - Adicionar/remover URLs: editar a array `urls` em `index.html` (cada item em string, separadas por vírgula). Preserve a lógica de incremento de índice.
  - Refatorar JS para arquivo separado: mover o bloco `<script>` para `index.js`, incluir `<script src="index.js"></script>` antes de `</head>`, e testar localmente.

- **Fluxo git recomendado antes de mudanças:**
  - `git status` — verifique alterações não commitadas
  - `git diff` — revise mudanças
  - `git add <arquivo>` && `git commit -m "Mensagem em PT-BR explicando mudança"` && `git push`

- **Restrições para agentes/automações:**
  - Não altere o idioma do documento sem pedir aprovação.
  - Se remover `localStorage` ou mudar a chave `redirect_index`, adicione uma nota no `README.md` explicando a nova semântica.
  - Evite criar arquivos de build (package.json, node_modules) a menos que peça explicitamente o suporte a builds.

- **Sugestão de PR/commit message:**
  - Título: `Atualiza redirecionamento: <breve descrição>`
  - Descrição: explique por que mudou a lista de URLs ou por que extraiu JS para `index.js`.

- **Padrões para agentes ao editar código:**
  - Mantenha mudanças pequenas e testáveis — prefira vários commits pequenos a um grande commit.
  - Inclua motivos nas mensagens de commit (por exemplo: `corrige url quebrada`, `remove url expirou em 2025-11-25`).

Se algo aqui estiver incompleto ou se você quiser que eu siga um estilo de commit/PR diferente, diga qual e eu atualizo este arquivo.
