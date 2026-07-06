---
description: Encerramento de conversa. Varre tudo que foi discutido e distribui pros lugares certos no seu cerebro. Execute este fluxo EXATAMENTE, sem pular etapas.
model: sonnet
---

Encerramento de conversa. Processa tudo que foi discutido e distribui pros lugares certos no seu segundo cerebro (arquivos markdown). Execute este fluxo EXATAMENTE, sem pular etapas.

## Como funciona

Esta skill **nao executa nenhuma acao externa que mexa com outra pessoa** (nao manda mensagem, nao cria evento, nao chama ferramenta de terceiros). Tudo que ela faz e **local e reversivel por git**. Por isso ela roda sozinha ate o fim, SEM pedir "posso executar?".

Voce fornece o **julgamento** (o que salvar, onde, como classificar, a mensagem de commit); o resto e escrever arquivo e commitar. Sem scripts — tudo com os tools de edicao e `git` na mao.

Acoes que envolvem outras pessoas (uma tarefa a delegar, um compromisso a marcar) viram so **registro** na lista "Ficou em aberto" do resumo final — quando voce precisar, voce faz na hora.

## Quando usar

- Ao final de qualquer conversa que teve conteudo acionavel.
- Apos brainstorm, analise, discussao, planejamento, transcricao, duvida resolvida.
- Quando voce disser "encerra", "fecha", "salva tudo", ou quando a conversa naturalmente chegar ao fim.

---

## Fase 1: Varredura da conversa (automatico, NAO pergunte nada)

### 1.0 Regra dura: consultar `_mapa.md` ANTES de grep/glob
Antes de qualquer grep/glob procurando arquivo existente no cerebro, leia `_mapa.md` primeiro. Ele indexa tudo por tema/pasta e resolve a maioria das buscas em 1 leitura.

### 1.1 Decisoes tomadas
Qualquer "vamos fazer X", "nao vamos fazer Y", "decidimos que Z". Inclua o MOTIVO se mencionado.

### 1.2 Informacao nova
Fatos, contextos, dados que nao existiam antes no cerebro. Cruze com `_mapa.md` — ja existe arquivo sobre esse tema?

### 1.3 Acoes identificadas (so registro)
Acoes concretas que apareceram. Liste pra voce nao perder o fio — mas NAO crie tarefa nem cobre ninguem automaticamente. Pra cada uma: o que (verbo no infinitivo), quem, prazo (se mencionado). Vai pra "Ficou em aberto" (Fase 4).

### 1.4 Eventos / compromissos (so registro)
Reunioes, prazos, datas. Liste — NAO marque nada. Vai pra "Ficou em aberto" (Fase 4).

### 1.5 Atualizacoes em arquivos existentes
Algo discutido muda ou complementa um arquivo que ja existe? Cruze com `_mapa.md`.

### 1.6 Conteudo de sessao
A conversa em si tem valor como registro? (brainstorm, reuniao, download mental, analise longa.)

### 1.7 Feedback ou preferencias suas
Voce corrigiu algo, pediu pra mudar abordagem, ou expressou uma preferencia sobre como o Claude deve trabalhar com voce? Registre pra aplicar nas proximas conversas (ver Fase 3.4).

### 1.8 Item do trilho trabalhado?
Esta sessao trabalhou um item do `## HOJE` do `TAREFAS.md`?
- Read o `## HOJE`. Item `[~]` (iniciado pelo `/iniciar`) ou `[ ]` que casa com o tema → item a **fechar**.
- Trabalho substantivo que NAO estava no HOJE (apareceu no dia) → tambem loga, marcado como eventualidade.
- Conversa puramente operacional (1-2 acoes simples) → nao loga, pula a 3.3b.

---

## Fase 2: Decisoes de encerramento (interno — NAO pergunte, NAO mostre plano)

NAO existe checkpoint. Resolva as decisoes abaixo SOZINHO, com default seguro, e va DIRETO pra Fase 3. O que ficou decidido aparece no resumo da Fase 4 — depois de feito, nao como pedido de aprovacao.

- **Sessao:** salva se foi brainstorm / reuniao / download mental / analise longa. NAO salva se foi operacional curto.
- **Criar vs atualizar:** NAO crie arquivo novo se ja existe um sobre o tema — atualize (cruze com `_mapa.md`).
- **Em duvida se vale salvar:** teste **"isso eu descubro lendo o cerebro/codigo depois?"**. Sim → descarta. Nao, e e duravel → salva. NAO jogue a duvida pro usuario.
- **Split em 2+ notas:** se cobriu 2+ temas separados E a nota unica passaria de ~150 linhas, salve N notas menores. Default e 1 nota.
- **Brainstorm estrategico vs execucao:** se DESENHOU arquitetura nova, as acoes sao HIPOTESES FUTURAS — registre enxuto (1-2) em "Ficou em aberto", nao despeje 5+ itens que viram ruido.
- **Ja executado durante a conversa:** se algo ja foi salvo no meio da conversa, NAO duplique. Sinalize: "Ja executado durante a conversa — nada pendente."

