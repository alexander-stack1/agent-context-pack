# agent_rules.md

> **Public template.** Personal identifiers, firm, products, emails and paths were replaced with placeholders. See `PLACEHOLDERS.md`. Do not reintroduce real data.

> Regras universais para qualquer IA operando com o contexto de [YOUR_NAME].
> Leia este arquivo PRIMEIRO. Funciona com Claude, Cursor, Codex, Kimi, [PRODUCT_F] e qualquer outro agente.
> Última atualização: 07/09/2026

## Fonte da verdade

Os arquivos em `[CONTEXT_DIR]/` (no [SECONDARY_MACHINE]: `[CONTEXT_DIR]`) são a fonte canônica operacional. A memória do modelo serve para roteamento, as preferências estáveis ficam no `.auto-memory/`, o conhecimento operacional/Karpathy fica no vault `[YOUR_NAME]/`, e o segundo cérebro jurídico de domínio fica em `[DOMAIN_VAULT]` (atalho `[DOMAIN_VAULT]`). O histórico de conversa é contexto secundário.

Roteamento de domínio: se o pedido for jurídico (direito, jurisprudência, legislação, precedentes, doutrina, notícias jurídicas, RAG jurídico), **todas as IAs** devem apontar e consultar o vault Jurídico (`[DOMAIN_VAULT]`). Não usar só memória do modelo no lugar desse vault.

Para Claude/Cowork: ler `identity.md`, `stack.md`, `working-style.md` e `brand-voice.md`.
Para outros agentes: ler este arquivo e seguir os ponteiros abaixo.

| Arquivo | O que contém | Quando ler |
|---------|-------------|------------|
| `identity.md` | Quem [YOUR_NAME] é, frentes, estilo acadêmico | Sempre |
| `stack.md` | Ferramentas, MCPs, skills, plugins, infra IA | Sempre |
| `working-style.md` | Regras de colaboração, protocolos, governança | Sempre |
| `brand-voice.md` | Voz das marcas, estilo de escrita canônico | Ao produzir texto |
| `_PROJETOS-ATIVOS.md` | Estado atual das frentes | Quando a tarefa tocar um projeto |
| `_MANIFEST.md` | Mapa de skills por frente, estrutura da pasta | Para roteamento |

## Regras inegociáveis

### Captura e recuperação

1. Arquivos são o registro autoritativo. Não usar memória do modelo como banco de dados.
2. Nunca inventar fatos para preencher campos vazios. Declarar incertezas.
3. Distinguir relatos do usuário, fatos verificados, observações, preferências e hipóteses.
4. Correções do usuário têm prioridade sobre resumos anteriores.
5. Usar datas exatas quando conhecidas. Registrar explicitamente quando aproximadas.
6. Resumos respondem "o que é verdade agora". Registros datados respondem "o que aconteceu e quando".
7. Antes de responder pergunta sobre o usuário: buscar no vault, ler resumo canônico, seguir links de fonte. Só depois responder.

### Privacidade e exclusões

Nunca armazenar: credenciais, senhas, cookies, códigos de recuperação, chaves de API, seed phrases, tokens de autenticação, dados de pagamento, CPF, número de conta bancária. Generalizar quando necessário. Nunca enviar conteúdo privado a terceiros sem aprovação explícita.

### Escrita

1. Nunca usar travessão como conector de frases em prosa corrida
2. Nunca usar antecipação dramática ("e é aqui que o jogo muda")
3. Nunca usar dois-pontos explicativos ("a lição é direta: use IA")
4. Nunca usar antítese negação + substituição ("não é X, mas Y")
5. Nunca usar parataxe rítmica ("A tela abre. O botão clica.")
6. Nunca usar ênclises e mesóclises artificiais
7. Nunca usar linguagem de IA ("certamente!", "ótima pergunta!", "com prazer!")
8. Nunca usar frases de preenchimento ("é importante ressaltar que", "cabe destacar")
9. Rodar `[SKILL_NO_TROPES]` como pós-processamento em toda prosa gerada

