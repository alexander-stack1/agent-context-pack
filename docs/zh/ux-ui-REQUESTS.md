# ux-ui-REQUESTS.md

> **公开模板。** 个人标识、律所、产品、邮箱与路径已替换为占位符。见 `PLACEHOLDERS.md`。请勿重新引入真实数据。

> 精简菜单：雇用 UI 或重构时该要求什么。
> 更新：07/09/2026
> 正典闸门在 `ux-ui-INDEX.md` + `ux-ui-criteria.md`（+ web/mobile）。工艺经底层 **impeccable** / **frontend-design** — 你不必记住英文名。

---

## 这样要求（7 项技能）

| 你想要… | 要求 / 技能 | 封装内容 |
|------------|--------------|-----------|
| 编码**前**规划屏幕 | **`[SKILL_UI_PLAN]`** | R0 + 闸门 + impeccable `shape`（若要求则含变体） |
| Landing / 营销 web+mobile | **`[SKILL_UI_LANDING]`** | web-landing + mobile 闸门 + Persuade 模式 |
| 审阅 UX、无障碍、响应式 | **`[SKILL_UI_REVIEW]`** | 闸门清单 + impeccable `critique` + `audit` |
| 视觉重构（层级、字体、颜色、mobile↔web） | **`[SKILL_UI_REFACTOR]`** | 闸门 + 按需 `distill` / `layout` / `typeset` / `adapt` / `colorize` / `clarify` |
| 抛光并加固以发版 | **`[SKILL_UI_POLISH]`** | `polish` + `harden` + `[SKILL_UI_PROVE]` |
| 证明屏幕正确 | **`[SKILL_UI_PROVE]`** | `visual-verify`（截图对照参考） |
| [PRODUCT_A] 的增量重设计 | **`[SKILL_UI_REDESIGN]`** | [PRODUCT_A] briefing + 闸门（不改品牌） |

基础技能（很少单独要求）：`ux-ui-criteria` — 仅失败关闭闸门。

---

## 现成短语

- 「对 [屏幕/流程] 运行 **[SKILL_UI_PLAN]**。」
- 「为 [产品] 做 **[SKILL_UI_LANDING]**，web 与 mobile。」
- 「对本页 / 本 PR 做 **[SKILL_UI_REVIEW]**。」
- 「**[SKILL_UI_REFACTOR]**：杂乱 / 难读 / 在 mobile 上坏了。」
- 「合并前 **[SKILL_UI_POLISH]**。」
- 「对照 mock / 姊妹页做 **[SKILL_UI_PROVE]**。」
- 「**[SKILL_UI_REDESIGN]** 层 [Chrome|Panel|Listings|Forms]。」

---

## 不要再这样要求（冗余 / 错误）

| 旧做法 | 原因 | 改用 |
|--------|---------|------------|
| 松散英文 impeccable 命令（`polish`、`bolder`…） | PT 菜单已选取引擎 | 表中技能 |
| 直接用 `frontend-design` 插件 | 与 impeccable 工艺重叠 | `[SKILL_UI_PLAN]` / `[SKILL_UI_LANDING]` / `[SKILL_UI_REFACTOR]` |
| `ui-design` 市场（数十技能） | 噪声；闸门+impeccable 覆盖流程 | 上表菜单 |
| `design-an-interface` | 是 API/模块，**不是** UI | （本菜单外） |
| `[SKILL_DESIGN_A]`、`[SKILL_DESIGN_B]` | 在 stack 中被引用，Claude 中**无文件夹** | 从 stack 移除 |
| `asc-app-create-ui` | App Store Connect 自动化，非设计 | （外部） |
| `product-partner` | 完整产品周期 | 仅当推出产品，非点状 UI |
| `meigen-ai-design` | 图像生成 | 仅当你需要插画资产 |

官方插件**仍作为引擎安装**；入口是本菜单。

---

## 本菜单任一技能的固定顺序

1. R0（`ux-ui-INDEX.md`）
2. 闸门（`ux-ui-criteria.md` + 适用时 web/mobile）
3. 按技能的 Impeccable / 核验引擎
4. 交付带清单；不编造社会证明
