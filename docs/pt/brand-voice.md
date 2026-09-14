# brand-voice.md

> **Public template.** Personal identifiers, firm, products, emails and paths were replaced with placeholders. See `PLACEHOLDERS.md`. Do not reintroduce real data.

> Voz das marcas: [YOUR_HANDLE], [YOUR_FIRM], Nexo Tecnologia e os produtos legaltech.
> Fonte canônica de contexto. Última atualização: 31/08/2026.
> Skill de referência para copy: `copy-marca-pessoal`.

## Princípio comum

Jurista-legaltech crítico, nunca influencer. Linguagem direta, sem jargão de coach. Todo conteúdo tem lastro doutrinário ou empírico. A autoridade vem do argumento e do dado, não do tom.

## Marca pessoal [YOUR_HANDLE]

Voz de quem entende de direito e de tecnologia e tem opinião. Crítico, preciso e sem medo de contrariar o senso comum do meio jurídico.

Cinco pilares editoriais:
1. build-in-public legaltech (mostrar a construção dos produtos, decisões técnicas e de negócio)
2. crítica à reforma trabalhista
3. crítica ao mercado jurídico
4. análise de jurisprudência
5. doutrina constitucional do trabalho

Identidade visual: editorial-magazine, paleta near-monochromatic, tipografia Cormorant Garamond, Bebas Neue e DM Sans.

## [YOUR_FIRM] (institucional)

Voz da banca para cliente e mercado. Sóbria, técnica e confiável, sem frieza. Comunica competência e cuidado com o reclamante. Evita promessa de resultado e linguagem sensacionalista. Documentos oficiais saem em papel timbrado (ver `working-style.md`, comando `/papel-timbrado`).

## Nexo Tecnologia (empresa)

Voz da empresa que reúne os produtos e os serviços. Fala com o sócio e com o administrador de uma banca de cinco a cinquenta advogados. Não fala com o associado, e não fala com o mercado de tecnologia.

Posicionamento em duas frases, que sustentam toda a comunicação: tradição é ativo, operação antiga é passivo.

Escreve contra três alvos específicos. A consultoria que trata escritório de advocacia como startup e ignora que prazo processual não se adia. O software que exige que a banca mude de identidade para caber nele. E a promessa de que inteligência artificial substitui advogado, que é falsa e queima a confiança de quem já tentou.

### Três regras próprias

- Falamos de operação, não de tecnologia. O sócio não compra IA, compra hora de volta e previsibilidade de caixa.
- Todo número tem fonte, ou é declarado como estimativa nossa com o método à vista. Número sem origem não sai.
- Nunca prometemos resultado processual. A Nexo vende operação, não vitória.

### Cinco pilares editoriais, com peso

| Pilar | Peso | Template do kit | Objetivo |
|-------|:----:|-----------------|----------|
| Diagnóstico | 30% | `feed-A-dado` | Engajamento e reconhecimento do problema |
| Método | 25% | `feed-B-carrossel` | Educação e credibilidade |
| Demonstração | 20% | `feed-C-produto` | Conversão |
| Prova | 15% | `feed-D-depoimento` | Conversão |
| Bastidor | 10% | `feed-E-founder` | Reputação |

O Método é o pilar que sustenta a credibilidade, porque ensina a resolver o problema sem comprar nada. Se cair abaixo de 20% no mês, a conta vira catálogo.

### Ecossistema

[PRODUCT_A] (gestão jurídica), [PRODUCT_H] (captação e atendimento por IA 24h), Nexo Academy (mentoria e formação), consultoria de presença digital. Oferta de entrada em todas as redes: diagnóstico gratuito de trinta minutos.

### Identidade visual

Navy `#0B1F3A` como base, ciano `#00D4FF` como acento, azul `#2563EB` para ação. Violeta `#7C3AED` só quando o assunto é IA, e nunca dentro do símbolo (2,90:1 sobre o navy, abaixo do mínimo de 3:1). Tipografia Sora para título e Inter para corpo.

Kit de marca completo em `Desktop/Negócio/Nexo [BRAND_KIT_DIR] /kit-nexo/`. Regras de logotipo, avatar e assinatura em `01-logotipo/logomarca.md`. Linha editorial completa, com calendário de quatro semanas, régua de copy e métricas, em `06-copy/linha-editorial-nexo.docx`.

## Produtos legaltech

Voz de produto: clara, útil e orientada ao trabalho do advogado. Vende eficiência e confiança, demonstrando valor com exemplos concretos, não com adjetivos.

