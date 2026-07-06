<!--
  Bloco do metodo de trabalho — cole estas 2 secoes no CLAUDE.md do seu cerebro
  (depois da secao de estrutura/inbox). Elas ensinam o agente a operar o trilho e os rituais.
  Requer o plugin `metodo-pique` instalado (fornece /iniciar, /encerrar, /inbox, /modelo).
-->

## Trilho de tarefas (TAREFAS.md)

`TAREFAS.md` (na raiz do cerebro) e o **trilho central de execucao** — o que EU faco. Camadas:

- **SEMANA** — o foco da semana (5-8 itens macro), gerado no inicio da semana.
- **HOJE** — 3-6 itens em ordem de execucao, cada um etiquetado por modo. O HOJE **puxa do SEMANA**, nao do backlog inteiro — e isso que mantem o foco.
- **AGUARDANDO** — o que espero de terceiros e preciso cobrar. **DECISOES** — o que so eu decido. **FRENTES** — os trabalhos grandes em curso. **RESTO/BACKLOG** — por importancia.

O trilho e descartavel (regenera por semana, olha pra frente); o registro duravel do que foi feito vai pro `log-do-feito.md` (acumula, olha pra tras).

**Marcadores:** `[ ]` a fazer · `[~]` em andamento · `[x]` feito. A etiqueta de modo vem em backticks logo apos o checkbox.

## Rituais e modos de trabalho

Todo trabalho e de um **modo** — e a clareza vem de saber em qual voce esta e ficar nele. Os modos vivem na legenda do topo do `TAREFAS.md` (default: `Pensar` decidir/mapear · `Produzir` entregar o que importa · `Afiar` melhorar a propria ferramenta). Regras de ouro: **nunca misturar Produzir e Afiar** na mesma janela; **Afiar e bloco agendado, nunca impulso**; **WIP <= 2** frentes vivas; travou? pergunte "**que modo e esse, e qual o output em 1 frase?**".

Rituais (comandos do plugin `metodo-pique`):
- `/metodo-pique:iniciar` — puxa o proximo item do HOJE, carimba o inicio e carrega o modo.
- `/metodo-pique:encerrar` — no fim da conversa, distribui o que foi discutido pro cerebro, fecha o item do trilho e loga o feito.
- `/metodo-pique:inbox` — processa o inbox e deixa ele vazio.
- `/metodo-pique:modelo` — recomenda modelo + effort pra uma tarefa.
