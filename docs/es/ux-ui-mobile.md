# ux-ui-mobile.md

> **Public template.** Personal identifiers, firm, products, emails and paths were replaced with placeholders. See `PLACEHOLDERS.md`. Do not reintroduce real data.

> Subreglas MOBILE para landing responsiva e app UI.
> Fontes visuais: anatomia mobile da landing; práticas mobile UX; contraste mobile vs web.
> Usar con `ux-ui-criteria.md` + `ux-ui-INDEX.md`. Fail-closed.
> Atualização: 07/09/2026

---

## Cuando aplicar

- Breakpoint mobile de landing/marketing (≤768px), **ou**
- App nativo / PWA con navegação por abas, **ou**
- Chat/agent UI em telefone.

Se a tarefa for landing completa: primero `ux-ui-web-landing.md` (desktop), después **este archivo** para o layout mobile. No aplicar grid de 3 columnas no mobile.

---

## PASO 0 — Gate MOBILE

1. Declarar contexto: `landing-mobile` | `app-shell` | `chat-agent`.
2. Portrait-first. Landscape = bônus, no default.
3. Atenção curta: uma tarefa por pantalla; CTAs acima da dobra.
4. Cor 60-30-10 (`ux-ui-INDEX.md`).
5. Alvos de toque ≥ 44×44 pt/px CSS.

---

## A. Landing mobile (seções da misma anatomia, layout diferente)

### PASO M1 — Navbar mobile

**Hacer**
- Logo à esquerda.
- CTA compacto (“Get Started” / ação primária) visível.
- Hamburger à direita para o restante dos links (Solutions, Pricing, FAQs…).

**Subreglas**
- M-NAV-1: Sem fila de 6 links em texto no topo mobile.
- M-NAV-2: CTA da barra = ação primária (no “Menu”).
- M-NAV-3: Menu aberto = lista clara + fechar óbvio; sin modal empilhado.

### PASO M2 — Hero mobile (pilha vertical)

Orden obligatoria (de cima para baixo):

1. Headline (`[resultado] — [objeção]`)
2. Subhead curto
3. **CTA primário (CTV)** ← antes do visual
4. Visual/produto

**Subreglas**
- M-HERO-1: CTA acima do visual (acima da dobra).
- M-HERO-2: Uma columna; sin texto ao lado do mockup.
- M-HERO-3: Tipografia legível sin zoom (corpo ≥ 16px).

### PASO M3 — Seções de conteúdo

Use cases, pain, why, how, benefits, pricing, testimonials, CTV, FAQ, footer:

**Subreglas**
- M-LAY-1: **Sempre 1 columna**. Cards empilhados.
- M-LAY-2: Pricing = cards empilhados; plano “best” primero o con badge claro.
- M-LAY-3: Testimonials = 1 card visível + swipe (gesto), no 5 fotos lado a lado.
- M-LAY-4: FAQ acordeão full-width.
- M-LAY-5: Espaçamento generoso entre seções; polegar precisa de respiro.

### PASO M4 — Checklist landing mobile

- [ ] Hamburger + CTA na navbar
- [ ] Hero: headline → CTA → visual
- [ ] 1 columna em todas as seções de grid
- [ ] CTA acima da dobra
- [ ] Fontes legíveis; alvos ≥ 44pt
- [ ] 60-30-10; accent só em CTA

---

## B. App mobile (shell de produto)

### PASO M5 — Navegação app

**Hacer**
- Preferir **bottom tab bar** (3–5 destinos) para tareas principais.
- Hamburger só para secundário/settings, no para o core path.

**Subreglas**
- M-APP-1: Destinos da tab = tareas frequentes; labels curtos + ícone.
- M-APP-2: Tab ativa visualmente óbvia.
- M-APP-3: No depender de hover.

### PASO M6 — Interação touch

**Subreglas**
- M-TOUCH-1: Tap / swipe / pinch; sin Affordance só de hover.
- M-TOUCH-2: Controles finger-friendly (≥ 44pt); espaçamento entre alvos.
- M-TOUCH-3: Gestos descobertos con signifier (o evitar gesto oculto no MVP).

### PASO M7 — Conteúdo e atención

**Subreglas**
- M-ATT-1: Uma ação primária por pantalla.
- M-ATT-2: Minimizar digitação (defaults, picker, autocomplete, OCR/scan se couber).
- M-ATT-3: Otimizar para vários tamaños (safe area, notch, teclado aberto).
- M-ATT-4: Sesson curta: estado salvo; retomar sin refazer.

### PASO M8 — Checklist app mobile

- [ ] Bottom nav o padrão de plataforma justificado
- [ ] Sem dependência de hover
- [ ] Alvos ≥ 44pt; tipografia legível
- [ ] Digitação mínima no happy path
- [ ] Estados: vazio / loading / error / offline
- [ ] Safe areas respeitadas

---

## C. Chat / conversational agent (mobile)

### PASO M9 — Layout chat

**Hacer**
- Header: título do agente + ações (busca/perfil) sin roubar a área de mensagens.
- Histórico em bolhas (user vs agent) con contraste claro.
- Input fixo embaixo: campo + enviar; mic opcional se voz existir de verdade.

**Subreglas**
- M-CHAT-1: Input siempre acessível (acima do teclado).
- M-CHAT-2: Mensagens longas do agente quebradas; CTAs inline só cuando forem a ação.
- M-CHAT-3: No inventar voz/mic se no houver implementação.

### PASO M10 — Checklist chat

- [ ] Bolhas distinguíveis
- [ ] Input inferior estável
- [ ] Enviar con alvo ≥ 44pt
- [ ] Erro de envio recuperável

---

## D. Tabela rápida MOBILE vs WEB (no confundir)

| Dimenson | MOBILE | WEB |
|----------|--------|-----|
| Nav | Hamburger + CTA; o bottom tabs no app | Links horizontais + CTA siempre visível |
| Layout | 1 columna | Grid 2–3 columnas |
| Interação | Touch/gesture; sin hover | Click + hover + teclado |
| Orientação | Portrait-first | Landscape amplo |
| Atenção | Tarea rápida | Exploração más longa |
| Hero landing | CTA **antes** do visual | Visual pode ficar ao lado; CTA acima da dobra |

---

## Rejeição automática (mobile)

Rehacer se:
- Grid de 3 columnas no mobile;
- CTA do hero abaixo do visual;
- Links desktop cravados no topo sin hamburger;
- Alvo &lt; 44pt sin justificativa;
- Hover como único signifier.