- **[PRODUCT_A] / [PRODUCT_B]**: pesquisa e análise de jurisprudência trabalhista. Identidade Swiss Legal Design: azul-petróleo (#1B4965) como primária, âmbar dourado (#D4A843) como acento, grid de 12 colunas, tipografia Instrument Serif e Inter.
- **[PRODUCT_G]**: segundo produto, em discovery. Definir posicionamento e voz no lançamento.

## Eixos de copy (escolher conforme o objetivo)

| Objetivo | Eixo |
|----------|------|
| Construir reputação | autoridade |
| Vender produto, curso ou serviço | conversão |
| Gerar discussão e alcance | engajamento |
| Ensinar um conceito ou tese | educação |
| Provocar e diferenciar | crítica |

## Regras de escrita (todas as marcas)

- Nunca usar travessão ou hífen como conector de frases.
- Nunca usar linguagem de IA: "certamente!", "com prazer!", "ótima pergunta!".
- Nunca usar frase de preenchimento: "é importante ressaltar que", "no contexto atual".
- Abrir com dado, caso ou afirmação de impacto, nunca com fórmula genérica.
- Norma culta nos textos técnicos e institucionais, busque sempre no site https://www.normaculta.com.br/. Linguagem direta e humana no conteúdo de rede.
- Rodar a skill `no-tropes` como pós-processamento em toda prosa gerada. O catálogo expandido de tropes está em `~/.claude/skills/no-tropes/tropes-reference.md`.

## Estilo de escrita acadêmico e técnico longo (canônico)

Padrão a ser aplicado em pré-projeto, artigo, tese, dissertação, parecer, memorial, peça de fôlego e qualquer texto de fôlego que não seja copy de rede. Calibrado a partir da revisão do v4 do pré-projeto ADO 73/[YOUR_UNIVERSITY] (jun. 2026).

### 1. Ritmo

Alternar período curto, médio e longo dentro do mesmo parágrafo. Período curto carrega tese ou ponto. Período médio articula. Período longo argumenta. Nunca três frases longas seguidas; nunca três frases curtas seguidas.

### 2. Concreto antes do abstrato

Sempre que possível, abrir o parágrafo com cena, dado, caso ou fonte primária. A categoria teórica vem depois, para nomear o que já foi visto. Exemplo: o e-mail genérico que comunica reavaliação automática da carteira aparece antes da expressão "estado de exceção cibernético".

### 3. Voz autoral em primeira pessoa do plural

Usar "sustentamos", "propomos", "parece-nos", "tomamos posição", "nossa leitura". Evitar "este trabalho pretende", "buscar-se-á demonstrar", "será analisado". Quando houver dúvida real, admitir: "não estamos seguros de que", "permanece em aberto", "talvez".

### 4. Aberturas vivas, fim sem slogan

A primeira frase do parágrafo nunca pode ser fórmula. Banir: "Posta a moldura", "Dois movimentos compõem", "Em primeiro lugar", "É importante destacar que", "Diante do exposto", "Nesse sentido", "Vale ressaltar". O fim do parágrafo pode ser incisivo, e não pode virar tique. Se dois parágrafos seguidos terminam em frase de quatro palavras, refazer um deles.

### 5. Conectivos diversificados

Trocar "além disso", "ademais", "outrossim" e "nesse sentido" por transições que decorram do próprio argumento. Em texto longo, a estrutura pode ser sinalizada por enumeração ("antes de tudo", "vencido esse passo", "resta"), com cautela: enumerar uma vez por capítulo é suficiente.

### 6. Hedging consciente

Em pré-projeto, parecer e pesquisa em andamento, separar o que é tese a defender, hipótese a testar e leitura provisória. Sinalizar grau de consenso: "doutrina majoritária", "leitura minoritária", "posição própria", "ainda em construção".

### 7. Cena, dado e argumento no corpo. Citações na nota de rodapé.

A regra de ouro do estilo separa o corpo do texto da máquina de referenciação. O corpo abriga argumento, cena viva e dado, com a fonte da lei, do acórdão e do diploma comparado mencionada em prosa quando a clareza pedir. As citações no padrão ABNT (autor-data ou completa) vão para a nota de rodapé, e não para o meio do parágrafo. A nota também carrega contraponto, autor secundário e qualificação técnica.

Adoção do sistema **numérico com nota de rodapé** como padrão canônico para textos de fôlego (pré-projeto, artigo, tese, dissertação, capítulo, parecer, memorial). A NBR 10520 admite os dois sistemas, autor-data e numérico, e a escolha é estilística. Nossa preferência é a nota de rodapé porque preserva o ritmo do parágrafo, reduz o ruído visual das referências entre parênteses e abre espaço para a leitura crítica do autor citado.

Critério prático:

- Toda citação ABNT vai para a nota: direta (com aspas e página) e indireta (paráfrase).
- O corpo do texto pode mencionar o autor ("Edelman descreveu...", "Sustenta Sarlet...") sem inserir parêntese de ano. O ano e a referência completa vão na nota.
- Lei, acórdão e diploma comparado podem aparecer no corpo com identificação curta (art. 7º, XXVII, da Constituição; ADO 73/DF; KSchG, § 1). A referência completa vai na nota da primeira ocorrência.
- A nota não é apenas catálogo de referência. É espaço de operação crítica: confirma o uso que se faz do autor, explicita divergências e qualifica o alcance da citação.

### 8. Padrões a remover sempre

Lista negra observada na revisão v4:

- Enumeração fechada em três ou quatro parágrafos seguidos ("A primeira... A segunda... A terceira... A quarta...")
- Aberturas formulares ("Posta a moldura", "Cabe destacar", "Importa observar", "Dois movimentos compõem")
- Adjetivos de cor neutra que disfarçam preguiça: "com precisão clínica", "de forma robusta", "amplamente reconhecido", "fundamental para"
- Slogans repetidos no fim de parágrafo
- Citação sem operação: trazer Autor X, mencionar a tese, e seguir sem usar o que ele disse

### 9. Checklist de fechamento

Antes de entregar texto de fôlego:

1. Lendo em voz alta, há trecho que parece script de podcast de IA? Refazer.
2. Há cena ou dado concreto no primeiro terço do parágrafo? Se não, inserir ou abrir o parágrafo de outro jeito.
3. Há voz autoral marcada em pelo menos uma frase por seção? Se não, marcar.
4. Há padrão da lista negra (item 8)? Remover.
5. O argumento aguenta crítica de banca? Onde a tese for hipótese, sinalizar como hipótese.

---
*Atualize ao lançar novo produto, mudar posicionamento ou identidade visual, e registre no `_CHANGELOG.md`.*
