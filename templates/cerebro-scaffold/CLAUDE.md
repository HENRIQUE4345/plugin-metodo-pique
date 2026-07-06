# Segundo Cerebro — {NOME}

Este e o segundo cerebro do {NOME}. Markdown puro, estruturado para IA.
O mapa completo esta em `_mapa.md` — consultar SEMPRE antes de buscar arquivos.

## Quem sou eu

- {1-2 linhas: quem e voce, o que faz, contexto de trabalho}
- Lingua: {idioma}, comunicacao direta.

## Estrutura

5 pastas fixas de conteudo + infraestrutura:

```
projetos/       — Coisas com prazo e objetivo definido.
areas/          — Responsabilidades continuas sem prazo.
conhecimento/   — Tudo aprendido + referencias + metodologias, por subtema.
sessoes/        — Temporal: brainstorms, reunioes, downloads mentais.
arquivo/        — Inativos: projetos concluidos, pausados, obsoletos.
```

Infraestrutura:
```
inbox/          — Porta de entrada. DIARIO.md (log do dia) + REVISAO.md (correcoes) + contextos/.
diarios/        — Arquivo historico dos diarios processados (YYYY-MM-DD.md).
_mapa.md        — Indice local do cerebro.
TAREFAS.md      — Trilho central de execucao (ver secao abaixo).
CLAUDE.md       — Este arquivo.
```

## Canais de entrada

| Canal | O que entra | Quando processa |
|-------|------------|-----------------|
| `inbox/DIARIO.md` | Tudo do dia: ideias, lembretes, acoes, pensamentos | Fim do dia (`/metodo-pique:inbox`) |
| `inbox/REVISAO.md` | Correcoes/ajustes a fazer no cerebro | Quando quiser |
| `inbox/contextos/` | Output de chats com IA, investigacoes, brainstorms | Quando quiser |

### Formato do DIARIO.md
```
[HH:MM] [ORIGEM] [TIPO]: conteudo
```

## Trilho de tarefas (TAREFAS.md)

`TAREFAS.md` (raiz) e o **trilho central de execucao** — o que EU faco. Camadas:
- **SEMANA** — foco da semana (5-8 itens), gerado no inicio da semana.
- **HOJE** — 3-6 itens em ordem, cada um etiquetado por modo. O HOJE **puxa do SEMANA**, nao do backlog inteiro.
- **AGUARDANDO** (cobrar terceiros) · **DECISOES** (so eu decido) · **FRENTES** (grandes em curso) · **RESTO/BACKLOG**.

O trilho e descartavel (regenera por semana); o registro do que foi feito vai pro `log-do-feito.md`.
Marcadores: `[ ]` a fazer · `[~]` em andamento · `[x]` feito.

## Rituais e modos de trabalho

Todo trabalho e de um **modo** (a legenda vive no topo do `TAREFAS.md`; default: `Pensar` decidir/mapear · `Produzir` entregar o que importa · `Afiar` melhorar a propria ferramenta). Regras: nunca misturar Produzir e Afiar; Afiar e bloco agendado; WIP <= 2; travou? "que modo e esse, e qual o output em 1 frase?".

Comandos (plugin `metodo-pique`): `/metodo-pique:iniciar` · `/metodo-pique:encerrar` · `/metodo-pique:inbox` · `/metodo-pique:modelo`.

## Regras para o Agente

1. Consultar `_mapa.md` antes de buscar ou criar arquivos.
2. Ao criar arquivo novo: usar o template padrao, atualizar `_mapa.md`.
3. Nunca deletar arquivo — mover para `arquivo/` e atualizar `_mapa.md`.
4. Nomes em kebab-case, sem acento, com a data primeiro (`YYYY-MM-DD-descricao.md`).
5. Um tema por arquivo. Se passar de ~150 linhas, dividir.
6. Nada automatico — a IA sugere, o humano aprova.

## Template padrao de arquivo

```
# [Titulo descritivo]

**Criado:** YYYY-MM-DD
**Status:** ativo | arquivado
**Tags:** tag1, tag2

## Contexto
Por que isso existe.

## Conteudo
O conteudo principal.
```
