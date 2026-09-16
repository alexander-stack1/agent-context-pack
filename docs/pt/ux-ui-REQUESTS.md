# ux-ui-PEDIDOS.md

> **Public template.** Personal identifiers, firm, products, emails and paths were replaced with placeholders. See `PLACEHOLDERS.md`. Do not reintroduce real data.

> Cardápio condensado: o que pedir na contratação de UI ou na refatoração.
> Atualização: 07/09/2026
> Gates canônicos em `ux-ui-INDEX.md` + `ux-ui-criteria.md` (+ web/mobile). Craft via **impeccable** / **frontend-design** por baixo — você não precisa lembrar os nomes em inglês.

---

## Peça assim (7 skills)

| Você quer… | Peça / skill | Encapsula |
|------------|--------------|-----------|
| Planejar tela **antes** de codar | **`[SKILL_UI_PLAN]`** | R0 + gates + impeccable `shape` (+ variantes se pedido) |
| Landing / marketing web+mobile | **`[SKILL_UI_LANDING]`** | gates web-landing + mobile + modo Persuade |
| Revisar UX, a11y, responsivo | **`[SKILL_UI_REVIEW]`** | gates checklist + impeccable `critique` + `audit` |
| Refatorar visual (hierarquia, tipo, cor, mobile↔web) | **`[SKILL_UI_REFACTOR]`** | gates + `distill` / `layout` / `typeset` / `adapt` / `colorize` / `clarify` conforme o caso |
| Polir e endurecer pra ship | **`[SKILL_UI_POLISH]`** | `polish` + `harden` + `[SKILL_UI_PROVE]` |
| Provar que a tela ficou certa | **`[SKILL_UI_PROVE]`** | `visual-verify` (screenshot vs referência) |
| Redesign incremental do [PRODUCT_A] | **`[SKILL_UI_REDESIGN]`** | briefing [PRODUCT_A] + gates (não troca marca) |

Skill de base (raramente pedir sozinha): `ux-ui-criteria` — só os gates fail-closed.

---

## Frases prontas

- «Roda **[SKILL_UI_PLAN]** pra [tela/fluxo].»
- «**[SKILL_UI_LANDING]** do [produto], web e mobile.»
- «**[SKILL_UI_REVIEW]** nesta página / neste PR.»
- «**[SKILL_UI_REFACTOR]**: está poluído / ilegível / quebra no mobile.»
- «**[SKILL_UI_POLISH]** antes do merge.»
- «**[SKILL_UI_PROVE]** contra o mock / sibling.»
- «**[SKILL_UI_REDESIGN]** camada [Chrome|Painel|Listagens|Forms].»

---

## O que NÃO pedir mais (redundante / falso)

| Antigo | Por quê | Use em vez |
|--------|---------|------------|
| Comandos ingleses soltos do impeccable (`polish`, `bolder`…) | Cardápio PT já escolhe o motor | skills da tabela |
| `frontend-design` plugin direto | Sobreposto ao impeccable no craft | `[SKILL_UI_PLAN]` / `[SKILL_UI_LANDING]` / `[SKILL_UI_REFACTOR]` |
| `ui-design` marketplace (dezenas de skills) | Ruído; gates+impeccable cobrem o fluxo | cardápio acima |
| `design-an-interface` | É API/módulo, **não** UI | (fora deste cardápio) |
| `[SKILL_DESIGN_A]`, `[SKILL_DESIGN_B]` | Citados no stack, **sem pasta** no Claude | remover do stack |
| `asc-app-create-ui` | Automação App Store Connect, não design | (fora) |
| `product-partner` | Ciclo de produto inteiro | só se for lançar produto, não UI pontual |
| `meigen-ai-design` | Geração de imagem | só se precisar de asset ilustrado |

Plugins oficiais **permanecem instalados** como motor; o ponto de entrada é este cardápio.

---

## Ordem fixa de qualquer skill deste cardápio

1. R0 (`ux-ui-INDEX.md`)
2. Gates (`ux-ui-criteria.md` + web/mobile se couber)
3. Motor impeccable / verify conforme a skill
4. Checklists na entrega; sem prova social inventada
