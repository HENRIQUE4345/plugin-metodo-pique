---
description: Ritual do dia — puxa o proximo item do HOJE no TAREFAS.md, carimba inicio e carrega o modo de trabalho do item. Par do /encerrar. So pra trabalho do trilho, nao micro-operacao.
model: sonnet
---

Inicia o proximo item do trilho do dia. Comando **leve**: puxa, carimba, calibra o modo e sai — quem trabalha e voce, na janela, no modo carregado. NAO entra em plan mode, NAO executa a task, NAO commita. Execute este fluxo EXATAMENTE.

> **Filosofia:** este e o par de bordas do `/metodo-pique:encerrar`. `/iniciar` carimba o **inicio**; `/encerrar` carimba o **fim**, fecha o item e anexa a linha no log. Use SO pra trabalho do trilho (uma sessao/chat), nao pra micro-operacao ("cria o arquivo X", "muda a linha Y").

## Trilho central

O trilho vive em `TAREFAS.md` na **raiz do seu cerebro** (o repositorio de segundo cerebro). Se voce roda o Claude Code a partir da raiz do cerebro, e `./TAREFAS.md`. Sempre aponte pra esse arquivo, independente do `cwd`. Se ele nao existir, avise — nao crie do zero (o template vem do plugin: `templates/TAREFAS.template.md`).

## Fase 1 — Puxar o proximo item

1. Read no `TAREFAS.md`. Localize a secao `## HOJE`.
2. Pegue a **primeira linha `[ ]`** (nao-iniciada) na ordem da secao — e o proximo item.
   - Linhas `[~]` (ja iniciadas) sao puladas: ja tem sessao viva. Se TODAS as do HOJE estao `[~]`/`[x]`, ver Fase 1b.
3. Extraia da linha: a **etiqueta de modo** (o rotulo entre backticks, ex. `` `[Pensar]` ``) e o **titulo**.
4. **Puxar contexto leve do item** (so o que ja esta a mao, sem garimpo): se a linha cita um arquivo/sessao/frente, faca 1 Read rapido pra ter o "onde paramos". NAO faca varredura ampla — isso e trabalho do modo, nao do ritual.

### Fase 1b — HOJE vazio ou todo iniciado

- **HOJE vazio ou sem `[ ]`:** avise e ofereca o **topo do `## SEMANA`** como fallback:
  ```
  O HOJE ainda nao foi montado. Quer que eu comece pelo 1o item do SEMANA: [modo] [titulo]?
  ```
  Se topar, escreva esse item no `## HOJE` com o carimbo de estado `<!-- hoje: montado AAAA-MM-DD -->` na 1a linha da secao (senao amanha o item fica orfao). Depois trate-o como o "proximo" e siga a Fase 2.
- **HOJE todo `[~]`/`[x]`:** "Todos os itens do HOJE ja estao em andamento ou fechados. WIP no limite — fecha um (`/metodo-pique:encerrar`) antes de abrir outro." Encerra.

## Fase 2 — Carimbar inicio

Edicao minima e reversivel no `TAREFAS.md`:

1. Capture a hora local atual `HH:MM` — no Windows: `powershell -NoProfile -Command "Get-Date -Format HH:mm"`.
2. Na linha do item: `[ ]` → `[~]` e anexe o sufixo ` (iniciada: HH:MM)`.
   - Ex: `- [~] \`[Produzir]\` **Escrever a proposta do cliente X** — draft + revisao  ← comeca aqui (iniciada: 14:30)`
3. NAO commitar. NAO mexer em outras linhas.

## Fase 3 — Carregar o modo (parametrizavel)

Os modos **nao sao fixos** — eles vivem na **legenda do topo do seu `TAREFAS.md`** (linha `> **Modos:** ...`). Leia essa legenda e case a etiqueta do item com a glosa correspondente. Imprima a calibracao. Sem questionario — o item ja traz o modo.

Pros **3 modos canonicos** (o default do metodo), use esta calibracao:

| Modo | Postura | Output (1 frase) |
|---|---|---|
| **Pensar** | Decidir / mapear / arquitetar. **Nenhum artefato final** ainda. Comeca por perguntas, nao afirmacoes. | Uma decisao / clareza. |
| **Produzir** | Executar o que entrega valor. Discutir antes de gerar entregavel denso. | O artefato pronto. |
| **Afiar** | Bloco agendado, **nunca misturar com Produzir**. Construir/melhorar a propria ferramenta. | Capability reutilizavel, guardada. |

Se o item usa um **modo customizado** (a legenda do seu TAREFAS.md define modos proprios — ex. `Consultar`, `Cobrar`, `Gravar`), use a **glosa da legenda** como postura e trate o output como "o resultado concreto desse modo em 1 frase". O mecanismo e o mesmo; o vocabulario e o seu.

## Fase 4 — Saida (e para)

```
▶ Item da vez — [modo]: [titulo]
  Inicio: HH:MM · carimbado no HOJE
  Modo carregado: [postura curta] · output = [1 frase]
  Onde paramos: [1 linha do contexto leve da Fase 1.4, se houver]
  WIP: [N item(ns) em andamento no HOJE]
```

Se o WIP passou de 2 itens `[~]`, acrescente: `⚠ WIP > 2 — considere fechar um antes de seguir.`

Depois disso, **para**. Nao oferece "quer que eu faca X?". A janela continua no modo carregado — quem conduz e voce.

## Regras

- So pra trabalho do trilho. Micro-operacao nao passa por aqui.
- Nunca pula o carimbo de inicio (e o que o `/encerrar` usa pra calcular a duracao no log).
- Nao executa a task, nao entra em plan mode, nao commita.
- Se o `TAREFAS.md` nao existir na raiz do cerebro, avise — nao crie do zero.