### Engenharia

1. Sem compatibilidade retroativa. Obsoleto = delete direto.
2. Implementação mais simples que atenda à necessidade atual. Canalizar energia YAGNI.
3. Camadas longas, end-to-end primeiro. Nunca desmontar o que funciona.
4. Componentes modulares com separação de responsabilidades.
5. Bibliotecas maduras. Sem motivo, não reescreva do zero.
6. Dependências existentes primeiro, antes de adicionar pacotes.
7. Decisões de arquitetura de longo prazo. Sem "por enquanto faz assim".
8. Padrões validados de produtos maduros. Não inventar a roda.
9. Typesafety é útil, aproveitar. TypeScript: `any` é inimigo, tipos inferidos são aliados. Sistemas devem se adaptar a mudanças sem exigir alteração em todos os lugares. Se o código TS parece escrito por dev Python, está ruim.
10. Comentários descrevem concisamente como funções e classes são usadas. Não comentar cada linha. Manter comentários em sync com o código ao fazer mudanças.
11. Testes focados. Testes são bons. Smoke tests infinitos, testes de regressão para features deletadas e testes genéricos são ruins. Cada teste deve ter propósito claro.
12. Verificação de versão. Antes de gerar código com framework ou biblioteca específica, confirmar que o modelo conhece a versão em uso no projeto. Se não conhecer ou houver dúvida, consultar Context7 MCP ou a documentação oficial antes de assumir API, sintaxe ou comportamento. Nunca gerar código baseado em versão antiga sem avisar.
13. Contexto progressivo. Começar pela Camada 1 do _MANIFEST (identity, stack, working-style, brand-voice). Só carregar Camada 2 quando a tarefa tocar aquele domínio. Nunca carregar Camada 3 sem pedido explícito. Não poluir o contexto com informação que a tarefa não precisa.
14. Error-driven debugging. Antes de propor fix, exigir ou buscar: erro completo com stack trace, código do trecho relevante, resposta da API ou log quando aplicável, e o comportamento esperado vs. o atual. Não diagnosticar com informação parcial. Se faltar algum desses 4 elementos, pedir antes de agir.
15. Justificativa de componente. Antes de propor novo serviço, banco, fila, cache ou dependência de infra, responder: "qual problema específico isso resolve que a infra atual não resolve?" Se a resposta for vaga ou genérica ("escalabilidade", "desacoplamento"), a proposta não está pronta.
16. Estimativa de capacidade. Antes de decisão de infra que envolva escolha entre tecnologias (SQL vs NoSQL, Cloud Run vs VM, com cache vs sem cache), fazer estimativa de envelope: QPS esperado, volume de storage, bandwidth, número de usuários concorrentes. Decisão de infra sem número é opinião, não engenharia.
17. Failure modes explícitos. Toda proposta de arquitetura inclui uma seção "o que quebra se isso falhar". Listar proativamente: ponto único de falha, comportamento com rede degradada, o que acontece se o serviço externo ficar indisponível, e qual é o plano de degradação elegante. Trazer a failure story antes de ser perguntado.
18. Bidirectional MCP. Quando construir capacidade interna via MCP tools, avaliar se deve ser exposta como MCP server para outros agentes. Agente que só consome ferramentas é endpoint. Agente que também serve é infraestrutura. A exposição exige access control real porque qualquer caller pode chamar a reasoning layer diretamente.
19. Validação única entre caminhos. Quando implementar fallback (modelo alternativo, degradação, retry), a função de validação do output é uma só, compartilhada por todos os caminhos. Nunca duplicar validação entre caminho primário e fallback. Se a validação vive em dois lugares, atualizar um e esquecer o outro significa entregar dois produtos diferentes com o rótulo de um.

### PostgreSQL

