# Clasificación de esfuerzo (S / M / C)

> **Public template.** Personal identifiers, firm, products, emails and paths were replaced with placeholders. See `PLACEHOLDERS.md`. Do not reintroduce real data.


> Template canônico sugerido para colar em `working-style.md` (fonte única).
> Espelhos curtos: `agent_rules.md` e `senior-implementer-instructions.md`.
> Status: RASCUNHO — no aplicado à Camada 1 ates aprobación explícita.

## Propósito

Proporcionar **cerimônia de engenharia** ao **risco e à reversibilidade** da mudança.
Fail-closed, evidencia e raio de impacto **nunca** entram no atalho S.

## Antes de planejar

1. Classificar a tarefa como **S**, **M** o **C**.
2. Declarar na **primera línea** da resposta:
   `Esfuerzo: S|M|C — motivo: … — paths: …`
3. Se o usuario prefixar `[S]`, `[M]` o `[C]`, esse prefixo vence, **exceto** blacklist (abaixo): avisar e pedir confirmação explícita para seguir em S.

## Definiciones

### S — Simples (todas devem ser verdade)

- Mudança local e óbvia (typo, rename interno, copy, config sin comportamiento novo).
- Poucos archivos (orientação: ≤ 3), mismo módulo o docs.
- *Two-way door*: fácil reverter.
- Fora da blacklist de paths/temas.
- Sem contrato público de API nuevo o alterado.
- Sem authZ, RLS, OAuth, upload, rate limit, migration, deploy, segredo, billing/pagamento, producción.
- Pedido inequívoco (o `[S]`).

### M — Média

- Bug o feature con comportamiento assertável.
- Escopo limitado a pacote/módulo.
- No toca producción nem blacklist sin mitigação explícita.
- Falha parcial do checklist S, pero sin irreversibilidade.

### C — Complexa (cualquier um basta)

- Toca blacklist (ver abaixo).
- Escopo incerto, multi-serviço, o contrato público.
- Migration, deploy, producción, money, staged-write em sistema real.
- Auditoria de seguridad / pedido de “APROBADO”.
- Dúvida na classificação → **C**.

## Blacklist (força C)

Se o diff o a investigação tocar (path, símbolo o tema):

`auth`, `authorization`, `permission`, `rls`, `oauth`, `pkce`, `middleware` de auth,
`migration`, `deploy`, `production`, `.env`, `secret`, `token`, `service_role`,
`billing`, `payment`, `stripe`, `upload`, `rate.?limit`, `firewall`

→ classificar **C**. Se o usuario pediu `[S]`, **não** executar em S: explicar e pedir confirmação para tratar como C (o M con mitigação escrita).

## Ceremonia por clase

| Rito | S | M | C |
|------|---|---|---|
| Releer Camada 1 completa | Não, se sesson ya carrego e a tarefa no muda reglas | Sim se tocar código de produto | Sim |
| Memória do repo (`CLAUDE.md` / `REPO_MAP`) | Só se ya na sessão; abrir o archivo pedido | `CLAUDE.md` + sección do mapa | Contrato + mapa + retrieval con cite-and-verify |
| Plano + aprobación | 1 línea “Vo X” e segue se pedido inequívoco | Plano curto; aguarda se risco ≠ zero | Plano completo + aprobación explícita |
| TDD 8 pasos | N/A sin comportamiento; seno teste focal | TDD + testes do pacote/módulo | TDD completo |
| Suíte integral | No (path/pacote + lint/typecheck) | Pacote/módulo | Obrigatória + evidencia fresca |
| Mutação (“teste morde”) | No | Se houver teste nuevo | Sim, se houver teste nuevo |
| Multiagente | Prohibido | Só amplitude | Review adversarial ok |
| Revison independente / canário / smoke | Não, salvo pedido | Não, salvo adjacente a prod | Conforme deploy/seguridad |
| Staged-write + 2ª aprobación (money/prod) | N/A | N/A se só rascunho | Mantém |
| Fail-closed / no inventar / sin prod sin orden | **Sempre** | **Sempre** | **Sempre** |

## Línea de auditoría (obligatoria na entrega)

```
Esfuerzo: M — motivo: bug no serializer de X; comportamiento assertável
Paths: app/foo/serializers.py, tests/test_foo.py
Verificação: pytest tests/test_foo.py (GREEN) + ruff path
Repo: nome @ sha-curto — mapa: docs/agent/REPO_MAP.md (data)
```

## Ejemplos

**S**
- Typo em README.
- Rename de variável local sin API pública.
- Copiar material da pós para carpeta do Drive.

**M**
- Corrigir bug em serializer con teste.
- Endpoint read-only usando auth ya existente.

**C**
- Qualquer mudança em RLS / OAuth / migration / deploy.
- Nova claim de autorização.
- Promoção a producción.

## En duda

Tratar como **C**. YAGNI manda no *escopo* da mudança, no na *prova*.
