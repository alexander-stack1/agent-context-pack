# Placeholder legend

Replace these tokens before using the pack in production. Keep a **private** overlay for real values.

| Placeholder | Meaning |
|---|---|
| `[YOUR_NAME]` | Your name |
| `[YOUR_HANDLE]` | Public social / X handle |
| `[YOUR_FIRM]` | Firm, company, or studio |
| `[PARTNER_NAME]` | Partner or co-founder |
| `[YOUR_UNIVERSITY]` | University or research affiliation |
| `[YOU@EXAMPLE.COM]` | Personal email |
| `[TEAM@EXAMPLE.COM]` | Shared team inbox |
| `[FIRM_DOMAIN]` | Company domain |
| `[EMAIL]` | Any other email |
| `[YOUR_GITHUB]` | GitHub user or org |
| `[CONTEXT_REPO]` | Private context git repo name |
| `[HOME]` | Home directory |
| `[CONTEXT_DIR]` | This context pack on disk |
| `[OPS_VAULT]` | Operational notes vault (Karpathy-style) |
| `[DOMAIN_VAULT]` | Domain second brain for agents |
| `[PRODUCT_A]`…`[PRODUCT_K]` | Your products / repos |
| `[ORG_A]` / `[ORG_B]` | External orgs (examples) |
| `[RAG_STACK]` | Retrieval / RAG stack name |
| `[EXAM_TRACK_A]` / `[EXAM_TRACK_B]` | Optional exam or study tracks |
| `[BRAND_KIT_DIR]` | Path to brand kit assets |
| `[FIRM_ASSETS]` | Letterhead / logo folder |
| `[PRIMARY_MACHINE]` / `[SECONDARY_MACHINE]` | Machine labels |
| `[LOYALTY_A]`…`[LOYALTY_F]` | Loyalty programs (if ever needed) |
| `[CHANNEL_A]` / `[CHANNEL_B]` | Writing channels |
| `[RUNTIME]` / `[APP_FRAMEWORK]` / `[DATA_STORE]` / `[HOSTING]` | Stack placeholders |
| `[TEAM]` / `[ENTRYPOINT]` / `[ADMIN_ENTRY]` | Repo map placeholders |
| `[SKILL_SCOUT]` / `[SKILL_PRODUCT_PARTNER]` / `[SKILL_CONCISE_MODE]` | Optional custom skills |
| `[REDACTED]` | Stand-in for any secret value |

Never commit real secrets, client names, case numbers, or credentials to a public fork.

## Added in the second scrub pass

