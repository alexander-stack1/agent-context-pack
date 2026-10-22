# modelos.md — matriz de modelos e esforço (fonte única)

> Template. Preencha com os IDs exatos da documentação oficial de cada fornecedor e a data da conferência. Nunca preencher ID de memória.

Papéis: **ORQ** (orquestrador e planejamento), **PES** (raciocínio pesado), **EXE** (executor), **SIM** (busca, triagem, extração).
Formato: modelo | ID exato | esforço padrão | esforço máximo. Máximo só com ordem do humano ou classe C na blacklist.

| Ferramenta | ORQ | PES | EXE (especificada / difícil) | SIM |
|---|---|---|---|---|
| `[AGENT_CLI_A]` | `[MODEL_ORQ]` medium | `[MODEL_PES]` high | `[MODEL_EXE]` medium / high | `[MODEL_SIM]` low |
| `[AGENT_CLI_B]` | ... | ... | ... | ... |
| `[IDE_AGENT]` | ... | ... | ... | ... |

## S/M/C para modelo e esforço

| Classe | Decide e planeja | Executa | Revisa | Subagente |
|---|---|---|---|---|
| S (two-way door, fora da blacklist) | A própria sessão | Inline; se delegar algo mecânico, SIM low | Nenhum | Só busca/triagem |
| M (bug ou feature assertável, TDD) | ORQ medium | EXE medium (high se o teste falhar 2x) | Teste e lint; revisão ORQ | 1 EXE por módulo |
| C (blacklist, produção, dinheiro, dúvida) | ORQ high, plano e aprovação humana | EXE high | PES high com contexto limpo (adversarial) | EXE high, SIM low |

Regras: em dúvida, C. Prefixo `[S]` não vence a blacklist. Revisor nunca é o modelo que escreveu. Redação final de domínio fica com ORQ ou PES, nunca com SIM.
Modelos que exigem retenção de dados no fornecedor não recebem dado de cliente.

## Fontes
Liste aqui a URL oficial de cada ID e de cada parâmetro de esforço.
