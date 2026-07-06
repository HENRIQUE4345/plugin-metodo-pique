---
name: metodo
description: "Conhecimento do metodo de trabalho com Claude Code: os modos de trabalho (Pensar/Produzir/Afiar), o trilho TAREFAS.md (SEMANA -> HOJE -> backlog), o ciclo do dia e da semana, a estrutura de segundo cerebro em 5 pastas e o inbox. Auto-invoca quando o usuario mencionar modo de trabalho, Pensar/Produzir/Afiar, trilho, TAREFAS, foco do dia ou da semana, planejar, organizar tarefas, o que fazer agora, WIP/muitas janelas abertas, ou quando disser que esta perdido, travado ou dando voltas."
---

# Skill: Metodo de Trabalho

Este e o metodo de trabalhar com o Claude Code de forma focada: um trilho de tarefas, um punhado de rituais, e a disciplina de saber em que modo voce esta. Nada aqui depende de ferramenta de empresa — so de um segundo cerebro em markdown.

## Quando esta skill e relevante

Invocar quando o usuario mencionar:
- Modo de trabalho, Pensar/Produzir/Afiar, "que modo e esse"
- Trilho, TAREFAS.md, HOJE, SEMANA, backlog, foco
- Planejar o dia/semana, "o que faco agora", organizar tarefas
- **"To perdido / travado / dando voltas / nao sei por onde comecar"** (gatilho de maior valor — aplique o teste do modo, abaixo)
- WIP, muitas janelas/abas abertas, misturar coisas

## Os modos de trabalho (o coracao do metodo)

Todo trabalho cai em um de tres modos. A clareza do dia vem de saber em qual voce esta — e ficar nele. O caos vem de trocar de modo no meio sem perceber.

| Modo | O que e | A unica coisa que importa (o output) |
|---|---|---|
| **Pensar** | Decidir, mapear, arquitetar, download mental, planejar | Uma decisao / clareza — nenhum artefato final ainda |
| **Produzir** | Executar o trabalho que entrega valor | O artefato pronto (entregavel, feature, documento) |
| **Afiar** | Construir/melhorar a propria ferramenta (skill, automacao, o cerebro) | Uma capability reutilizavel, pronta e guardada |

> Os modos sao **parametrizaveis**: eles vivem na legenda do topo do seu `TAREFAS.md`. Pensar/Produzir/Afiar sao o default. Quem nao constroi as proprias ferramentas pode nem usar **Afiar**; quem tem um trabalho de outra natureza pode definir os proprios modos (ex. `Consultar`, `Preparar`, `Gravar`, `Cobrar`) — o mecanismo e o mesmo, o vocabulario e seu.

## Regras de ouro (inegociaveis)

- **Nunca misture Produzir e Afiar na mesma janela.** Afiar e viciante e sempre rouba o tempo do Produzir (que e o que paga). Bateu vontade de afiar no meio de uma entrega? Anota no trilho e volta.
- **Afiar e bloco agendado, nunca impulso** — e termina com a ferramenta guardada (senao vira mais uma coisa pela metade).
- **WIP <= 2 frentes vivas.** Frente demais = nada termina. Se bater impaciencia com a espera, calibre o modelo/velocidade — nao abra mais uma janela.
- **O teste do travamento:** quando travar ("to perdido"), pergunte **"que modo e esse, e qual o output em 1 frase?"**. Se voce nao consegue dizer o output, o trabalho nao esta definido — volte pro Pensar.

## O trilho — TAREFAS.md

Um unico arquivo markdown na raiz do cerebro. E o trilho de execucao pessoal — **o que EU faco**. Camadas:

- **SEMANA** — o foco da semana (5-8 itens macro), gerado uma vez (segunda cedo).
- **HOJE** — 3-6 itens em ordem de execucao, cada um etiquetado por modo. **O HOJE puxa do SEMANA, nao do backlog inteiro** — e isso que mantem o foco.
- **AGUARDANDO / DECISOES / FRENTES / RESTO** — o que depende de terceiros (cobrar), o que so voce decide, os trabalhos grandes em curso, e o backlog.

Principio: **o trilho e descartavel** (regenera por semana e olha pra frente); o registro duravel do que foi feito vai pro `log-do-feito.md` (que acumula e olha pra tras). O template do trilho vem do plugin: `templates/TAREFAS.template.md`.

## O ciclo (dia e semana)

```
planejar a semana  ->  montar o HOJE  ->  /iniciar  ->  [trabalho num modo so]  ->  /encerrar
(monta o SEMANA)       (puxa do SEMANA)  (carimba +                              (carimba fim,
                                          carrega o modo)                         move pro log)
```

- `/metodo-pique:iniciar` — puxa o proximo item do HOJE, carimba o inicio e carrega o modo.
- `/metodo-pique:encerrar` — no fim da conversa, distribui o que foi discutido pros lugares certos do cerebro, fecha o item e loga.
- `/metodo-pique:inbox` — processa o inbox e deixa ele vazio.

## A estrutura de cerebro (5 pastas) + inbox

Todo conteudo vai em uma de 5 pastas fixas:
```
projetos/       — coisas com prazo e objetivo definido
areas/          — responsabilidades continuas sem prazo
conhecimento/   — tudo aprendido + referencias + metodologias
sessoes/        — brainstorms, reunioes, downloads mentais
arquivo/        — inativos: concluidos, pausados, obsoletos
```
Regras: max 2 niveis; ~150 linhas por doc; um tema por arquivo; nome em kebab-case sem acento, com a data primeiro (`YYYY-MM-DD-descricao.md`); nunca deletar (mover pra `arquivo/`); nada automatico (a IA sugere, voce aprova).

O **inbox** e a porta de entrada: um `DIARIO.md` (log do dia) + `REVISAO.md` (correcoes) + `contextos/` (outputs de chats). Processa no fim do dia com `/metodo-pique:inbox`. **O inbox sempre termina vazio** — se acumular arquivo sem destino, o canal perde a funcao.

## Comandos disponiveis

- `/metodo-pique:iniciar` — puxa o proximo item do HOJE + carrega o modo
- `/metodo-pique:encerrar` — fecha a conversa, distribui pro cerebro, loga o feito
- `/metodo-pique:inbox` — processa o inbox (termina vazio)
- `/metodo-pique:modelo` — recomenda modelo + effort pra uma tarefa

## Calibragem (dev vs nao-dev)

**Pensar** e **Produzir** servem a qualquer pessoa (decidir vs entregar). **Afiar** so faz sentido pra quem constroi as proprias ferramentas — se voce nao "afia", ignore esse modo e a regra de nao-misturar. Como os modos vivem na legenda do seu `TAREFAS.md`, e la que voce escolhe quais valem pra voce.
