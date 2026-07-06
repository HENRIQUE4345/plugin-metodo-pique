# Extrair Contexto de Conversa

Prompt para usar ao final de qualquer conversa produtiva (brainstorm, investigacao, pesquisa, download mental).
Funciona em: Claude Desktop, Claude Chrome, Claude Code.

Cole o prompt abaixo ou use como atalho. O Claude vai analisar tudo que foi discutido e gerar um documento .md pronto para salvar em `inbox/contextos/`.

---

## Prompt

Analise TODA a conversa acima e gere um documento de contexto extraindo os insumos mais relevantes.

## O que extrair

Identifique e organize nos blocos abaixo (inclua apenas os blocos que tiverem conteudo real — nao force blocos vazios):

1. **Resumo** — Do que se trata a conversa, em 2-3 frases objetivas.
2. **Insights e aprendizados** — Coisas que eu entendi, aprendi ou que ficaram claras durante a conversa. Cada item deve ser autocontido (fazer sentido fora do contexto do chat).
3. **Ideias que surgiram** — Ideias novas, possibilidades, coisas para explorar. Separar ideias concretas de especulacoes.
4. **Decisoes tomadas** — Se alguma decisao foi batida durante a conversa, registrar com o racional por tras.
5. **Informacoes uteis** — Dados, referencias, comparativos, numeros, ou qualquer informacao factual relevante que vale guardar.
6. **Duvidas abertas** — Perguntas que ficaram sem resposta ou pontos que preciso investigar mais.
7. **Proximos passos** — Acoes concretas que derivam da conversa (se houver).

## Formato de saida

Gere o documento COMPLETO no formato abaixo. Nao resuma demais — prefira manter riqueza de conteudo a ser generico. Cada item deve fazer sentido isoladamente, sem depender do contexto da conversa.

# [Titulo descritivo do tema da conversa]

**Criado:** [data de hoje, YYYY-MM-DD]
**Status:** ativo
**Tags:** [tags relevantes separadas por virgula]
**Tipo:** [brainstorm | investigacao | download-mental | conceito | pesquisa]

## Resumo

[2-3 frases]

## Insights e Aprendizados

- [insight 1]
- [insight 2]

## Ideias

- [ideia 1]
- [ideia 2]

## Decisoes

- [decisao]: [racional]

## Informacoes Uteis

[conteudo factual, dados, referencias]

## Duvidas Abertas

- [duvida 1]

## Proximos Passos

- [ ] [acao 1]
- [ ] [acao 2]

## Regras

- Titulo deve ser descritivo do TEMA, nao "Resumo da conversa".
- Tags validas de dominio: trabalho, saude, financas, casa, estudos, hobbies, relacionamento, produtividade.
- Tags validas de tipo: decisao, aprendizado, ideia, referencia, reflexao.
- Inclua tags de dominio + tipo.
- O nome sugerido para o arquivo deve ser em kebab-case, sem acentos, descritivo. Exemplo: `investigacao-tema.md`, `brainstorm-projeto-x.md`.
- Ao final do documento, sugira o nome do arquivo e o caminho completo: `inbox/contextos/[nome-do-arquivo].md`

Se voce tiver acesso ao filesystem, salve diretamente na pasta do cerebro em `inbox/contextos/[nome].md`. Se nao tiver, gere o documento completo para eu copiar.
