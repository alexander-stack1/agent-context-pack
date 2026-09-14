# ux-ui-web-landing.md

> **Public template.** Personal identifiers, firm, products, emails and paths were replaced with placeholders. See `PLACEHOLDERS.md`. Do not reintroduce real data.

> Subreglas WEB (desktop) para landing de produto / AI agent.
> Fonte visual: anatomia de landing high-converting (navbar → footer).
> Usar con `ux-ui-criteria.md` + `ux-ui-INDEX.md`. Fail-closed.
> Atualização: 07/09/2026

---

## Cuando aplicar

Tarea = landing page, marketing site, pricing page, home de SaaS/agent **em viewport desktop/web** (≥1024px como referência).

Se también houver mobile: rode este archivo para desktop **e** `ux-ui-mobile.md` para o breakpoint mobile. No misture reglas no mismo paso.

---

## PASO 0 — Gate (obligatorio)

Antes de cualquier sección:

1. Declarar **job** em uma frase: "Visitante consegue X".
2. Declarar **ação primária** da página (uma só).
3. Confirmar modo Impeccable = **Persuade** (se for marketing).
4. Aplicar color **60-30-10** (`ux-ui-INDEX.md` § Cor).

Sem PASO 0 completo → parar e pedir o que faltar.

---

## PASO 1 — Navbar (WEB)

**Hacer**
- Logo à esquerda.
- Links em texto horizontal: Solutions, Benefits, How It Works, Integrations, FAQs, Pricing (só os que existirem no produto; no inventar sección vazia).
- CTA primário siempre visível na barra (botón).

**Subreglas**
- W-NAV-1: Labels literais; máx. 6–7 itens.
- W-NAV-2: CTA da navbar = misma ação primária do Hero (o entrada para ela).
- W-NAV-3: Sem hamburger no desktop ≥1024px.
- W-NAV-4: Hover states em links (web only).

**No fazer**: menu complexo, dropdown aninhado no MVP, CTA secundário empatado con o primário.

**Verificar**: CTA visível sin scroll; labels claros em ≤1s.

---

## PASO 2 — Hero (WEB)

**Hacer**
- Headline no padrão: `[Resultado desejado] — [objeção removida]`.
- Subhead: `paso de ação + benefício prometido pela headline`.
- CTA primário: **Call-to-Value** = verbo de ação + benefício curto (ex.: "Começar grátis — economize 10h/semana"). No usar só "Saiba mais" / "OK".
- Visual grande do produto (mockup o vídeo) mostrando o outcome.

**Subreglas**
- W-HERO-1: Uma headline; sin slogan vazio.
- W-HERO-2: CTA acima da dobra junto con headline (desktop pode colocar visual ao lado; CTA no some abaixo do fold).
- W-HERO-3: Objeção na headline deve ser real do público; se NO VERIFICADO, marcar.
- W-HERO-4: Visual = produto em uso, no stock genérico sin contexto.

**Verificar**: em 3s dá para dizer o que es e o que clicar.

---

## PASO 3 — Social proof (logos)

**Hacer**: faixa horizontal de logos / stats / selos.

**Subreglas**
- W-PROOF-1: Só logos/stats reais; seno `NO VERIFICADO` o omitir a sección.
- W-PROOF-2: No inventar clientes.

---

## PASO 4 — Use cases (3 columnas)

**Hacer**: 3 columnas (ícone + título + subhead). Como o produto encaixa em situações distintas.

**Subreglas**
- W-UC-1: Grid 3 columnas no desktop.
- W-UC-2: Curtas, focadas no público; sin feature dump.
- W-UC-3: Cada columna = um job diferente, no sinônimos.

---

## PASO 5 — Pain points (3 columnas)

**Hacer**: 3 dores con ícone (tom de alerta) + título + subhead; produto como resolução implícita.

**Subreglas**
- W-PAIN-1: Grid 3 columnas.
- W-PAIN-2: Dores do usuario, no reclamações internas do time.
- W-PAIN-3: Sem dark pattern de medo exagerado.

---

## PASO 6 — Why us (3 columnas)

**Hacer**: 3 diferenciais claros (más rápido / más fácil / más confiável — só se verdaderos).

**Subreglas**
- W-WHY-1: Grid 3 columnas.
- W-WHY-2: Cada item comparável a alternativa óbvia; sin superlativo vazio.

---

## PASO 7 — How it works (3–5 pasos)

**Hacer**: caminho numerado con ícones; 3 a 5 pasos.

**Subreglas**
- W-HOW-1: Orden linear; um verbo por paso.
- W-HOW-2: Sem jargão de implementação.

---

## PASO 8 — Benefits (grid 2×2)

**Hacer**: 3–4 benefícios em grid 2×2 (ícone + texto). Foco em “como facilita a vida”, no lista de specs.

**Subreglas**
- W-BEN-1: Desktop = 2 columnas.
- W-BEN-2: Benefício ≠ feature; traduzir feature → outcome.

---

## PASO 9 — Pricing (3 cards)

**Hacer**: 3 planos con features + CTA por card. Destacar o plano recomendado.

**Subreglas**
- W-PRICE-1: Precios só se reais; seno placeholder marcado `EXEMPLO` / `NO VERIFICADO`.
- W-PRICE-2: CTA por card alíneado à ação primária o upgrade.
- W-PRICE-3: Um card visualmente “best” (borda/badge), no três empatados.

---

## PASO 10 — Testimonials

**Hacer**: carrossel/faixa con nota, foto real, quote, resultado.

**Subreglas**
- W-TEST-1: Sem depoimento inventado.
- W-TEST-2: Preferir resultado concreto a elogio vago.

---

## PASO 11 — Bloco CTV (Call-to-Value)

**Hacer**: faixa de alto contraste con CTA ação+benefício.

**Subreglas**
- W-CTV-1: Repete a ação primária; no introduz terceira CTA concorrente.
- W-CTV-2: Contraste forte (accent 10% da regla 60-30-10).

---

## PASO 12 — FAQs

**Hacer**: acordeões (preço, setup, features, cancelamento).

**Subreglas**
- W-FAQ-1: Respostas curtas que removem atrito.
- W-FAQ-2: No esconder preço aquí se ya está na sección Pricing.

---

## PASO 13 — Footer

**Hacer**: links (Features, Pricing, Terms, Privacy, Contact), social, logo, selos de confiança se reais.

**Subreglas**
- W-FOOT-1: Links legais mínimos se for produto real.
- W-FOOT-2: Sem selo inventado.

---

## PASO 14 — Checklist WEB (anexar na entrega)

Marcar SÍ / NÃO / N/A:

- [ ] Orden das seções 1→13 respeitada (seções inexistentes = N/A, no inventar)
- [ ] Navbar con CTA siempre visível
- [ ] Hero: fórmula outcome—objeção + CTV
- [ ] Use cases / pain / why em 3 columnas
- [ ] Benefits em 2×2
- [ ] Pricing con plano destacado + CTA por card
- [ ] 60-30-10 aplicado (accent só em CTAs/ênfase)
- [ ] Hover/focus em controles clicáveis
- [ ] Nenhuma prova social inventada
- [ ] Checklist de `ux-ui-criteria.md` §7 también preenchido

Qualquer NÃO em item MUST → refazer antes de entregar.
