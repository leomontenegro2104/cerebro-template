---
name: ingest
description: Processa o material bruto em inbox/ (clips do Obsidian Web Clipper, transcrições, PDFs e cargas em lote de outras fontes como export do Notion/ChatGPT/Google Docs) e integra nas áreas do vault. Use quando o usuário disser "ingest", "processa o inbox", "adicionei material" ou "carga de contexto".
---

1. Liste `inbox/clips/` e `inbox/import/` (ignore `.gitkeep`). Se vazio, diga e pare.
2. **Carga em lote** (`inbox/import/<fonte>/`, muitos arquivos): primeiro faça um inventário (quantidade, tipos, temas) e proponha um plano de destino por grupo. Só execute após aprovação. Processe em lotes de ~20 arquivos.
3. Para cada arquivo:
   - Classifique a área (as listadas no `MAP.md` raiz, ou `pessoas`), ou "descartar".
   - Extraia o que importa: conceitos, fatos, ações, pessoas, decisões. Transcrição longa → resumo + pontos-chave + citações curtas, nunca cópia integral.
   - Atualize página existente se o tema já existe (veja o `MAP.md` da área); senão crie nova. Adicione `Fonte: [[raw/AAAA-MM/arquivo]]` ou a URL.
   - Crie `[[links]]` para páginas relacionadas.
   - Ação/prazo encontrado → `hot.md`. Pessoa relevante → `pessoas/nome.md`.
4. Mova o arquivo processado para `raw/AAAA-MM/` (mês atual). Nunca edite o conteúdo.
5. Atualize os `MAP.md` das áreas tocadas e acrescente uma linha por lote em `log.md`.
6. Termine com: quantos arquivos, o que foi criado/atualizado, o que foi descartado e por quê.

Nunca grave senhas, tokens, número de conta ou documentos que aparecerem no material.
