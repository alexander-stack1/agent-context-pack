# ux-ui-criteria.md

> **Public template.** Personal identifiers, firm, products, emails and paths were replaced with placeholders. See `PLACEHOLDERS.md`. Do not reintroduce real data.

> Guia técnico canônico para qualquer IA que gere, revise ou prototipe interface.
> Destilação operacional (não cópia) de: Norman (*The Design of Everyday Things*), Krug (*Don't Make Me Think*), Yablonski (*Laws of UX* / lawsofux.com), Wathan & Schoger (*Refactoring UI*), Johnson (*Designing with the Mind in Mind*).
> Última atualização: 07/09/2026
> Status: CAMADA 1 (carregar em toda tarefa de UI/UX, tela, protótipo, design system ou front).

---

## 0. Como a IA deve usar este arquivo

1. Ler este arquivo **antes** de propor layout, copy de UI, fluxo, componente ou revisão visual.
2. Tratar como **fail-closed**: se um critério MUST não puder ser atendido, declarar `NÃO ATENDE` + motivo; não inventar conformidade.
3. Na entrega, anexar o **Checklist de fechamento** (seção 7) preenchido. Sem checklist = entrega incompleta.
4. Não reproduzir texto integral das obras. Aplicar critérios. Citar a obra só como referência de origem do critério (ex.: "Norman: affordance").
5. Em conflito entre critérios, preferir nesta ordem: (1) clareza da ação principal, (2) redução de carga cognitiva, (3) hierarquia visual, (4) estética.

**Gatilho de prompt (cole quando pedir UI):**
`Siga rigorosamente [CONTEXT_DIR]/ux-ui-criteria.md. Entregue com o checklist de fechamento preenchido. Fail-closed.`

---

## 1. Princípios-mestre (MUST)

### 1.1 Ação óbvia (Krug + Norman)
- A tela deve responder em ≤3 segundos mentais: **o que é isto**, **o que posso fazer**, **onde estou**.
- Uma **ação primária** por tela (ou por estado). Secundárias visivelmente subordinadas.
- Controles devem parecer o que fazem (affordance). Estado atual deve ser perceptível (feedback).
- Mapeamento controle→efeito natural (ex.: gesto/botão alinhado ao resultado esperado).

### 1.2 Não faça o usuário pensar (Krug)
- Rótulos literais, não criativos. Evitar jargão interno.
- Navegação convencional quando existir padrão de plataforma (iOS HIG / web).
- Autoexplicativo > instrução. Se precisar de manual na tela, o fluxo falhou.
- Happy path sem distrações. Opções avançadas atrás de progressive disclosure.

### 1.3 Modelo mental e psicologia (Johnson + Yablonski)
- Projetar para percepção e memória humanas limitadas; não para o modelo do sistema.
- Reduzir escolhas simultâneas (Hick). Alvos grandes o bastante para o contexto (Fitts).
- Consistência com o que o usuário já conhece (Jakob) **dentro do produto e da plataforma**.
- Agrupar o que é processado junto (proximidade / lei da similaridade).
- Evitar sobrecarga: chunks, hierarquia, menos campos no primeiro passo.

### 1.4 Hierarquia e craft visual (Refactoring UI)
- Hierarquia por **tamanho, peso, cor e espaçamento**; não por decoração.
- Espaçamento em escala consistente (ex.: 4/8). Alinhar a uma grade implícita.
- Contraste de texto legível (corpo vs fundo). Não usar cinza claro em cinza claro.
- Cor com função: 1 cor de marca para ênfase; estados (erro/sucesso/aviso) distintos e não só por cor.
- Menos bordas; preferir espaço, sombra sutil ou fundo diferenciado para separar.
- Densidade adequada ao contexto: mobile = menos por tela; desktop pode empilhar com respiro.

### 1.5 Erro, recuperação e confiança (Norman + Johnson)
- Prevenir erro antes de corrigir (constraints, defaults seguros, confirmação só no destrutivo).
- Mensagem de erro: o que aconteceu, por quê (em linguagem humana), como corrigir agora.
- Ações destrutivas: reversíveis quando possível; senão confirmação explícita com consequência nomeada.
- Loading e estados vazios são UI: nunca tela morta sem próximo passo.

---

## 2. MUST-NOT (proibido na entrega)

- Placeholder genérico como copy final ("Lorem", "Click here", "Saiba mais" sem objeto).
- Mais de uma CTA visualmente empatada na mesma região.
- Modal empilhado sobre modal; alerta que não diz o que fazer.
- Ícone sem rótulo quando o significado não é universal.
- Formulário pedindo dado que o sistema já tem ou que pode ser opcional depois.
- Animação que atrasa a tarefa ou esconde estado.
- Dark pattern: urgência falsa, opt-out escondido, checkbox pré-marcado prejudicial.
- Contraste insuficiente; texto sobre imagem sem scrim.
- Inventar métricas de usabilidade ou "testes com usuários" sem evidência.

---

## 3. Critérios por tipo de entrega

### 3.1 Wireframe / fluxo
- Listar telas e estados (vazio, carregando, erro, sucesso, permissão negada).
- Marcar ação primária e dados mínimos do MVP.
- Explicitar decisões do usuário e pontos de abandono.

### 3.2 UI de alta fidelidade / App Store solo
- Tipografia: no máximo 2 famílias; escala limitada (ex.: 3–5 tamanhos).
- Componentes reutilizados com mesmo padding e raio.
- Safe areas iOS; alvos ≥ 44pt quando tocáveis.
- Acessibilidade mínima: Dynamic Type quando couber; labels em controles; não informação só por cor.

### 3.3 Copy de interface
- Verbo no botão = resultado ("Salvar PDF", não "OK").
- Título da tela = tarefa ou objeto, não marketing.
- Microcopy de erro e vazio escritos por último, nunca omitidos.

### 3.4 Revisão de tela existente
- Relatar achados como: `ACHADO` | `OK` | `NÃO VERIFICADO` | `NÃO APLICÁVEL`.
- Cada `ACHADO` com: critério violado (seção deste guia), evidência na tela, correção mínima.

---

## 4. Mapa rápido: obra → o que extrair (sem citar texto)

| Fonte | Use para |
|-------|----------|
| Norman | Affordance, signifiers, feedback, mapping, constraints, gulfs of execution/evaluation |
| Krug | Clareza imediata, happy path, navegação óbvia, testes de usabilidade leves |
| Yablonski / lawsofux.com | Hick, Fitts, Jakob, Miller, Prägnanz, aesthetic-usability, postel's, peak-end (aplicar com parcimônia) |
| Refactoring UI | Hierarquia tipográfica, espaçamento, cor, profundidade, alinhamento, empty states visuais |
| Johnson | Percepção, atenção, memória, reconhecimento vs recordação, carga cognitiva |

Site de apoio gratuito (não substitui o livro): https://lawsofux.com/

---

## 5. Ordem de trabalho obrigatória (gerar UI)

1. **Job**: uma frase "usuário consegue X quando Y".
2. **Estados**: lista completa antes de desenhar.
3. **Estrutura**: hierarquia e ação primária (sem cor).
4. **Craft**: tipografia, espaço, cor, componentes.
5. **Copy**: rótulos finais.
6. **Stress**: vazio, erro, offline, 1ª abertura, retorno.
7. **Checklist** (seção 7).

Não pular para cores/estilo antes dos passos 1–3.

---

## 6. Critérios de rejeição automática da entrega

A IA deve **refazer** (não entregar) se:
- Ação primária ambígua;
- Checklist ausente ou com itens MUST em branco;
- Copy placeholder;
- Nenhum estado de erro/vazio descrito;
- Contraste ou alvo de toque claramente insuficientes no que foi especificado.

---

## 7. Checklist de fechamento (obrigatório na resposta)

Copiar e marcar `SIM` / `NÃO` / `N/A`. Todo `NÃO` exige correção ou justificativa `NÃO ATENDE`.

**Clareza**
- [ ] Em 3s fica claro o que é a tela e a ação principal
- [ ] Uma CTA primária visível; secundárias subordinadas
- [ ] Rótulos literais; sem jargão interno

**Interação**
- [ ] Controles com affordance/signifier adequados
- [ ] Feedback imediato para ações (toque, submit, save)
- [ ] Destrutivo com confirmação ou undo
- [ ] Estados: vazio / loading / erro / sucesso descritos

**Cognição**
- [ ] Escolhas no passo atual reduzidas ao necessário
- [ ] Consistência com padrões da plataforma e do próprio produto
- [ ] Reconhecimento > memorização (opções visíveis, histórico, defaults)

**Visual**
- [ ] Hierarquia tipográfica clara (≤5 tamanhos úteis)
- [ ] Espaçamento em escala consistente
- [ ] Contraste de texto adequado
- [ ] Cor com função; não só estética
- [ ] Alvos tocáveis adequados (mobile)

**Ética / abuso**
- [ ] Sem dark pattern
- [ ] Sem urgência ou culpa fabricada

**Meta**
- [ ] Job da tela declarado em uma frase
- [ ] Achados marcados OK / ACHADO / NÃO VERIFICADO / NÃO APLICÁVEL quando for revisão

---

## 8. Registro neste contexto

- Arquivo: `[CONTEXT_DIR]/ux-ui-criteria.md`
- Incluir no `_MANIFEST.md` (Camada 1) na próxima revisão estrutural.
- Opcional: apontar em `working-style.md` na seção de design / produto.
- Apps Solo e qualquer bot de UI devem ser instruídos a carregar este arquivo quando a tarefa for interface.

---
*Critérios operacionais para uso por IA. Não substitui a leitura das obras. Não redistribuir PDF das obras.*
