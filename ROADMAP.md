# Roadmap — metodo-pique

O metodo evolui com o tempo. Este arquivo e o trilho do proprio plugin: o que ja
entrega, o que vem, e o que ficou de fora de proposito (com o porque).

## Feito — v1.1.0 (2026-07-06)

- **Comandos:** `iniciar`, `encerrar`, `inbox`, `modelo`, `setup`.
- **Skill:** `metodo` (auto-invoca, inclusive no "to travado/perdido").
- **Templates:** `TAREFAS.template.md`, `CLAUDE-metodo.md`, `cerebro-scaffold/` (molde de cerebro completo).
- **Modos parametrizaveis** pela legenda do `TAREFAS.md` de cada pessoa (default Pensar/Produzir/Afiar; `/setup` calibra por perfil — nao empurra Afiar pra quem nao constroi ferramenta).
- **Fonte unica:** o molde de cerebro vive so aqui; o `/setup` instancia de dentro do plugin e nao deixa lixo de setup.

## Proximo — v1.1.x (o ciclo completo do dia/semana)

Destilar os rituais que hoje ficaram de fora, tirando o acoplamento a Google Calendar:

- **`bom-dia`** — monta o `## HOJE` puxando do `## SEMANA` (hoje o original le a agenda + ClickUp; a versao generica monta so do trilho + do que a pessoa registrar).
- **`boa-noite`** — balanco do dia (quantas Pensar/Produzir por modo; planejado vs ad-hoc) e devolve ao backlog o que nao fechou.
- **`planejamento-semanal`** — monta o `## SEMANA` a partir do RESTO/BACKLOG.

Com esses tres, o `TAREFAS.md` passa a se auto-montar (hoje o HOJE/SEMANA e montado na mao).

## Depois — v2 (subsistema de telemetria)

- **`continuar`** (retomar sessao anterior), **`tempo`** (consulta de tempo/custo), **`dashboard`** (uso de IA).
- Dependem de embarcar um **hook de abertura** que registra a sessao + um gerador proprio. So vale se houver demanda real — nao e o coracao do metodo.

## Extensao separada — `metodo-dev` (nao entra no core)

O ciclo de dev do Henrique (spec/headless, escolha de modelo/effort por tarefa, extended thinking) e puramente tecnico. Se virar demanda, sai como um **plugin de extensao** proprio, nao no metodo generico — pra nao confundir quem nao e dev.

## Ideias soltas (sem prioridade)

- `auditoria-cerebro` destilado (os 8 eixos de auditoria de um cerebro em markdown, sem o encanamento de submodule).
- Suporte a idioma no `/setup` (hoje assume o idioma que a pessoa pedir; poderia gerar o cerebro ja no idioma).
