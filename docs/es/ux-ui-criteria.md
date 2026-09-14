# ux-ui-criteria.md

> **Public template.** Personal identifiers, firm, products, emails and paths were replaced with placeholders. See `PLACEHOLDERS.md`. Do not reintroduce real data.

> Guia técnico canônico para cualquier IA que gere, revise o prototipe interface.
> Destilação operacional (no cópia) de: Norman (*The Design of Everyday Things*), Krug (*Don't Make Me Think*), Yablonski (*Laws of UX* / lawsofux.com), Wathan & Schoger (*Refactoring UI*), Johnson (*Designing with the Mind in Mind*).
> Última actualización: 07/09/2026
> Status: CAMADA 1 (cargar em toda tarefa de UI/UX, pantalla, protótipo, design system o front).

---

## 0. Como a IA deve usar este archivo

1. Ler este archivo **antes** de propor layout, copy de UI, fluxo, componente o revison visual.
2. Tratar como **fail-closed**: se um critério MUST no puder ser atendido, declarar `NO CUMPLE` + motivo; no inventar conformidade.
3. Na entrega, anexar o **Checklist de fechamento** (sección 7) preenchido. Sem checklist = entrega incompleta.
4. No reproduzir texto integral das obras. Aplicar critérios. Citar a obra só como referência de origem do critério (ex.: "Norman: affordance").
5. Em conflito entre critérios, preferir nesta orden: (1) clareza da ação principal, (2) redução de carga cognitiva, (3) hierarquia visual, (4) estética.

**Gatilho de prompt (cole cuando pedir UI):**
`Siga rigorosamente [CONTEXT_DIR]/ux-ui-criteria.md. Entregue con o checklist de fechamento preenchido. Fail-closed.`

---

## 1. Princípios-mestre (MUST)

### 1.1 Ação óbvia (Krug + Norman)
- A pantalla deve responder em ≤3 segundos mentais: **o que es isto**, **o que posso fazer**, **dónde estou**.
- Uma **ação primária** por pantalla (o por estado). Secundárias visivelmente subordinadas.
- Controles devem parecer o que fazem (affordance). Estado atual deve ser perceptível (feedback).
- Mapeamento controle→efeito natural (ex.: gesto/botón alíneado ao resultado esperado).

### 1.2 No faça o usuario pensar (Krug)
- Rótulos literais, no criativos. Evitar jargão interno.
- Navegação convencional cuando existir padrão de plataforma (iOS HIG / web).
- Autoexplicativo > instrução. Se precisar de manual na pantalla, o fluxo falhou.
- Happy path sin distrações. Opções avançadas atrás de progressive disclosure.

### 1.3 Modelo mental e psicologia (Johnson + Yablonski)
- Projetar para percepção e memória humanas limitadas; no para o modelo do sistema.
- Reduzir escolhas simultâneas (Hick). Alvos grandes o bastante para o contexto (Fitts).
- Consistência con o que o usuario ya conhece (Jakob) **dentro do produto e da plataforma**.
- Agrupar o que es processado junto (proximidade / lei da similaridade).
- Evitar sobrecarga: chunks, hierarquia, menos campos no primero paso.

### 1.4 Hierarquia e craft visual (Refactoring UI)
- Hierarquia por **tamaño, peso, color e espaçamento**; no por decoração.
- Espaçamento em escala consistente (ex.: 4/8). Alínear a uma grade implícita.
- Contraste de texto legível (corpo vs fundo). No usar cinza claro em cinza claro.
- Cor con função: 1 color de marca para ênfase; estados (error/éxito/aviso) distintos e no só por cor.
- Menos bordas; preferir espaço, sombra sutil o fundo diferenciado para separar.
- Densidade adequada ao contexto: mobile = menos por pantalla; desktop pode empilhar con respiro.

### 1.5 Erro, recuperação e confiança (Norman + Johnson)
- Prevenir error antes de corrigir (constraints, defaults seguros, confirmação só no destrutivo).
- Mensagem de error: o que aconteceu, por quê (em linguagem humana), como corrigir agora.
- Ações destrutivas: reversíveis cuando possível; seno confirmação explícita con consequência nomeada.
- Loading e estados vazios son UI: nunca pantalla morta sin próximo paso.

---

## 2. MUST-NOT (proibido na entrega)

- Placeholder genérico como copy final ("Lorem", "Click here", "Saiba mais" sin objeto).
- Mais de uma CTA visualmente empatada na misma região.
- Modal empilhado sobre modal; alerta que no diz o que fazer.
- Ícone sin rótulo cuando o significado no es universal.
- Formulário pedindo dado que o sistema ya tem o que pode ser opcional depois.
- Animação que atrasa a tarefa o escdónde estado.
- Dark pattern: urgência falsa, opt-out escondido, checkbox pré-marcado prejudicial.
- Contraste insuficiente; texto sobre imagem sin scrim.
- Inventar métricas de usabilidade o "testes con usuarios" sin evidencia.

---

## 3. Critérios por tipo de entrega

### 3.1 Wireframe / fluxo
- Listar pantallas e estados (vazio, carregando, error, éxito, permisson negada).
- Marcar ação primária e dados mínimos do MVP.
- Explicitar decisões do usuario e pontos de abandono.

### 3.2 UI de alta fidelidade / App Store solo
- Tipografia: no máximo 2 famílias; escala limitada (ex.: 3–5 tamaños).
- Componentes reutilizados con mismo padding e raio.
- Safe areas iOS; alvos ≥ 44pt cuando tocáveis.
- Acessibilidade mínima: Dynamic Type cuando couber; labels em controles; no informação só por cor.

### 3.3 Copy de interface
- Verbo no botón = resultado ("Salvar PDF", no "OK").
- Título da pantalla = tarefa o objeto, no marketing.
- Microcopy de error e vazio escritos por último, nunca omitidos.

### 3.4 Revison de pantalla existente
- Relatar achados como: `HALLAZGO` | `OK` | `NO VERIFICADO` | `NO APLICABLE`.
- Cada `HALLAZGO` com: critério violado (sección deste guia), evidencia na pantalla, correção mínima.

---

## 4. Mapa rápido: obra → o que extrair (sin citar texto)

| Fonte | Use para |
|-------|----------|
| Norman | Affordance, signifiers, feedback, mapping, constraints, gulfs of execution/evaluation |
| Krug | Clareza imediata, happy path, navegação óbvia, testes de usabilidade leves |
| Yablonski / lawsofux.con | Hick, Fitts, Jakob, Miller, Prägnanz, aesthetic-usability, postel's, peak-end (aplicar con parcimônia) |
| Refactoring UI | Hierarquia tipográfica, espaçamento, cor, profundidade, alíneamento, empty states visuais |
| Johnson | Percepção, atención, memória, reconhecimento vs recordação, carga cognitiva |

Site de apoio gratuito (no substitui o livro): https://lawsofux.com/

---

## 5. Orden de trabalho obligatoria (gerar UI)

1. **Job**: uma frase "usuario consegue X cuando Y".
2. **Estados**: lista completa antes de desenhar.
3. **Estrutura**: hierarquia e ação primária (sin cor).
4. **Craft**: tipografia, espaço, cor, componentes.
5. **Copy**: rótulos finais.
6. **Stress**: vazio, error, offline, 1ª abertura, retorno.
7. **Checklist** (sección 7).

No pular para colores/estilo antes dos pasos 1–3.

---

## 6. Critérios de rejeição automática da entrega

A IA deve **refazer** (no entregar) se:
- Ação primária ambígua;
- Checklist ausente o con itens MUST em branco;
- Copy placeholder;
- Nenhum estado de error/vazio descrito;
- Contraste o alvo de toque claramente insuficientes no que foi especificado.

---

## 7. Checklist de fechamento (obligatorio na resposta)

Copiar e marcar `SÍ` / `NÃO` / `N/A`. Todo `NÃO` exige correção o justificativa `NO CUMPLE`.

**Clareza**
- [ ] Em 3s fica claro o que es a pantalla e a ação principal
- [ ] Uma CTA primária visível; secundárias subordinadas
- [ ] Rótulos literais; sin jargão interno

**Interação**
- [ ] Controles con affordance/signifier adequados
- [ ] Feedback imediato para ações (toque, submit, save)
- [ ] Destrutivo con confirmação o undo
- [ ] Estados: vazio / loading / error / éxito descritos

**Cognição**
- [ ] Escolhas no paso atual reduzidas ao necessário
- [ ] Consistência con padrões da plataforma e do propio produto
- [ ] Reconhecimento > memorização (opções visíveis, histórico, defaults)

**Visual**
- [ ] Hierarquia tipográfica clara (≤5 tamaños úteis)
- [ ] Espaçamento em escala consistente
- [ ] Contraste de texto adequado
- [ ] Cor con função; no só estética
- [ ] Alvos tocáveis adequados (mobile)

**Ética / abuso**
- [ ] Sem dark pattern
- [ ] Sem urgência o culpa fabricada

**Meta**
- [ ] Job da pantalla declarado em uma frase
- [ ] Achados marcados OK / HALLAZGO / NO VERIFICADO / NO APLICABLE cuando for revisión

---

## 8. Registro neste contexto

- Archivo: `[CONTEXT_DIR]/ux-ui-criteria.md`
- Incluir no `_MANIFEST.md` (Camada 1) na próxima revison estrutural.
- Opcional: apontar em `working-style.md` na sección de design / produto.
- Apps Solo e cualquier bot de UI devem ser instruídos a cargar este archivo cuando a tarefa for interface.

---
*Critérios operacionais para uso por IA. No substitui a leitura das obras. No redistribuir PDF das obras.*