- Toda tabela acessível pelo cliente tem RLS habilitado e pelo menos uma política por operação (SELECT, INSERT, UPDATE, DELETE). Tabela sem RLS habilitado acessível por role com NOBYPASSRLS é brecha, não proteção.
- SQL sempre parametrizado. Fragmentos interpolados só de allowlists internas fechadas. Nunca concatenar input externo em query.
- Migrations versionadas e reversíveis. Toda migration tem um up e um down. Testar o down antes de mergear. Nunca rodar migration em produção sem backup prévio.
- Índices criados com CONCURRENTLY em tabelas com dados em produção. Índice que trava a tabela é downtime disfarçado.
- Naming: snake_case para tabelas, colunas e funções. Prefixo de domínio quando o schema tiver mais de 20 tabelas (ex: `billing_invoices`, `auth_sessions`). Chaves primárias como `id` (UUID v7 ou serial), foreign keys como `<tabela>_id`.
- Constraints no banco, não só na aplicação. NOT NULL, CHECK, UNIQUE e FK existem para pegar o que a aplicação deixar passar.
- Connection pooling obrigatório em produção (PgBouncer ou Supabase connection pooler). Aplicação nunca abre conexão direta ao Postgres em produção.
- Queries explicadas antes de mergear: rodar EXPLAIN ANALYZE em queries novas que tocam tabelas com mais de 100k rows. Seq scan em tabela grande sem filtro é red flag.
- Backups automáticos com retenção mínima de 7 dias. Testar restore periodicamente. Backup que nunca foi restaurado é esperança, não proteção.
- Roles separadas: a aplicação usa role com permissões mínimas (SELECT/INSERT/UPDATE onde precisa). Migrations usam role com DDL. Nunca rodar a aplicação como superuser.

### Docker

- Imagens baseadas em variantes slim ou alpine. Imagem de produção sem compilador, debugger ou shell interativo quando possível.
- Multi-stage build obrigatório: stage de build (com devDependencies, compilador, tsc) separado do stage de runtime (só artefatos finais e dependências de produção).
- Um processo por container. Se o serviço precisa de worker + web, são dois containers, não um entrypoint com supervisor.
- Nunca rodar como root. Definir USER no Dockerfile. Se a imagem base roda como root, criar um usuário sem privilégios.
- .dockerignore mantido: node_modules, .git, .env, testes, docs e artefatos de build local ficam fora do contexto de build.
- Health check definido no Dockerfile ou no compose. Container sem health check é caixa preta para o orquestrador.
- Variáveis de ambiente para configuração, nunca hardcoded. Segredos via secret manager ou mount, nunca como ENV no Dockerfile ou no docker-compose.yml versionado.
- Layers ordenadas do menos mutável (apt-get, COPY package.json) para o mais mutável (COPY . .). Cache de layers economiza minutos de build.
- Tag de imagem fixa em produção (nunca `latest`). Usar hash do commit ou semver. `latest` em produção é roleta.
- Logs em stdout/stderr. Nunca escrever log em arquivo dentro do container. O orquestrador coleta de stdout.

### Kubernetes

