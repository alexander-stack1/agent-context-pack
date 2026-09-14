# ux-ui-REQUESTS.md

> **Public template.** Personal identifiers, firm, products, emails and paths were replaced with placeholders. See `PLACEHOLDERS.md`. Do not reintroduce real data.

> Menú condensado: o que pedir na contratação de UI o na refatoração.
> Atualização: 07/09/2026
> Gates canônicos em `ux-ui-INDEX.md` + `ux-ui-criteria.md` (+ web/mobile). Craft via **impeccable** / **frontend-design** por baixo — tú no precisa lembrar os nomes em inglês.

---

## Peça así (7 skills)

| Tú quer… | Peça / skill | Encapsula |
|------------|--------------|-----------|
| Planejar pantalla **antes** de codar | **`planejar-interface`** | R0 + gates + impeccable `shape` (+ variantes se pedido) |
| Landing / marketing web+mobile | **`desenhar-landing`** | gates web-landing + mobile + modo Persuade |
| Revisar UX, a11y, responsivo | **`revisar-experiencia`** | gates checklist + impeccable `critique` + `audit` |
| Refatorar visual (hierarquia, tipo, cor, mobile↔web) | **`refatorar-interface`** | gates + `distill` / `layout` / `typeset` / `adapt` / `colorize` / `clarify` según o caso |
| Polir e endurecer pra ship | **`polir-para-ship`** | `polish` + `harden` + `provar-com-screenshot` |
| Provar que a pantalla fico certa | **`provar-com-screenshot`** | `visual-verify` (screenshot vs referência) |
| Redesign incremental do [PRODUCT_A] | **`redesenhar-[PRODUCT_A]`** | briefing [PRODUCT_A] + gates (no troca marca) |

Skill de base (raramente pedir sozinha): `ux-ui-criteria` — só os gates fail-closed.

---

## Frases listas

- «Roda **planejar-interface** pra [pantalla/fluxo].»
- «**desenhar-landing** do [produto], web e mobile.»
- «**revisar-experiencia** nesta página / neste PR.»
- «**refatorar-interface**: está poluído / ilegível / quebra no mobile.»
- «**polir-para-ship** antes do merge.»
- «**provar-com-screenshot** contra o mock / sibling.»
- «**redesenhar-[PRODUCT_A]** camada [Chrome|Painel|Listagens|Forms].»

---

## O que NÃO pedir más (redundante / falso)

| Antigo | Por quê | Use em vez |
|--------|---------|------------|
| Comandos ingleses soltos do impeccable (`polish`, `bolder`…) | Menú PT ya escolhe o motor | skills da tabla |
| `frontend-design` plugin direto | Sobreposto ao impeccable no craft | `planejar-interface` / `desenhar-landing` / `refatorar-interface` |
| `ui-design` marketplace (dezenas de skills) | Ruído; gates+impeccable cobrem o fluxo | menú acima |
| `design-an-interface` | É API/módulo, **não** UI | (fora deste menú) |
| `design-mentes-brilhantes`, `apple-design-master` | Citados no stack, **sin carpeta** no Claude | remover do stack |
| `asc-app-create-ui` | Automação App Store Connect, no design | (fora) |
| `product-partner` | Ciclo de produto inteiro | só se for lançar produto, no UI pontual |
| `meigen-ai-design` | Geração de imagem | só se precisar de asset ilustrado |

Plugins oficiais **permanecem instalados** como motor; o ponto de entrada es este menú.

---

## Orden fixa de cualquier skill deste menú

1. R0 (`ux-ui-INDEX.md`)
2. Gates (`ux-ui-criteria.md` + web/mobile se couber)
3. Motor impeccable / verify según a skill
4. Checklists na entrega; sin prova social inventada
