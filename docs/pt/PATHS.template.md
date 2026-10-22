# PATHS.md — caminhos canônicos (template)

> Camada 2, carregada sob gatilho. Fonte única do caminho local de cada repositório, vault e pasta de ativos.

**Regra:** nenhum outro arquivo repete caminho local; os demais referenciam este. Exceção: o `CLAUDE.md` de um repo pode declarar o próprio caminho.
**Quando carregar:** demanda que envolva caminho de repo, clone, worktree, deploy ou script com caminho embutido. Antes de afirmar caminho, nunca depois.
**Nunca afirmar caminho de memória.** Ausente aqui = NÃO VERIFICADO: dizer e perguntar.

## Repositórios de código
| Produto | Caminho local | Remoto | Branch | Papel |
|---|---|---|:-:|---|
| `[PRODUCT_A]` | `~/dev/[product-a]` | `[YOUR_GITHUB]/[product-a]` (privado) | `main` | ... |
| `[PRODUCT_B]` | `~/dev/[product-b]` | `VERIFICAR` | `VERIFICAR` | ... |

## Contexto, vaults e ativos
| O que | Caminho | Observação |
|---|---|---|
| Contexto canônico | `[CONTEXT_DIR]` | Mapa em [`MANIFEST.md`](MANIFEST.md) |
| Vault operacional | `[OPS_VAULT]` | O humano lê, o LLM escreve |
| Vault de domínio | `[DOMAIN_VAULT]` | Roteamento obrigatório em pedido de domínio |
| Credenciais | `[CONTEXT_DIR]/credentials/` | Nunca abrir, citar ou espelhar |
| Despachos | `~/dev/dispatches` | Um arquivo por despacho |

## Exceções nomeadas à regra de `~/dev`
| Caminho | Motivo | Decidido em |
|---|---|---|
| `~/[product-x]` | Fora de pasta sincronizada; fonte de deploy | `[DATE]` |

## Caminhos aposentados, não usar
| Caminho | Estado |
|---|---|
| `[OLD_PATH]` | Aposentado em `[DATE]`. Substituído por `[NEW_PATH]` |

*Ao mover ou renomear pasta, atualizar só este arquivo e registrar no changelog.*