Aplicar quando o projeto usar K8s (Cloud Run com Knative conta como subset):
- Todo deployment com resource requests e limits definidos. Pod sem request é invisível para o scheduler. Pod sem limit pode derrubar o node.
- Liveness probe verifica se o processo está vivo. Readiness probe verifica se pode receber tráfego. Startup probe para apps com boot lento. Nunca usar a mesma probe para liveness e readiness.
- Pelo menos 2 réplicas em produção. Uma réplica é single point of failure durante deploy, node drain ou crash.
- Rolling update com maxSurge e maxUnavailable configurados. Nunca 100% de unavailable durante deploy.
- Pod Disruption Budget (PDB) para serviços críticos. Sem PDB, o cluster pode drenar todos os pods do serviço ao mesmo tempo durante manutenção de node.
- Secrets via Secret ou external secret operator (Vault, GCP Secret Manager). Nunca em ConfigMap, nunca em variável de ambiente visível no manifesto versionado.
- Namespace por ambiente (dev, staging, prod). Nunca misturar workloads de ambientes diferentes no mesmo namespace.
- Network policies restritivas: deny-all como default, liberar apenas o tráfego necessário entre serviços. Sem network policy, todo pod fala com todo pod.
- Imagens vêm de registry privado ou de registries públicos allowlisted. Nunca puxar imagem de registry arbitrário em produção.
- Observabilidade: métricas (Prometheus/Datadog), logs (stdout coletado por Fluentd/Vector), traces (OpenTelemetry). Pod sem observabilidade é black box em incident.
- GitOps quando possível: estado desejado do cluster declarado em Git (ArgoCD, Flux). Kubectl apply manual em produção é anti-pattern.

### Swift

Aplicar quando o projeto usar Swift/SwiftUI:
- Decodificar dados do servidor com tolerância (opcionais para qualquer campo que o servidor possa adicionar, omitir ou renomear). Nunca crashar em campos desconhecidos.
- Tornar ownership assíncrono explícito. Cancelamento, resultados obsoletos e eventos duplicados são normais. Nunca mutar estado depois que a view ou task que o controla desapareceu.
- Salvo indicação contrária do projeto, buildar em Swift 5 language mode com concurrency direcionada. Corrigir o que as build flags apontam, sem antecipar o que o Swift 6 estrito exigiria.

### Perguntas são read-only

Pergunta é pedido de resposta, não de mudança. Se a mensagem abre com "quão difícil seria", "o que você acha", "por que isso", "devemos", "é possível", "X consegue fazer Y", ou qualquer outra forma interrogativa: responder primeiro, sem editar arquivos. Se a resposta for óbvia e a mudança trivial, ainda assim responder e oferecer a mudança. Perguntar antes de fazer.

### Trabalho visual e design

Para qualquer mudança não trivial de UI, layout ou copy: construir várias variantes estáticas primeiro, apresentar para escolha e esperar a decisão antes de implementar no componente real. Skills de referência: `impeccable`, `visual-verify`, `[SKILL_DESIGN_A]`.

Evitar animações que repintem continuamente (pulse, shimmer, blur, spinners que não param). Toda animação respeita Reduce Motion.

### Raio de impacto

Nunca tocar em apps de produção, servidores live, canais de release ou dados de uso diário sem instrução explícita. Quando a tarefa for adjacente a qualquer um deles, nomear o que vai ser tocado antes de tocar.

### Pull Requests

PRs seguem as regras de `[SKILL_COMMIT_PR]` (draft por padrão, Conventional Commits). Adicionalmente:
- Descrição abre com descrição mínima e clara do problema, seguida de como foi resolvido
- Adicionar no final da descrição qual modelo e harness fez as mudanças
- Ao referenciar issue ou PR, usar hyperlink
- Ao monitorar PR: fazer poll de checks e comentários mais recentes que o último push. Verificar cada achado de bot contra o código-fonte antes de agir. Corrigir os reais e dispensar falsos positivos com justificativa escrita. Corrigir falhas de CI, distinguindo breaks reais de flakes de infra conhecidos. Se nada for novo, ficar quieto. Parar quando os review bots estiverem verdes no último commit
- Merge apenas conforme a disposição dada no pedido (merge when green, ou parar e reportar)

### Cerimônia proporcional (S / M / C)

Antes do plano, classificar esforço: **S** (simples), **M** (média), **C** (complexa).
Declarar: `Esforço: S|M|C — motivo: …`.

