---
description: Onboarding de um segundo cerebro novo. Faz perguntas, instancia a estrutura do molde (que vem dentro do plugin), personaliza tudo pro usuario e nao deixa lixo de setup. Rode uma vez, numa pasta nova.
argument-hint: (rode dentro da pasta vazia onde o cerebro vai morar)
model: sonnet
---

Voce vai configurar um **segundo cerebro** novo pra esta pessoa, do zero. Este comando roda **uma vez**, na pasta onde o cerebro vai viver. Ao final, a pasta e um cerebro personalizado e pronto — sem nenhum arquivo de setup sobrando. Execute este fluxo EXATAMENTE.

> **O molde** vive dentro do proprio plugin, em `${CLAUDE_PLUGIN_ROOT}/templates/cerebro-scaffold/`. Voce copia de la e personaliza aqui. A pessoa nao precisa baixar nada.

## Fase 0 — Checar o terreno

1. Confirme o diretorio atual (`pwd`) — e aqui que o cerebro vai morar. Pergunte à pessoa se e esse mesmo o lugar, se houver duvida.
2. Se **ja existe** um `CLAUDE.md` que parece um cerebro configurado (sem placeholders `{NOME}`/`[SEU_NOME]`), PARE e avise: "Ja existe um cerebro configurado aqui. Quer reconfigurar (sobrescreve) ou cancelar?". Nao sobrescreva sem confirmacao.
3. Caso contrario, siga.

## Fase 1 — Perguntas de configuracao

Faça as perguntas abaixo de forma conversacional e eficiente (pode agrupar). Espere as respostas antes de montar qualquer coisa.

**Sobre a pessoa:**
1. Qual seu nome?
2. O que voce faz? (profissao, ocupacao principal)
3. Quais ferramentas voce usa no dia a dia? (apps, programas)
4. Como voce prefere se comunicar? (direta, detalhada, casual)
5. Voce usa gestao de tarefas? Qual? (ClickUp, Todoist, nenhum…) E agenda? (Google Calendar, Outlook…)

**Modos de trabalho (calibra o TAREFAS.md):**
6. **Voce constroi ou melhora as suas proprias ferramentas — escreve automacoes, scripts, configura o proprio sistema?**
   - **Sim** (dev/tecnico) → a legenda de modos inclui `Afiar` (melhorar a propria ferramenta): `Pensar` · `Produzir` · `Afiar`.
   - **Nao** → deixe `Afiar` de fora. Se a pessoa gere outras pessoas, use `Pensar` · `Produzir` · `Cobrar`; senao, so `Pensar` · `Produzir`. Se ela tiver um verbo proprio pro trabalho dela (ex. consultor: `Consultar`/`Gravar`), ofereça incluir.

**Areas e projetos:**
7. Quais areas da sua vida voce quer organizar? (ex: trabalho, saude, financas, casa, estudos, relacionamento, hobbies)
8. Voce tem projetos ativos agora? Quais? (qualquer coisa com prazo/objetivo)
9. Tem algum tema de conhecimento que voce ja quer comecar a registrar?
10. Voce vai usar o cerebro mais pelo celular (WhatsApp) ou pelo computador?

## Fase 2 — Instanciar o molde

1. Se a pasta ainda **nao** tem a estrutura do cerebro, copie o molde de dentro do plugin pro diretorio atual:
   ```
   cp -r "${CLAUDE_PLUGIN_ROOT}/templates/cerebro-scaffold/." .
   ```
   (No Windows sem `cp`, use o Bash tool — ele tem `cp`. Isso traz: `CLAUDE.md`, `_mapa.md`, `TAREFAS.md`, `inbox/` com `DIARIO.md`+`REVISAO.md`+`contextos/`, `diarios/`, as 5 pastas `projetos/areas/conhecimento/sessoes/arquivo/`, e `.suporte/prompts/extrair-contexto.md`.)
2. Se a estrutura ja veio junto (a pessoa copiou o scaffold à mao), pule a copia e va direto personalizar.

## Fase 3 — Personalizar

Com base nas respostas, edite os arquivos recem-criados (troque TODOS os placeholders `{...}`):

1. **`CLAUDE.md`** — nome, ocupacao, ferramentas, gestao de tarefas/agenda, estilo de comunicacao, idioma.
2. **`TAREFAS.md`** — nome, data de hoje, e **a legenda de modos** conforme a resposta 6 (esse e o ponto-chave da calibragem: nao empurre `Afiar` pra quem nao constroi ferramenta).
3. **`_mapa.md`** — nome no titulo.
4. **Arquivos iniciais** — crie stubs curtos (so o header do template padrao) pras areas (resposta 7) em `areas/`, pros projetos (resposta 8) em `projetos/`, e pro tema de conhecimento (resposta 9) em `conhecimento/`. Registre cada um no `_mapa.md`. Nao invente conteudo — so o esqueleto pra pessoa preencher.

## Fase 4 — Limpeza (nao deixe lixo de setup)

1. Se veio junto algum `SETUP.md` ou `README.md` de bootstrap (de uma copia manual antiga do template), **apague-os** — o onboarding e este comando, nao um arquivo solto.
2. Confirme por `ls` na raiz que sobrou APENAS: `CLAUDE.md`, `TAREFAS.md`, `_mapa.md`, as 5 pastas, `inbox/`, `diarios/`, `.suporte/`. Qualquer resto de setup = apagar.

## Fase 5 — Fechamento

1. Se a pasta ainda nao e um repo git, sugira: `git init` + primeiro commit (`cerebro: setup inicial`). Ofereça rodar.
2. Mostre um resumo curto:
   ```
   ## Cerebro configurado — {NOME}
   Estrutura criada · CLAUDE.md e TAREFAS.md personalizados · modos: [lista]
   Areas: [lista] · Projetos: [lista]

   Como usar no dia a dia:
   - Joga tudo em inbox/DIARIO.md ao longo do dia
   - /metodo-pique:inbox pra processar (termina vazio)
   - /metodo-pique:iniciar pra abrir um item do trilho · /metodo-pique:encerrar pra fechar
   ```
3. Termina aqui. O cerebro esta pronto.

## Regras

- Nunca sobrescreva um cerebro ja configurado sem confirmacao explicita.
- Nao invente conteudo nas areas/projetos — so o esqueleto.
- Nao deixe NENHUM arquivo de setup na raiz ao final (esse e o motivo de o setup ser um comando, e nao um `.md` solto).
- Comunique-se no idioma que a pessoa pediu.
