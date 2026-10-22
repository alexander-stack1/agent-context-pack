# guardrails.md — travas por hook

> Template público. Ajuste tetos, caminhos e scripts no overlay privado.

Princípio: tarefa clara vai até o fim; o hook segura as linhas vermelhas sem pedir ok. Erro interno do guard depois do parse **bloqueia** (fail-closed).

## Bloqueio duro, sem liberação
1. **Credenciais:** leitura de `credentials/`, `.env*` (exceto `.env.example`, `.env.sample`, `.env.template`), `~/.ssh`, arquivos de auth das CLIs de agente e storageState de testes.
2. **Segredo:** `printenv`, `env`, leitura direta do cofre com saída no terminal, `echo` de variável secreta. Segredo só entra por injeção (`[VAULT_CLI] run ...`).
3. **Push:** force push (`--force`, `-f`, `--force-with-lease`, refspec com `+`), push na `main`/`master`, apagar a `main` ou mexer na proteção dela. Push de outras branches é livre.
4. **Commit:** nunca `--no-verify`. Hooks são parte da prova.
5. **Merge:** só por `scripts/merge-safe.sh` (CI verde, revisor aprovando preso ao sha do head, squash com `--match-head-commit`, nunca `--admin`).
6. **Deploy:** só por `scripts/deploy-safe.sh` (versão anterior conhecida, rollback definido, smoke test e rollback automático se falhar).
7. **Dinheiro:** API de pagamento em produção só por wrapper com teto por operação e por dia (`config/limits.toml`); sem estorno, webhook, chave, conta ou transferência; log de tudo.
8. **Dados de produção:** `DROP`, `TRUNCATE` ou `DELETE` sem `WHERE` fora de banco local/teste; exclusão de banco, bucket ou repositório; migration remota fora de `scripts/migrate-prod.sh` (recusa destrutiva, snapshot antes).
9. **Dado de cliente:** upload (`scp`, `rsync` remoto, `curl` com upload, CLIs de nuvem, gist, MCP de upload) de caminho listado em `config/client-data.txt`.
10. **Subagente somente leitura:** sem Edit, Write, patch ou shell que grave.

## Bloqueio com liberação temporária (só no terminal do humano)
11. Envio externo (e-mail, chat, pagamentos). E-mail e mensagem seguem por rascunho.
12. Destrutivo local: `rm -rf` fora do repo atual ou de `/tmp`; `reset --hard`, `clean -f`, `branch -D` na `main` ou com cwd desconhecido.

## Apenas aviso
13. Blacklist S/M/C sem `Esforço: C` declarado (rito, não licença); gravação em pasta sincronizada (iCloud/Drive) ou lixeira.
14. PostToolUse: aviso quando a saída parece conter segredo.
15. Lembrete de verificação de fonte em pedidos de domínio.

## Operação local
- Servidores de desenvolvimento só em `127.0.0.1`, nunca `0.0.0.0`. Painéis administrativos fechados para a internet.
- Antes de editar arquivo canônico ou config: backup ao lado com carimbo `arquivo.bak-AAAAMMDD-HHMMSS-[REASON]`.
- Código fora de pastas sincronizadas, em `~/dev` por convenção (exceções nomeadas em `PATHS.md`).

## Registro e prova
- Cada decisão (allow, aviso, deny, allow-aprovado) vai para `logs/harness.jsonl` só com metadados.
- `evals/` simula payloads das CLIs de agente contra o guard; `sync-harness --check` roda os evals.
- Implementação de referência: um único `guard-pretooluse` lido por todas as CLIs que aceitam hook.

## Tamanho de arquivo
- Arquivo autorado por agente: até ~5.000 tokens (≈ 20.000 bytes). Hook pre-commit mede só os staged.
- Fora da contagem: lockfiles, código gerado, binários/assets, `@generated`/`DO NOT EDIT`, e `.agent-size-ignore` (com justificativa).
- Dividir por responsabilidade, nunca por número de linhas; preservar a API pública com reexport; rodar build, lint e testes.