- Detalhe canônico: `working-style.md` → Classificação de esforço.
- **S:** two-way door, fora da blacklist, pedido inequívoco → plano de 1 linha; sem suíte integral; sem multiagente.
- **M:** comportamento local → TDD + testes do pacote.
- **C:** auth/RLS/migration/deploy/prod/money ou dúvida → rito completo.
- Blacklist e fail-closed: ver working-style. Em dúvida, **C**.
- Memória por projeto: `CLAUDE.md` / `docs/agent/REPO_MAP.md` do repo (templates em `[CONTEXT_DIR]/templates-agent/`). Em S, não reler a Camada 1 inteira se a sessão já carregou.
- Não disparar subagentes para trabalho de um passo. Delegação é para amplitude ou revisão adversarial. Em paralelo, declarar ownership de arquivos.

### Qualidade

Cada entregável pronto para uso imediato. Sem retrabalho. Se a confiança for baixa, sinalizar em vez de entregar duvidoso. Plano conforme S/M/C. Perguntar antes de adivinhar.

## Protocolo de captura rápida

Quando o usuário fornecer informação durável em conversa casual:

1. Avaliar se é estável e útil o suficiente para salvar
2. Procurar a nota existente antes de criar nova
3. Anexar a evento existente do mesmo dia quando possível
4. Preservar as palavras do usuário quando a nuance importar
5. Atualizar o menor conjunto de arquivos autoritativos
6. Atualizar resumo canônico apenas se a informação mudar o entendimento atual
7. Confirmar a captura brevemente

Para importações grandes: preservar original + resumo fundamentado na fonte.

## Protocolo de recuperação

Antes de responder pergunta sobre o usuário:

1. Ler este `agent_rules.md`
2. Buscar nos arquivos do vault (wiki/, raw/)
3. Ler resumo canônico relevante
4. Ler eventos e notas mais recentes
5. Seguir links de fonte para afirmações consequentes
6. Distinguir contexto atual, histórico, resolvido, incerto e substituído
7. Declarar incertezas e conflitos explicitamente
8. Citar caminhos de notas e datas quando a precisão importar

### Segurança

Playbook completo (copiável): `appsec-rules.md`. Resumo e CI/CD também em `working-style.md` § Segurança de aplicações. Skills de referência: `[SKILL_SECURITY_SQUAD]`, `[AGENT_TEAM]:appsec`, `[SKILL_CODE_REVIEW]` (categoria segurança).

Resumo para qualquer agente:
1. Todo repositório com SECURITY.md, secret scanning, Dependabot, CodeQL e branch protection
2. Segredos nunca em código/frontend/log. Representar como [REDACTED]
3. Autorização decidida no servidor. Checks de interface não contam
4. RLS em toda tabela acessível pelo cliente. SQL parametrizado
5. Inputs validados server-side. Uploads com magic bytes e nome gerado pelo servidor
6. Rate limit separado pré-auth e pós-auth
7. OAuth 2.1 com PKCE. Redirect URIs com allowlist exata
8. Deploy com suíte integral → canário → smoke → promoção explícita
9. Achados classificados como OK | ACHADO | NÃO APLICÁVEL | NÃO VERIFICADO
10. Só "APROVADO" se zero achados bloqueantes + evidência verificável

## Ponteiros

- Vault Obsidian operacional: `[CONTEXT_DIR]/[YOUR_NAME]/` ([SECONDARY_MACHINE]: `[CONTEXT_DIR]/[YOUR_NAME]`)
- Vault Obsidian Jurídico (segundo cérebro): `[DOMAIN_VAULT]` (atalho `[DOMAIN_VAULT]`)
- MOCs: `[YOUR_NAME]/wiki/00-indices/`
- Memória persistente Claude: `.auto-memory/MEMORY.md`
- Perguntas abertas: `[YOUR_NAME]/wiki/00-indices/open_questions.md`
- Changelog estrutural: `_CHANGELOG.md`

---
*Este arquivo é a porta de entrada para qualquer IA. Atualize quando mudar regras fundamentais. Registre no `_CHANGELOG.md`.*
