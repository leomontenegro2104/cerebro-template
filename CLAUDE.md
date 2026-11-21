# Cérebro — regras do vault

Este é o second brain de [NOME]. Vault Obsidian em markdown, versionado em Git (repo privado).
Vale para qualquer IA: `AGENTS.md` é symlink deste arquivo.

## Primeira sessão (setup)
Se este arquivo ainda tiver `[NOME]`, faça o setup antes de qualquer outra coisa:
1. Pergunte o nome e troque `[NOME]` em todo o vault.
2. Pergunte quais áreas da vida ela quer organizar (ex.: trabalho, estudos, saúde, finanças, casa).
   Crie uma pasta `kebab-case` por área, cada uma com um `MAP.md`, e liste-as na tabela de Camadas e no `MAP.md` raiz.
3. Rode a entrevista de `me/entrevista-identidade.md`.
4. Apague esta seção "Primeira sessão" e registre no `log.md`.

## Ao iniciar qualquer sessão
1. Leia `MAP.md` (índice global) e `hot.md` (o que está quente agora).
2. Leia `me/user.md` e `me/soul.md` para tom e contexto. Respeite `me/anti-slop.md` em todo texto escrito.
3. Vá para o `MAP.md` da área relevante antes de abrir arquivos soltos.

## Camadas (regra mais importante)
| Pasta | Dono | Regra |
|---|---|---|
| `inbox/` | [NOME] | Entrada de material bruto (Web Clipper → `inbox/clips/`, cargas de outras fontes → `inbox/import/`). Leia, não edite. |
| `raw/` | ninguém | Arquivo morto imutável. Após processar, mova de `inbox/` para `raw/AAAA-MM/`. Nunca edite nem apague. |
| `me/` | [NOME] | Identidade. Só edite quando ela pedir. |
| Áreas (`pessoas/` + as listadas no `MAP.md`) | IA | Conhecimento organizado. Crie, atualize, faça cross-links. |
| `hot.md`, `decisoes.md`, `daily/` | IA | Mantidos pelas skills `/salvar` e `/ingest`. |

## Convenções
- Nomes de arquivo: `kebab-case.md`, sem acento. Datas: `AAAA-MM-DD`.
- Links internos: `[[nome-do-arquivo]]` (wiki links do Obsidian).
- Toda página de conhecimento cita a fonte: `Fonte: [[raw/AAAA-MM/arquivo]]` ou URL.
- Toda alteração feita por IA vira uma linha em `log.md`: `AAAA-MM-DD | skill/ação | arquivos | resumo`.
- Ao criar página nova, adicione-a ao `MAP.md` da área com uma linha de resumo.
- Fato incerto ou conflitante: marque com `> [!question]` em vez de inventar.
- Resposta boa (análise, comparação, plano) gerada em conversa: pergunte "Salvo como página em X?".

## Git
- O vault é sincronizado com GitHub (Obsidian Git faz commit/push a cada 15 min e pull ao abrir).
- Sessão na nuvem (celular / claude.ai/code): ao terminar, faça `git pull --rebase` e commit + push **direto na `main`**, sem abrir PR nem deixar branch solta. Mensagem curta em português.

## Segurança
- Nunca escreva senhas, tokens, número de conta/cartão, CPF ou documentos.
- Se houver extratos bancários, ficam em `financas/extratos/` (está no `.gitignore`, só local). No Git vão só resumos.
- Investimentos: organizar decisões dela. Não dar recomendação de compra/venda.

## Skills (`.claude/skills/`)
- `/ingest` — processa `inbox/` (clips e cargas em lote) para as áreas.
- `/salvar` — fim de sessão: atualiza hot, decisões, pessoas, daily, log.
- `/revisao-semanal` — health check do vault e revisão das metas.
