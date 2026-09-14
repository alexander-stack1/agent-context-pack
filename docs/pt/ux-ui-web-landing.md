# ux-ui-web-landing.md

> **Public template.** Personal identifiers, firm, products, emails and paths were replaced with placeholders. See `PLACEHOLDERS.md`. Do not reintroduce real data.

> Subregras WEB (desktop) para landing de produto / AI agent.
> Fonte visual: anatomia de landing high-converting (navbar → footer).
> Usar com `ux-ui-criteria.md` + `ux-ui-INDEX.md`. Fail-closed.
> Atualização: 07/09/2026

---

## Quando aplicar

Tarefa = landing page, marketing site, pricing page, home de SaaS/agent **em viewport desktop/web** (≥1024px como referência).

Se também houver mobile: rode este arquivo para desktop **e** `ux-ui-mobile.md` para o breakpoint mobile. Não misture regras no mesmo passo.

---

## PASSO 0 — Gate (obrigatório)

Antes de qualquer seção:

1. Declarar **job** em uma frase: "Visitante consegue X".
2. Declarar **ação primária** da página (uma só).
3. Confirmar modo Impeccable = **Persuade** (se for marketing).
4. Aplicar cor **60-30-10** (`ux-ui-INDEX.md` § Cor).

Sem PASSO 0 completo → parar e pedir o que faltar.

---

## PASSO 1 — Navbar (WEB)

**Fazer**
- Logo à esquerda.
- Links em texto horizontal: Solutions, Benefits, How It Works, Integrations, FAQs, Pricing (só os que existirem no produto; não inventar seção vazia).
- CTA primário sempre visível na barra (botão).

**Subregras**
- W-NAV-1: Labels literais; máx. 6–7 itens.
- W-NAV-2: CTA da navbar = mesma ação primária do Hero (ou entrada para ela).
- W-NAV-3: Sem hamburger no desktop ≥1024px.
- W-NAV-4: Hover states em links (web only).

**Não fazer**: menu complexo, dropdown aninhado no MVP, CTA secundário empatado com o primário.

**Verificar**: CTA visível sem scroll; labels claros em ≤1s.

---

## PASSO 2 — Hero (WEB)

**Fazer**
- Headline no padrão: `[Resultado desejado] — [objeção removida]`.
- Subhead: `passo de ação + benefício prometido pela headline`.
- CTA primário: **Call-to-Value** = verbo de ação + benefício curto (ex.: "Começar grátis — economize 10h/semana"). Não usar só "Saiba mais" / "OK".
- Visual grande do produto (mockup ou vídeo) mostrando o outcome.

**Subregras**
- W-HERO-1: Uma headline; sem slogan vazio.
- W-HERO-2: CTA acima da dobra junto com headline (desktop pode colocar visual ao lado; CTA não some abaixo do fold).
- W-HERO-3: Objeção na headline deve ser real do público; se NÃO VERIFICADO, marcar.
- W-HERO-4: Visual = produto em uso, não stock genérico sem contexto.

**Verificar**: em 3s dá para dizer o que é e o que clicar.

---

## PASSO 3 — Social proof (logos)

**Fazer**: faixa horizontal de logos / stats / selos.

**Subregras**
- W-PROOF-1: Só logos/stats reais; senão `NÃO VERIFICADO` ou omitir a seção.
- W-PROOF-2: Não inventar clientes.

---

## PASSO 4 — Use cases (3 colunas)

**Fazer**: 3 colunas (ícone + título + subhead). Como o produto encaixa em situações distintas.

**Subregras**
- W-UC-1: Grid 3 colunas no desktop.
- W-UC-2: Curtas, focadas no público; sem feature dump.
- W-UC-3: Cada coluna = um job diferente, não sinônimos.

---

## PASSO 5 — Pain points (3 colunas)

**Fazer**: 3 dores com ícone (tom de alerta) + título + subhead; produto como resolução implícita.

**Subregras**
- W-PAIN-1: Grid 3 colunas.
- W-PAIN-2: Dores do usuário, não reclamações internas do time.
- W-PAIN-3: Sem dark pattern de medo exagerado.

---

## PASSO 6 — Why us (3 colunas)

**Fazer**: 3 diferenciais claros (mais rápido / mais fácil / mais confiável — só se verdadeiros).

**Subregras**
- W-WHY-1: Grid 3 colunas.
- W-WHY-2: Cada item comparável a alternativa óbvia; sem superlativo vazio.

---

## PASSO 7 — How it works (3–5 passos)

**Fazer**: caminho numerado com ícones; 3 a 5 passos.

**Subregras**
- W-HOW-1: Ordem linear; um verbo por passo.
- W-HOW-2: Sem jargão de implementação.

---

## PASSO 8 — Benefits (grid 2×2)

**Fazer**: 3–4 benefícios em grid 2×2 (ícone + texto). Foco em “como facilita a vida”, não lista de specs.

**Subregras**
- W-BEN-1: Desktop = 2 colunas.
- W-BEN-2: Benefício ≠ feature; traduzir feature → outcome.

---

## PASSO 9 — Pricing (3 cards)

**Fazer**: 3 planos com features + CTA por card. Destacar o plano recomendado.

**Subregras**
- W-PRICE-1: Preços só se reais; senão placeholder marcado `EXEMPLO` / `NÃO VERIFICADO`.
- W-PRICE-2: CTA por card alinhado à ação primária ou upgrade.
- W-PRICE-3: Um card visualmente “best” (borda/badge), não três empatados.

---

## PASSO 10 — Testimonials

**Fazer**: carrossel/faixa com nota, foto real, quote, resultado.

**Subregras**
- W-TEST-1: Sem depoimento inventado.
- W-TEST-2: Preferir resultado concreto a elogio vago.

---

## PASSO 11 — Bloco CTV (Call-to-Value)

**Fazer**: faixa de alto contraste com CTA ação+benefício.

**Subregras**
- W-CTV-1: Repete a ação primária; não introduz terceira CTA concorrente.
- W-CTV-2: Contraste forte (accent 10% da regra 60-30-10).

---

## PASSO 12 — FAQs

**Fazer**: acordeões (preço, setup, features, cancelamento).

**Subregras**
- W-FAQ-1: Respostas curtas que removem atrito.
- W-FAQ-2: Não esconder preço aqui se já está na seção Pricing.

---

## PASSO 13 — Footer

**Fazer**: links (Features, Pricing, Terms, Privacy, Contact), social, logo, selos de confiança se reais.

**Subregras**
- W-FOOT-1: Links legais mínimos se for produto real.
- W-FOOT-2: Sem selo inventado.

---

## PASSO 14 — Checklist WEB (anexar na entrega)

Marcar SIM / NÃO / N/A:

- [ ] Ordem das seções 1→13 respeitada (seções inexistentes = N/A, não inventar)
- [ ] Navbar com CTA sempre visível
- [ ] Hero: fórmula outcome—objeção + CTV
- [ ] Use cases / pain / why em 3 colunas
- [ ] Benefits em 2×2
- [ ] Pricing com plano destacado + CTA por card
- [ ] 60-30-10 aplicado (accent só em CTAs/ênfase)
- [ ] Hover/focus em controles clicáveis
- [ ] Nenhuma prova social inventada
- [ ] Checklist de `ux-ui-criteria.md` §7 também preenchido

Qualquer NÃO em item MUST → refazer antes de entregar.
