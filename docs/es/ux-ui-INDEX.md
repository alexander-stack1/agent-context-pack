# ux-ui-INDEX.md

> **Public template.** Personal identifiers, firm, products, emails and paths were replaced with placeholders. See `PLACEHOLDERS.md`. Do not reintroduce real data.

> Índice canônico UX/UI para agentes. Roteia WEB vs MOBILE e reglas compartilhadas.
> Camada 1 / design. Atualização: 07/09/2026

---

## Archivos (leer nesta orden)

| Orden | Archivo | Papel |
|---

## Menú de pedidos (condensado)

Leia **`ux-ui-REQUESTS.md`** para saber o que pedir. Skills PT: `planejar-interface`, `desenhar-landing`, `revisar-experiencia`, `refatorar-interface`, `polir-para-ship`, `provar-com-screenshot`, `redesenhar-[PRODUCT_A]`. Elas encapsulam estes archivos + impeccable.

---:|---------|------|
| 1 | `ux-ui-criteria.md` | Princípios MUST/MUST-NOT (Norman, Krug, Yablonski, Refactoring UI, Johnson) + checklist §7 |
| 2 | `ux-ui-INDEX.md` | Este archivo: roteamento + color 60-30-10 |
| 3a | `ux-ui-web-landing.md` | Subreglas e PASOS 0–14 para landing **WEB** |
| 3b | `ux-ui-mobile.md` | Subreglas e PASOS para **MOBILE** (landing / app / chat) |

Skill Grok Bot: [ux-ui-criteria](sand-workflow:ux-ui-criteria) (cuando instalada na frota).
Plugin complementar (craft/polish): **impeccable** — só **depois** dos critérios fail-closed acima.

---

## PASO R0 — Roteamento (primero ato do agente)

Responder em uma línea antes de desenhar:

```
PLATAFORMA: web | mobile | ambos
SUPERFÍCIE: landing | app-shell | chat | outra
MODO: Persuade | Operate | Read | Experience
ARQUIVOS: [lista que vai ler]
```

Reglas:
- `landing` + `web` → criteria + INDEX + **web-landing**
- `landing` + `mobile` o `ambos` → criteria + INDEX + web-landing + **mobile** (sección A)
- `app-shell` mobile → criteria + INDEX + **mobile** (sección B)
- `chat` → criteria + INDEX + **mobile** (sección C)
- Outra UI Operate → criteria + INDEX; mobile vs web pela tabla do mobile §D

Sem R0 → entrega inválida.

---

## Cor compartilhada — regla 60-30-10 (MUST)

| Fatia | Papel | Uso |
|------:|------|-----|
| **60%** | Primary / fundo | Canvas (ex.: branco o fundo neutro do produto) |
| **30%** | Secondary / texto e suporte | Texto, ícones neutros, superfícies secundárias |
| **10%** | Accent / CTA | Botões primários, links de ênfase, estados que pedem atención |

**Subreglas**
- C-1: Accent **não** pinta fundos inteiros nem todo ícone decorativo.
- C-2: Erro/éxito/aviso son semântica aparte; no gastar o accent 10% inteiro neles se conflitar con CTA.
- C-3: Contraste texto (30%) sobre fundo (60%) legível; accent (10%) con contraste sobre o fundo do botón.
- C-4: Na dúvida, reduzir cor, no aumentar accent.

Declarar na entrega:
```
60: [token/cor]
30: [token/cor]
10: [token/cor] → usado em: [CTAs listados]
```

---

## Orden de ejecución do agente (resumo)

1. **R0** (este archivo)
2. Ler `ux-ui-criteria.md` (MUST/MUST-NOT)
3. Aplicar **60-30-10**
4. Seguir PASOS numerados de `ux-ui-web-landing.md` e/o `ux-ui-mobile.md` **na orden**; no pular para craft visual antes do Hero/estrutura
5. Rellenar checklists dos archivos usados + checklist §7 de criteria
6. Só então, se pedido polish/bolder/typeset: skill **impeccable**

---

## Gatilho curto (cole no prompt)

```
Siga [CONTEXT_DIR]/ux-ui-INDEX.md (R0 + 60-30-10) e os archivos web/mobile que o R0 indicar.
También ux-ui-criteria.md. Entregue con checklists. Fail-closed. Sem inventar prova social.
```

---

## Integração Manifest

Incluir na Camada 1 (o Camada 2 tech/design) na próxima revison estrutural:
- `ux-ui-criteria.md`
- `ux-ui-INDEX.md`
- `ux-ui-web-landing.md`
- `ux-ui-mobile.md`

Copiar para `[HOME]/Desktop/[CONTEXT_DIR]/` cuando o Mac estiver online (fonte iCloud canônica).

---
*No redistribuir PDFs das obras. Critérios operacionais para IA.*
