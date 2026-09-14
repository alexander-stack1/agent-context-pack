# Boot de memória por projeto + política de retrieval

> **Public template.** Personal identifiers, firm, products, emails and paths were replaced with placeholders. See `PLACEHOLDERS.md`. Do not reintroduce real data.


> Complemento operacional aos templates 04–06. Pode viver em `docs/agent/README.md` do repo
> ou como skill interna “boot-repo”.

## Ritual de abertura de sessão (por esforço)

### S
1. Se `CLAUDE.md` já foi lido nesta sessão → não reler.
2. Abrir só o(s) arquivo(s) do pedido.
3. Verificar com comando mínimo do `CLAUDE.md`.

### M
1. Ler `CLAUDE.md`.
2. Ler a seção relevante de `docs/agent/REPO_MAP.md` (checar `git_sha`).
3. Confirmar paths com `rg` / `Read`.
4. TDD + testes do pacote.

### C
1. `CLAUDE.md` + `REPO_MAP` + `DECISIONS` tocados pelo tema.
2. Camada 1 de appsec (`working-style` / agent_rules) se auth/dados/deploy.
3. Retrieval (Codebase Memory) só como hipótese → cite-and-verify.
4. Fixar repo, branch, commit/tree no plano.
5. Rito C completo.

## Cite-and-verify

```
Hipótese (retrieval): FooService em app/foo/services.py
Prova: Read app/foo/services.py L… — CONFIRMADO | NÃO VERIFICADO
```

Sem prova → não editar com base na hipótese.

## Atualização de memória

| Evento | Ação |
|--------|------|
| PR merge que mexe estrutura de pastas/módulos | Regenerar `REPO_MAP` ou marcar `stale` |
| Nova decisão estável de arquitetura | ADR em `DECISIONS.md` |
| Landmine descoberto no trabalho | 1 bullet em Hotspots do mapa (mesmo PR ou follow-up) |
| Conversa casual | Não gravar no mapa; no máximo ponteiro em memória de agente |

## Proibido

- Colar codebase em `.auto-memory`
- Tratar resumo de chat como mapa
- Um RAG global para todos os produtos misturados
- Atualizar mapa sem atualizar `git_sha`
