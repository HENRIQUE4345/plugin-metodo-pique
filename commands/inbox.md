---
description: Processa o inbox do cerebro (DIARIO + REVISAO + contextos), classifica cada entrada, gera um PLANO.md pra voce revisar e, apos confirmacao, executa e deixa o inbox vazio. Execute este fluxo EXATAMENTE.
model: sonnet
---

Processa o inbox completo do seu cerebro. Siga este fluxo EXATAMENTE:

## Fase 1: Leitura

1. Leia `_mapa.md` para ter contexto do cerebro.
2. Leia `inbox/DIARIO.md` (se existir e tiver conteudo).
3. Leia `inbox/REVISAO.md` (se existir e tiver conteudo).
4. Liste e leia todos os arquivos em `inbox/contextos/` (se houver).

Se NENHUM dos tres tiver conteudo, avise que o inbox esta vazio e encerre.

## Fase 2: Gerar PLANO.md

Para cada entrada encontrada, classifique em:
- **Acoes/Tarefas**: coisas para fazer (ex: "preciso fazer X", "lembrar de Y")
- **Ideias**: insights, ideias de produto, conteudo, negocios
- **Informacao**: fatos, dados, contexto que vale registrar no cerebro
- **Revisao**: correcoes ou ajustes em arquivos existentes do cerebro
- **Descartavel**: desabafo sem conteudo acionavel, nota obsoleta, registro ja processado

Gere o arquivo `inbox/PLANO.md` com este formato:

# Plano de Processamento — YYYY-MM-DD

## Resumo do dia
Breve resumo de 2-3 frases sobre o que foi registrado.

## Tarefas
- [ ] Descricao da tarefa | Prioridade: urgente/alta/normal/baixa

## Salvar no cerebro
| # | Conteudo (resumo) | Destino | Acao |
|---|-------------------|---------|------|
| 1 | Descricao | `areas/saude.md` (secao X) | Adicionar |
| 2 | Descricao | `conhecimento/novo-tema.md` | Criar novo |

## Revisoes no cerebro
| # | O que mudar | Arquivo alvo | Tipo |
|---|------------|--------------|------|
| 1 | Descricao da correcao | `arquivo.md` | Atualizar |

## Descartar
| # | Item | Motivo |
|---|------|--------|
| 1 | Descricao | Motivo pelo qual nao precisa salvar |

## Origem dos itens
Lista de quais entradas do DIARIO/REVISAO/contextos geraram cada item acima.

## Fase 3: Pausa para revisao

Apos gerar o PLANO.md:
1. Avise que o plano foi gerado em `inbox/PLANO.md`.
2. Peca para abrir o arquivo, revisar, editar o que quiser.
3. Diga: "Quando terminar de revisar, me avise que eu executo."
4. NAO execute nada ate receber confirmacao.

## Fase 4: Execucao (apos confirmacao)

1. Releia `inbox/PLANO.md` (pode ter sido editado).
2. Execute EXATAMENTE o que esta no plano revisado:
   - Salve conteudo nos arquivos indicados do cerebro
   - Aplique revisoes/correcoes nos arquivos indicados
   - Atualize `_mapa.md` se novos arquivos foram criados
3. Se o DIARIO.md foi processado:
   - Mova para `diarios/YYYY-MM-DD.md`
   - Crie novo `inbox/DIARIO.md` vazio (com o header padrao)
4. Limpe `inbox/REVISAO.md` (se tinha conteudo).
5. Remova arquivos processados de `inbox/contextos/`.
6. Apague `inbox/PLANO.md`.
7. Mostre um resumo final do que foi feito.

> **Regra de ouro:** o inbox SEMPRE termina vazio. Se acumular arquivo sem destino, o canal perde a funcao. Ao final, `inbox/` deve conter apenas `DIARIO.md` (vazio), `REVISAO.md` (vazio) e `contextos/` (vazio).
