# ux-ui-mobile.md

> **Public template.** Personal identifiers, firm, products, emails and paths were replaced with placeholders. See `PLACEHOLDERS.md`. Do not reintroduce real data.

> Subregras MOBILE para landing responsiva e app UI.
> Fontes visuais: anatomia mobile da landing; práticas mobile UX; contraste mobile vs web.
> Usar com `ux-ui-criteria.md` + `ux-ui-INDEX.md`. Fail-closed.
> Atualização: 07/09/2026

---

## Quando aplicar

- Breakpoint mobile de landing/marketing (≤768px), **ou**
- App nativo / PWA com navegação por abas, **ou**
- Chat/agent UI em telefone.

Se a tarefa for landing completa: primeiro `ux-ui-web-landing.md` (desktop), depois **este arquivo** para o layout mobile. Não aplicar grid de 3 colunas no mobile.

---

## PASSO 0 — Gate MOBILE

1. Declarar contexto: `landing-mobile` | `app-shell` | `chat-agent`.
2. Portrait-first. Landscape = bônus, não default.
3. Atenção curta: uma tarefa por tela; CTAs acima da dobra.
4. Cor 60-30-10 (`ux-ui-INDEX.md`).
5. Alvos de toque ≥ 44×44 pt/px CSS.

---

## A. Landing mobile (seções da mesma anatomia, layout diferente)

### PASSO M1 — Navbar mobile

**Fazer**
- Logo à esquerda.
- CTA compacto (“Get Started” / ação primária) visível.
- Hamburger à direita para o restante dos links (Solutions, Pricing, FAQs…).

**Subregras**
- M-NAV-1: Sem fila de 6 links em texto no topo mobile.
- M-NAV-2: CTA da barra = ação primária (não “Menu”).
- M-NAV-3: Menu aberto = lista clara + fechar óbvio; sem modal empilhado.

### PASSO M2 — Hero mobile (pilha vertical)

Ordem obrigatória (de cima para baixo):

1. Headline (`[resultado] — [objeção]`)
2. Subhead curto
3. **CTA primário (CTV)** ← antes do visual
4. Visual/produto

**Subregras**
- M-HERO-1: CTA acima do visual (acima da dobra).
- M-HERO-2: Uma coluna; sem texto ao lado do mockup.
- M-HERO-3: Tipografia legível sem zoom (corpo ≥ 16px).

### PASSO M3 — Seções de conteúdo

Use cases, pain, why, how, benefits, pricing, testimonials, CTV, FAQ, footer:

**Subregras**
- M-LAY-1: **Sempre 1 coluna**. Cards empilhados.
- M-LAY-2: Pricing = cards empilhados; plano “best” primeiro ou com badge claro.
- M-LAY-3: Testimonials = 1 card visível + swipe (gesto), não 5 fotos lado a lado.
- M-LAY-4: FAQ acordeão full-width.
- M-LAY-5: Espaçamento generoso entre seções; polegar precisa de respiro.

### PASSO M4 — Checklist landing mobile

- [ ] Hamburger + CTA na navbar
- [ ] Hero: headline → CTA → visual
- [ ] 1 coluna em todas as seções de grid
- [ ] CTA acima da dobra
- [ ] Fontes legíveis; alvos ≥ 44pt
- [ ] 60-30-10; accent só em CTA

---

## B. App mobile (shell de produto)

### PASSO M5 — Navegação app

**Fazer**
- Preferir **bottom tab bar** (3–5 destinos) para tarefas principais.
- Hamburger só para secundário/settings, não para o core path.

**Subregras**
- M-APP-1: Destinos da tab = tarefas frequentes; labels curtos + ícone.
- M-APP-2: Tab ativa visualmente óbvia.
- M-APP-3: Não depender de hover.

### PASSO M6 — Interação touch

**Subregras**
- M-TOUCH-1: Tap / swipe / pinch; sem Affordance só de hover.
- M-TOUCH-2: Controles finger-friendly (≥ 44pt); espaçamento entre alvos.
- M-TOUCH-3: Gestos descobertos com signifier (ou evitar gesto oculto no MVP).

### PASSO M7 — Conteúdo e atenção

**Subregras**
- M-ATT-1: Uma ação primária por tela.
- M-ATT-2: Minimizar digitação (defaults, picker, autocomplete, OCR/scan se couber).
- M-ATT-3: Otimizar para vários tamanhos (safe area, notch, teclado aberto).
- M-ATT-4: Sessão curta: estado salvo; retomar sem refazer.

### PASSO M8 — Checklist app mobile

- [ ] Bottom nav ou padrão de plataforma justificado
- [ ] Sem dependência de hover
- [ ] Alvos ≥ 44pt; tipografia legível
- [ ] Digitação mínima no happy path
- [ ] Estados: vazio / loading / erro / offline
- [ ] Safe areas respeitadas

---

## C. Chat / conversational agent (mobile)

### PASSO M9 — Layout chat

**Fazer**
- Header: título do agente + ações (busca/perfil) sem roubar a área de mensagens.
- Histórico em bolhas (user vs agent) com contraste claro.
- Input fixo embaixo: campo + enviar; mic opcional se voz existir de verdade.

**Subregras**
- M-CHAT-1: Input sempre acessível (acima do teclado).
- M-CHAT-2: Mensagens longas do agente quebradas; CTAs inline só quando forem a ação.
- M-CHAT-3: Não inventar voz/mic se não houver implementação.

### PASSO M10 — Checklist chat

- [ ] Bolhas distinguíveis
- [ ] Input inferior estável
- [ ] Enviar com alvo ≥ 44pt
- [ ] Erro de envio recuperável

---

## D. Tabela rápida MOBILE vs WEB (não confundir)

| Dimensão | MOBILE | WEB |
|----------|--------|-----|
| Nav | Hamburger + CTA; ou bottom tabs no app | Links horizontais + CTA sempre visível |
| Layout | 1 coluna | Grid 2–3 colunas |
| Interação | Touch/gesture; sem hover | Click + hover + teclado |
| Orientação | Portrait-first | Landscape amplo |
| Atenção | Tarefa rápida | Exploração mais longa |
| Hero landing | CTA **antes** do visual | Visual pode ficar ao lado; CTA acima da dobra |

---

## Rejeição automática (mobile)

Refazer se:
- Grid de 3 colunas no mobile;
- CTA do hero abaixo do visual;
- Links desktop cravados no topo sem hamburger;
- Alvo &lt; 44pt sem justificativa;
- Hover como único signifier.