Va direto pra Fase 3.

---

## Fase 3: Execucao

Execute na ordem. **Regra de ouro da ordem:** TODO write (conteudo, sessao, log, preferencia) acontece ANTES do commit (3.5), pra entrar no mesmo commit. Nao pergunte aprovacao — as decisoes ja foram tomadas na Fase 2.

### 3.1 Atualizar arquivos existentes
Edite conforme a Fase 2. Mantenha o formato e o template padrao do cerebro.

### 3.2 Criar arquivos novos
Use o template padrao do `CLAUDE.md` do cerebro. **Atualize `_mapa.md`** com a nova entrada (o `_mapa.md` usa forward slash `/` sempre nos paths).

### 3.3 Salvar sessao
Se a Fase 2 decidiu salvar, crie o arquivo em `sessoes/` com o template padrao de sessao (nome `YYYY-MM-DD-HHMM-tipo-descricao.md`; contexto, conteudo, decisoes, relacionados).

### 3.3b Fechar item do trilho + log-do-feito (se a Fase 1.8 detectou)

**Fechar no `TAREFAS.md` (`## HOJE`):** item trabalhado `[~]`/`[ ]` → `[x]`. Capture a hora local de fim `HH:MM` (`powershell -NoProfile -Command "Get-Date -Format HH:mm"`). Se a linha tinha `(iniciada: HH:MM)`: calcule a duracao e substitua o sufixo por `(HH:MM → HH:MM · Nmin)`.

**Anexar a linha no log** — append direto no markdown de `log-do-feito.md` (raiz do cerebro; crie se nao existir, com uma secao por mes `## YYYY-MM` e uma tabela `| Data | Tarefa | Duracao | Modo |`). Faca dedup por (data, tarefa) — se ja esta la, nao duplica.

**Item nao-feito** (parou no meio): deixa `[~]` no HOJE, nao loga incompleto.

### 3.4 Registrar preferencia sua (se a Fase 1.7 detectou)
Se voce expressou uma regra de como o Claude deve trabalhar com voce (tom, quando perguntar, o que evitar), registre-a pra valer nas proximas conversas: adicione uma linha curta na secao de preferencias do `CLAUDE.md` do cerebro (crie a secao "## Preferencias" se nao houver). Uma frase por preferencia.

### 3.5 Commit do cerebro (1 repo, git na mao)
Agora que TODOS os writes acima ja aconteceram:
1. `git status --short` pra ver o que esta sujo.
2. **Stage seletivo** dos arquivos que ESTA conversa tocou — nunca `git add -A` (pode arrastar arquivo de outra coisa).
3. `git commit -m "cerebro: <resumo curto do que mudou>"`.
4. Se o repo tem remote (`git remote`): `git push`. Se o push falhar (conflito/sem upstream), **nao resolva sozinho** — commite local e registre a pendencia na Fase 4.
5. Se nada foi tocado, sem commit — segue.

---

## Fase 4: Confirmacao final (o fim — sem pergunta)

Apresente o resumo do que FOI feito. Termina aqui — NAO faca pergunta, NAO peca confirmacao.

```
## Encerrado

**Salvei:**
- Cerebro — atualizado: [lista] | criado: [lista]
- Sessao: [salva como ... / nao necessario]
- Trilho: [item fechado + logado / nada]
- Preferencia registrada: [regra / nada]
- Git: [commitado+pushado / commitado local (push pendente: <motivo>) / nada]

**Ficou em aberto** (eu nao faco — voce resolve quando precisar):
- Acoes: [acao → quem | prazo]  (ou "nenhuma")
- Compromissos: [evento → data, participantes]  (ou "nenhum")

Tudo guardado. Pode fechar o chat.
```

Se uma secao nao tem nada, escreva "nenhum"/"nada" — nao omita (transparencia).

### 4.1 Bloco de retomada (condicional — SO se houver continuacao real)

Se esta sessao deixou trabalho claramente em aberto — uma proxima fase nomeada, um documento a continuar, trabalho declarado incompleto — emita ao final um bloco colavel pra abrir o proximo chat ja com contexto:

```
## Retomando — <tema>
**Objetivo:** [1 frase]
**Estado:** [onde parou]
**Paths canonicos:** [arquivos a abrir]
**Proxima acao:** [o primeiro passo concreto]
```

Condicional, NUNCA "sempre". Conversa fechada/resolvida nao gera bloco.

---

## Regras

- **Execute direto apos a Fase 2** — sem mostrar plano, sem pedir aprovacao.
- Conversa puramente operacional → processamento minimo, e ta certo. Nao invente acoes.
- Em duvida se algo vale salvar → teste "isso eu descubro lendo o cerebro/codigo depois?". NAO jogue a duvida pro usuario.
- NAO duplique. Se ja foi salvo no meio da conversa, nao salve de novo.
- Nunca `git add -A` — sempre stage seletivo. Nunca resolve conflito de push sozinho.
- Comunique-se no idioma do usuario, direto e sem formalidade.
