# Site da Bússola IA

Site estático de três páginas para a Bússola IA, consultoria em agentes de IA
para pequenos negócios. HTML puro, sem build e sem dependência externa: basta
dar duplo clique em `index.html`.

## Arquivos

| Arquivo | O que é |
|---|---|
| `index.html` | Página inicial |
| `calculadora.html` | Simulação de proposta |
| `perguntas.html` | Perguntas frequentes |
| `estilo.css` | Visual compartilhado das três páginas, com a lista de classes no topo |
| `contexto-negocio.md` | Fonte de verdade dos fatos do negócio |
| `AGENTS.md` / `CLAUDE.md` | Regras para os agentes que trabalham na pasta |

## Estado

As três páginas estão em construção: cabeçalho, navegação, rodapé e estilo já
existem; o conteúdo de cada `<main>` será escrito por um agente.

## Regras rápidas

Cabeçalho, navegação e rodapé são idênticos byte por byte nas três páginas.
Só se mexe dentro do `<main>`, só com classes de `estilo.css`, e todo fato sai
de `contexto-negocio.md`. O detalhe está em `AGENTS.md`.
