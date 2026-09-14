# ux-ui-INDEX.md

> **Public template.** Personal identifiers, firm, products, emails and paths were replaced with placeholders. See `PLACEHOLDERS.md`. Do not reintroduce real data.

> Índice canônico UX/UI para agentes. Roteia WEB vs MOBILE e regras compartilhadas.
> Camada 1 / design. Atualização: 07/09/2026

---

## Arquivos (ler nesta ordem)

| Ordem | Arquivo | Papel |
|---

## Cardápio de pedidos (condensado)

Leia **`ux-ui-PEDIDOS.md`** para saber o que pedir. Skills PT: `planejar-interface`, `desenhar-landing`, `revisar-experiencia`, `refatorar-interface`, `polir-para-ship`, `provar-com-screenshot`, `redesenhar-[PRODUCT_A]`. Elas encapsulam estes arquivos + impeccable.

---:|---------|------|
| 1 | `ux-ui-criteria.md` | Princípios MUST/MUST-NOT (Norman, Krug, Yablonski, Refactoring UI, Johnson) + checklist §7 |
| 2 | `ux-ui-INDEX.md` | Este arquivo: roteamento + cor 60-30-10 |
| 3a | `ux-ui-web-landing.md` | Subregras e PASSOS 0–14 para landing **WEB** |
| 3b | `ux-ui-mobile.md` | Subregras e PASSOS para **MOBILE** (landing / app / chat) |

Skill Grok Bot: [ux-ui-criteria](sand-workflow:ux-ui-criteria) (quando instalada na frota).
Plugin complementar (craft/polish): **impeccable** — só **depois** dos critérios fail-closed acima.

---

## PASSO R0 — Roteamento (primeiro ato do agente)

Responder em uma linha antes de desenhar:

```
PLATAFORMA: web | mobile | ambos
SUPERFÍCIE: landing | app-shell | chat | outra
MODO: Persuade | Operate | Read | Experience
ARQUIVOS: [lista que vai ler]
```

Regras:
- `landing` + `web` → criteria + INDEX + **web-landing**
- `landing` + `mobile` ou `ambos` → criteria + INDEX + web-landing + **mobile** (seção A)
- `app-shell` mobile → criteria + INDEX + **mobile** (seção B)
- `chat` → criteria + INDEX + **mobile** (seção C)
- Outra UI Operate → criteria + INDEX; mobile vs web pela tabela do mobile §D

Sem R0 → entrega inválida.

---

## Cor compartilhada — regra 60-30-10 (MUST)

| Fatia | Papel | Uso |
|------:|------|-----|
| **60%** | Primary / fundo | Canvas (ex.: branco ou fundo neutro do produto) |
| **30%** | Secondary / texto e suporte | Texto, ícones neutros, superfícies secundárias |
| **10%** | Accent / CTA | Botões primários, links de ênfase, estados que pedem atenção |

**Subregras**
- C-1: Accent **não** pinta fundos inteiros nem todo ícone decorativo.
- C-2: Erro/sucesso/aviso são semântica aparte; não gastar o accent 10% inteiro neles se conflitar com CTA.
- C-3: Contraste texto (30%) sobre fundo (60%) legível; accent (10%) com contraste sobre o fundo do botão.
- C-4: Na dúvida, reduzir cor, não aumentar accent.

Declarar na entrega:
```
60: [token/cor]
30: [token/cor]
10: [token/cor] → usado em: [CTAs listados]
```

---

## Ordem de execução do agente (resumo)

1. **R0** (este arquivo)
2. Ler `ux-ui-criteria.md` (MUST/MUST-NOT)
3. Aplicar **60-30-10**
4. Seguir PASSOS numerados de `ux-ui-web-landing.md` e/ou `ux-ui-mobile.md` **na ordem**; não pular para craft visual antes do Hero/estrutura
5. Preencher checklists dos arquivos usados + checklist §7 de criteria
6. Só então, se pedido polish/bolder/typeset: skill **impeccable**

---

## Gatilho curto (cole no prompt)

```
Siga [CONTEXT_DIR]/ux-ui-INDEX.md (R0 + 60-30-10) e os arquivos web/mobile que o R0 indicar.
Também ux-ui-criteria.md. Entregue com checklists. Fail-closed. Sem inventar prova social.
```

---

## Integração Manifest

Incluir na Camada 1 (ou Camada 2 tech/design) na próxima revisão estrutural:
- `ux-ui-criteria.md`
- `ux-ui-INDEX.md`
- `ux-ui-web-landing.md`
- `ux-ui-mobile.md`

Copiar para `[HOME]/Desktop/[CONTEXT_DIR]/` quando o Mac estiver online (fonte iCloud canônica).

---
*Não redistribuir PDFs das obras. Critérios operacionais para IA.*
