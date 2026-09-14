# Classificação de esforço (S / M / C)

> **Public template.** Personal identifiers, firm, products, emails and paths were replaced with placeholders. See `PLACEHOLDERS.md`. Do not reintroduce real data.


> Template canônico sugerido para colar em `working-style.md` (fonte única).
> Espelhos curtos: `agent_rules.md` e `instrucoes-implementador-senior.md`.
> Status: RASCUNHO — não aplicado à Camada 1 até aprovação explícita.

## Propósito

Proporcionar **cerimônia de engenharia** ao **risco e à reversibilidade** da mudança.
Fail-closed, evidência e raio de impacto **nunca** entram no atalho S.

## Antes de planejar

1. Classificar a tarefa como **S**, **M** ou **C**.
2. Declarar na **primeira linha** da resposta:
   `Esforço: S|M|C — motivo: … — paths: …`
3. Se o usuário prefixar `[S]`, `[M]` ou `[C]`, esse prefixo vence, **exceto** blacklist (abaixo): avisar e pedir confirmação explícita para seguir em S.

## Definições

### S — Simples (todas devem ser verdade)

- Mudança local e óbvia (typo, rename interno, copy, config sem comportamento novo).
- Poucos arquivos (orientação: ≤ 3), mesmo módulo ou docs.
- *Two-way door*: fácil reverter.
- Fora da blacklist de paths/temas.
- Sem contrato público de API novo ou alterado.
- Sem authZ, RLS, OAuth, upload, rate limit, migration, deploy, segredo, billing/pagamento, produção.
- Pedido inequívoco (ou `[S]`).

### M — Média

- Bug ou feature com comportamento assertável.
- Escopo limitado a pacote/módulo.
- Não toca produção nem blacklist sem mitigação explícita.
- Falha parcial do checklist S, mas sem irreversibilidade.

### C — Complexa (qualquer um basta)

- Toca blacklist (ver abaixo).
- Escopo incerto, multi-serviço, ou contrato público.
- Migration, deploy, produção, money, staged-write em sistema real.
- Auditoria de segurança / pedido de “APROVADO”.
- Dúvida na classificação → **C**.

## Blacklist (força C)

Se o diff ou a investigação tocar (path, símbolo ou tema):

`auth`, `authorization`, `permission`, `rls`, `oauth`, `pkce`, `middleware` de auth,
`migration`, `deploy`, `production`, `.env`, `secret`, `token`, `service_role`,
`billing`, `payment`, `stripe`, `upload`, `rate.?limit`, `firewall`

→ classificar **C**. Se o usuário pediu `[S]`, **não** executar em S: explicar e pedir confirmação para tratar como C (ou M com mitigação escrita).

## Cerimônia por classe

| Rito | S | M | C |
|------|---|---|---|
| Reler Camada 1 completa | Não, se sessão já carregou e a tarefa não muda regras | Sim se tocar código de produto | Sim |
| Memória do repo (`CLAUDE.md` / `REPO_MAP`) | Só se já na sessão; abrir o arquivo pedido | `CLAUDE.md` + seção do mapa | Contrato + mapa + retrieval com cite-and-verify |
| Plano + aprovação | 1 linha “Vou X” e segue se pedido inequívoco | Plano curto; aguarda se risco ≠ zero | Plano completo + aprovação explícita |
| TDD 8 passos | N/A sem comportamento; senão teste focal | TDD + testes do pacote/módulo | TDD completo |
| Suíte integral | Não (path/pacote + lint/typecheck) | Pacote/módulo | Obrigatória + evidência fresca |
| Mutação (“teste morde”) | Não | Se houver teste novo | Sim, se houver teste novo |
| Multiagente | Proibido | Só amplitude | Review adversarial ok |
| Revisão independente / canário / smoke | Não, salvo pedido | Não, salvo adjacente a prod | Conforme deploy/segurança |
| Staged-write + 2ª aprovação (money/prod) | N/A | N/A se só rascunho | Mantém |
| Fail-closed / não inventar / sem prod sem ordem | **Sempre** | **Sempre** | **Sempre** |

## Linha de auditoria (obrigatória na entrega)

```
Esforço: M — motivo: bug no serializer de X; comportamento assertável
Paths: app/foo/serializers.py, tests/test_foo.py
Verificação: pytest tests/test_foo.py (GREEN) + ruff path
Repo: nome @ sha-curto — mapa: docs/agent/REPO_MAP.md (data)
```

## Exemplos

**S**
- Typo em README.
- Rename de variável local sem API pública.
- Copiar material da pós para pasta do Drive.

**M**
- Corrigir bug em serializer com teste.
- Endpoint read-only usando auth já existente.

**C**
- Qualquer mudança em RLS / OAuth / migration / deploy.
- Nova claim de autorização.
- Promoção a produção.

## Em dúvida

Tratar como **C**. YAGNI manda no *escopo* da mudança, não na *prova*.
