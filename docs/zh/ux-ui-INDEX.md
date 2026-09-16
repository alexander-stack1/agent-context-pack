# ux-ui-INDEX.md

> **公开模板。** 个人标识、律所、产品、邮箱与路径已替换为占位符。见 `PLACEHOLDERS.md`。请勿重新引入真实数据。

> 面向智能体的正典 UX/UI 索引。路由 WEB 与 MOBILE 及共享规则。
> Camada 1 / 设计。更新：07/09/2026

---

## 文件（按此顺序阅读）

| 顺序 | 文件 | 角色 |
|---:|---------|------|
| 1 | `ux-ui-criteria.md` | MUST/MUST-NOT 原则（Norman、Krug、Yablonski、Refactoring UI、Johnson）+ 清单 §7 |
| 2 | `ux-ui-INDEX.md` | 本文件：路由 + 60-30-10 配色 |
| 3a | `ux-ui-web-landing.md` | **WEB** landing 的子规则与 STEPS 0–14 |
| 3b | `ux-ui-mobile.md` | **MOBILE**（landing / app / chat）的子规则与 STEPS |

## 精简请求菜单

阅读 **`ux-ui-REQUESTS.md`** 以了解该要求什么。PT 技能：`[SKILL_UI_PLAN]`、`[SKILL_UI_LANDING]`、`[SKILL_UI_REVIEW]`、`[SKILL_UI_REFACTOR]`、`[SKILL_UI_POLISH]`、`[SKILL_UI_PROVE]`、`[SKILL_UI_REDESIGN]`。它们封装这些文件 + impeccable。

Grok Bot 技能：[ux-ui-criteria](sand-workflow:ux-ui-criteria)（当已安装在机队中时）。
互补插件（工艺/抛光）：**impeccable** — 仅在上述失败关闭标准**之后**。

---

## STEP R0 — 路由（智能体的第一个动作）

设计前用一行回答：

```
PLATFORM: web | mobile | both
SURFACE: landing | app-shell | chat | other
MODE: Persuade | Operate | Read | Experience
FILES: [list that will be read]
```

规则：
- `landing` + `web` → criteria + INDEX + **web-landing**
- `landing` + `mobile` 或 `both` → criteria + INDEX + web-landing + **mobile**（A 节）
- `app-shell` mobile → criteria + INDEX + **mobile**（B 节）
- `chat` → criteria + INDEX + **mobile**（C 节）
- 其他 Operate UI → criteria + INDEX；按 mobile §D 表区分 mobile 与 web

无 R0 → 交付无效。

---

## 共享配色 — 60-30-10 规则（MUST）

| 切片 | 角色 | 用途 |
|------:|------|-----|
| **60%** | 主色 / 背景 | 画布（例如白或产品中性背景） |
| **30%** | 次色 / 文字与支持 | 文字、中性图标、次级表面 |
| **10%** | 强调 / CTA | 主按钮、强调链接、需注意的状态 |

**子规则**
- C-1: 强调色**不**涂满整块背景或每个装饰图标。
- C-2: 错误/成功/警告是独立语义；若与 CTA 冲突，不要把全部 10% 强调色花在它们上。
- C-3: 文字（30%）在背景（60%）上对比须可读；强调（10%）在按钮背景上有对比。
- C-4: 有疑虑时减色，不要增加强调色。

交付时声明：
```
60: [token/color]
30: [token/color]
10: [token/color] → used in: [listed CTAs]
```

---

## 智能体执行顺序（摘要）

1. **R0**（本文件）
2. 阅读 `ux-ui-criteria.md`（MUST/MUST-NOT）
3. 应用 **60-30-10**
4. 按顺序遵循 `ux-ui-web-landing.md` 和/或 `ux-ui-mobile.md` 中的编号 STEPS；在 Hero/结构之前不要跳到视觉工艺
5. 填写所用文件清单 + criteria §7 清单
6. 仅当请求抛光/加粗/排版时：再用 **impeccable** 技能

---

## 短触发器（粘贴到提示）

```
Follow [CONTEXT_DIR]/ux-ui-INDEX.md (R0 + 60-30-10) and the web/mobile files that R0 indicates.
Also ux-ui-criteria.md. Deliver with checklists. Fail-closed. Do not invent social proof.
```

---

## 与宣言的集成

在下次结构审阅时纳入 Camada 1（或 Camada 2 tech/design）：
- `ux-ui-criteria.md`
- `ux-ui-INDEX.md`
- `ux-ui-web-landing.md`
- `ux-ui-mobile.md`

Mac 在线时复制到 `[HOME]/Desktop/[CONTEXT_DIR]/`（正典 iCloud 来源）。

---
*不要再分发著作 PDF。面向 AI 的操作标准。*
