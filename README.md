# metodo-pique

Um método de trabalho com o **Claude Code**, empacotado como plugin. Genérico e parametrizável — sem acoplamento a ferramenta de empresa nenhuma. Pensado pra quem quer operar um **segundo cérebro** em markdown com foco: um trilho de tarefas, alguns rituais e a disciplina de saber em que **modo** você está.

> Extraído do sistema de trabalho do Henrique (Pique Digital) e limpo pra servir a qualquer pessoa.

## O que vem no pacote

**Comandos:**
- `/metodo-pique:iniciar` — puxa o próximo item do `HOJE` no `TAREFAS.md`, carimba o início e carrega o modo de trabalho do item.
- `/metodo-pique:encerrar` — no fim da conversa, varre o que foi discutido e distribui pros lugares certos do cérebro; fecha o item do trilho e loga o feito. Roda sozinho, tudo local e reversível por git.
- `/metodo-pique:inbox` — processa o inbox (DIARIO + REVISAO + contextos), gera um `PLANO.md` pra você revisar e, após confirmação, executa e deixa o inbox vazio.
- `/metodo-pique:modelo` — recomenda modelo + effort ideal pra uma tarefa (framework A/B/C).

**Skill:**
- `metodo` — conhecimento auto-invocado sobre os modos (Pensar/Produzir/Afiar), o trilho, o ciclo do dia/semana e a estrutura de cérebro. Ativa quando você fala de foco/tarefas — ou quando diz que está travado.

**Templates** (`templates/`):
- `TAREFAS.template.md` — o trilho vazio, parametrizável.
- `CLAUDE-metodo.md` — bloco de 2 seções pra colar no `CLAUDE.md` do seu cérebro.
- `cerebro-scaffold/` — um segundo cérebro inicial completo (5 pastas + inbox + `_mapa.md` + `CLAUDE.md`) pra quem ainda não tem um.

## Instalação

Requer o [Claude Code](https://claude.com/claude-code).

**Via marketplace:**
```
/plugin marketplace add HENRIQUE4345/plugin-metodo-pique
/plugin install metodo-pique@metodo-pique-marketplace
```

**Dev / local:**
```
claude --plugin-dir /caminho/para/plugin-metodo-pique
```

**Validar a estrutura:**
```
claude plugin validate ./plugin-metodo-pique
```

## Como começar (do zero)

1. Instale o plugin.
2. Se você **já tem** um cérebro em markdown: copie `templates/TAREFAS.template.md` pra raiz dele como `TAREFAS.md` (preencha `{NOME}` e a legenda de modos), e cole as 2 seções de `templates/CLAUDE-metodo.md` no seu `CLAUDE.md`.
3. Se você **não tem** cérebro ainda: copie `templates/cerebro-scaffold/` pra uma pasta nova, troque os `{NOME}`/placeholders, e `git init`.
4. No dia a dia: `/metodo-pique:iniciar` pra abrir um item · trabalhe no modo carregado · `/metodo-pique:encerrar` pra fechar · `/metodo-pique:inbox` no fim do dia.

## Os modos (o coração do método)

Todo trabalho é de um modo — e a clareza vem de saber em qual você está e ficar nele:

| Modo | O que é | O output |
|---|---|---|
| **Pensar** | Decidir, mapear, arquitetar, planejar | Uma decisão / clareza |
| **Produzir** | Executar o que entrega valor | O artefato pronto |
| **Afiar** | Melhorar a própria ferramenta | Uma capability guardada |

Regras de ouro: nunca misture **Produzir** e **Afiar** na mesma janela · **Afiar** é bloco agendado, nunca impulso · WIP ≤ 2 frentes vivas · travou? pergunte *"que modo é esse, e qual o output em 1 frase?"*.

Os modos são **parametrizáveis**: vivem na legenda do topo do seu `TAREFAS.md`. Quem não constrói ferramentas ignora **Afiar**; quem tem outra natureza de trabalho define os próprios (`Consultar`, `Preparar`, `Gravar`, `Cobrar`…).

## Licença

Uso livre. Adapte à vontade.
