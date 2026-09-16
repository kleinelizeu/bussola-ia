# Regras do projeto — site da Bússola IA

Leia este arquivo inteiro antes de escrever qualquer linha. Ele vale para todo
agente que trabalha nesta pasta.

O site tem três páginas: `index.html`, `calculadora.html` e `perguntas.html`.
Cada página é tarefa de um agente diferente.

---

## 1. Mexa só no seu arquivo

- Edite **apenas** o arquivo da sua tarefa. Nada mais.
- Não edite `estilo.css`, `contexto-negocio.md`, `AGENTS.md`, `CLAUDE.md`,
  `README.md`, `.gitignore` nem as páginas dos outros agentes.
- Não crie arquivos novos.
- Se faltar alguma coisa fora do seu arquivo, **pare e avise a pessoa**. Não
  resolva por conta própria.

## 2. Mexa só dentro do `<main>`

- Altere **somente** o conteúdo entre `<main id="conteudo">` e
  `</main>`.
- O `<head>` você pode ajustar apenas no `<title>` e na `<meta name="description">`.
- **Cabeçalho, navegação e rodapé são intocáveis.** Eles são idênticos byte por
  byte nas três páginas. Se você mudar uma vírgula, o site fica torto.
- Não acrescente nem remova nada antes do `<main>` ou depois do `</main>`,
  fora das duas linhas do `<head>` citadas acima.

## 3. Use só o que já existe em `estilo.css`

- Use **apenas** as classes listadas no comentário do topo de `estilo.css`.
- **Não crie CSS.** Nada de `<style>` na página, nada de atributo `style=`,
  nada de arquivo `.css` novo.
- **Não crie arquivo `.js` separado.** Se a sua página precisar de
  comportamento (o caso da calculadora), use um `<script>` curto no fim do
  próprio `<main>`, em JavaScript puro.
- Se uma classe de que você precisa não existe, resolva com as que existem ou
  **pare e avise a pessoa**.

## 4. HTML puro, sem nada de fora

- A página tem que abrir com **duplo clique** no arquivo, direto do disco.
- Sem build, sem npm, sem framework, sem TypeScript, sem pré-processador.
- **Nada vindo de CDN**: nenhuma fonte externa, nenhum ícone externo, nenhuma
  biblioteca externa, nenhuma imagem externa.
- Sem `fetch`, sem chamada de rede, sem `localStorage` obrigatório para a
  página funcionar.
- Escreva HTML acessível: hierarquia de títulos correta, `label` ligado a cada
  campo, texto alternativo onde couber.

## 5. Os fatos vêm só de `contexto-negocio.md`

- Nome, pessoa, cidade, WhatsApp, promessa, público, pacotes, preços, prazos,
  formas de pagamento e horas economizadas: tudo sai de `contexto-negocio.md`.
- **Não invente nada.** Sem depoimento, sem cliente, sem logo, sem número de
  faturamento, sem prêmio, sem equipe, sem e-mail, sem endereço, sem rede social.
- Todo link de contato aponta para `https://wa.me/5500000000000`.
- Tom: direto, sem tecnicês, falando com "você", frases curtas, **sem emoji**.
- **Nunca prometa resultado garantido.** As horas são médias de clientes; escreva
  sempre como estimativa.

## 6. Git: você não faz commit por conta própria

- **Nunca** faça commit sozinho.
- **Nunca** faça `push`.
- **Nunca** crie branch e nunca troque de branch.
- Ao terminar a tarefa, você **PARA** e espera a pessoa conferir.
- Só depois que a pessoa disser que aprovou, você faz o commit — e **apenas dos
  arquivos da sua tarefa**, nomeados um a um:

  ```
  git add calculadora.html
  git commit -m "Página de simulação de proposta"
  ```

- Nada de `git add .`, nada de `git add -A`, nada de `git commit -a`.
- Mensagem curta, em português, no que foi feito.

## 7. Se você é o orquestrador

Quem trabalha na **pasta principal** do projeto tem a função de integrar. Isso
muda o que a regra 6 permite:

- O orquestrador pode fazer `merge`, `commit` e `push` **quando a pessoa pedir**.
- O orquestrador pode tocar em qualquer arquivo da pasta, inclusive `estilo.css`,
  `contexto-negocio.md` e este arquivo de regras.
- O orquestrador é quem junta o trabalho dos agentes, confere se cabeçalho,
  navegação e rodapé continuam idênticos nas três páginas, e resolve conflito.
- Agente que trabalha em worktree ou em tarefa isolada **não** é orquestrador e
  continua preso à regra 6.

## 8. Ao terminar

Faça estes três passos, nesta ordem:

1. Marque a worktree como pronta para revisão:

   ```
   orca worktree set --worktree active --workspace-status in-review --comment '<o que entregou>'
   ```

2. Abra a sua própria página no navegador do Orca, sem subir servidor local:

   ```
   orca tab create --url file:///Users/kleinelizeu/bussola-ia/index.html
   ```

   Troque o arquivo pelo da sua tarefa (`calculadora.html` ou `perguntas.html`).
   É `file://` com o caminho absoluto. Não rode `python -m http.server`, nem
   `npx serve`, nem nada parecido.

3. Devolva um **resumo de três linhas**: o que você fez, o que usou de
   `contexto-negocio.md`, e o que ficou faltando ou precisa de decisão da pessoa.

Depois disso, pare e espere.