| Placeholder | Meaning |
|---|---|
| `[YOUR_COMPANY]` | Your tech / product company (distinct from `[YOUR_FIRM]`) |
| `[AGENT_TEAM]` | Your custom multi-agent team plugin (`[AGENT_TEAM]:appsec`, `:dba`, `:devops` are its roles) |
| `[YOUR_ROLE]` / `[PRACTICE_AREA]` / `[YOUR_INDUSTRY]` | Profession, practice area, and industry |
| `[FRONT_A]` / `[FRONT_B]` / `[FRONT_C]` | Your three professional fronts |
| `[YOUR_AUDIENCE]` / `[SECONDARY_AUDIENCE]` | Who you serve |
| `[ACADEMIC_TITLE]` / `[ACADEMIC_STATUS]` / `[ACADEMIC_FIELD]` | Academic degree, status, and research line |
| `[CITY_A]` / `[CITY_B]` | Office locations |
| `[TEAM_SIZE]` / `[N]` | Head count and any other count |
| `[AMOUNT_A]` / `[AMOUNT_B]` / `[TIER_1]` / `[TIER_2]` | Money figures and MRR tiers |
| `[DAILY_TASK_A..C]` / `[QUALITY_REF_A..B]` | Typical tasks and portfolio references |
| `[PRODUCT_A_DESCRIPTION]` / `[PRODUCT_DESIGN_SYSTEM]` / `[PRODUCT_I]` | Product one-liner, design system name, extra product |
| `[COMPANY_PRIMARY]` / `[COMPANY_ACCENT]` / `[COMPANY_ACTION]` / `[COMPANY_AI_COLOR]` | Company palette (hex) |
| `[COMPANY_FONT_HEADING]` / `[COMPANY_FONT_BODY]` | Company typography |
| `[PRODUCT_PRIMARY]` / `[PRODUCT_ACCENT]` / `[PRODUCT_FONT_HEADING]` / `[PRODUCT_FONT_BODY]` | Product palette and typography |
| `[PERSONAL_FONT_A..C]` | Personal-brand typography |
| `[KIT_TEMPLATE_A..E]` | Brand-kit post templates |
| `[LETTERHEAD_CMD]` / `[LETTERHEAD_FILE]` / `[LOGO_FILE]` | Letterhead command and firm assets |
| `[DOMAIN_MOC]` | Activator MOC note of the domain vault |
| `[THESIS_REF]` / `[CASE_REF]` | Thesis pre-project and example case citation |
| `[BOOK_AUTHOR]` / `[SKILL_DOMAIN_BOOK]` | Domain textbook converted into a skill |
| `[TOOL_MEDIA]` | Personal media-download tool |
| `[TASK_MORNING_BRIEF]` / `[TASK_NIGHTLY_REVIEW]` / `[TASK_LAW_MONITOR]` / `[TASK_EXAM_MONITOR]` / `[TASK_COMPETITOR_MONITOR]` / `[TASK_ON_DEMAND_A..G]` | Scheduled personal subagents |
| `[SKILL_CASE_SUMMARY]` `[SKILL_DOMAIN_DRAFTING]` `[SKILL_SETTLEMENT_CALC]` `[SKILL_EXPERT_REPORT]` `[SKILL_CALC_CHALLENGE]` `[SKILL_APPEALS]` `[SKILL_COUNTER_APPEAL]` `[SKILL_ENFORCEMENT]` `[SKILL_CASELAW_SEARCH]` `[SKILL_CASELAW_SEARCH_B]` `[SKILL_LAW_CHECK]` | Custom domain (law) skills |
| `[SKILL_ACADEMIC_REVIEW]` `[SKILL_ACADEMIC_ADVISOR]` `[SKILL_STUDY_DOC]` `[SKILL_COURT_ANALYSIS]` `[SKILL_EXAM_STUDY]` | Custom academic skills |
| `[SKILL_MARKET_INTEL]` `[SKILL_PRD]` `[SKILL_ISSUES]` `[SKILL_TRIAGE]` `[SKILL_RETRIEVAL_EVAL]` | Custom product skills |
| `[SKILL_CODE_REVIEW]` `[SKILL_E2E_ANALYSIS]` `[SKILL_COMMIT_PR]` `[SKILL_SECURITY_SQUAD]` | Custom engineering skills |
| `[SKILL_BRAND_COPY]` `[SKILL_NO_TROPES]` `[SKILL_SYNTHESIZE]` `[SKILL_INTERVIEW]` `[SKILL_INTERVIEW_CTX]` `[SKILL_TRANSLATE]` `[SKILL_CREATE_SKILL]` | Custom writing / productivity skills |
| `[SKILL_UI_PLAN]` `[SKILL_UI_LANDING]` `[SKILL_UI_REVIEW]` `[SKILL_UI_REFACTOR]` `[SKILL_UI_POLISH]` `[SKILL_UI_PROVE]` `[SKILL_UI_REDESIGN]` `[SKILL_DESIGN_A]` `[SKILL_DESIGN_B]` | Custom UI / design skills |

Public third-party skills (docx, xlsx, pptx, pdf, obsidian-*, Google Cloud skills, tdd, diagnose, review, archify, handoff, book-to-skill, skill-creator, impeccable, etc.) are kept by name because they are not personal.
