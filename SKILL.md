---
name: aon
description: Search AON offers via MCP tool. Use when the user wants to find, compare, or explore products/services (electronics, SaaS, education, travel, finance).
argument-hint: <query in any language>
---

# AON Offer Search Skill

用户通过 `/aon <需求>` 搜索 AgentOffer 网络中的真实 offer。

## 前置检查（每次执行必须先做）

在执行任何操作之前，先检查 `aon_search_offers` 工具是否可用（通过 ToolSearch 或检查可用工具列表）。

**如果工具不可用**，说明 MCP server 未安装。请告知用户：

> AON MCP 服务尚未安装。请运行以下命令安装，然后重启你的 MCP 宿主（如 Claude Code、Claude Desktop、Cursor 等）：
>
> ```
> uvx --from aon-demo-skill-python aon-demo-skill --install --global
> ```

然后停止执行，不要继续后续流程。

**如果工具可用**，继续执行下面的流程。

## 执行流程

1. **理解用户需求**：从 `$ARGUMENTS` 中提取意图
2. **判断是否需要澄清**：如果需求模糊，先调用 `aon_get_category_schema` 获取该品类的决策因子，向用户提出 1-2 个关键澄清问题
3. **搜索 offer**：调用 `aon_search_offers` 搜索
4. **展示结果**：以清晰的对比格式呈现

## 工具调用规范

### 搜索 offer

调用 `aon_search_offers`，参数提取规则：

| 参数 | 提取方式 |
|------|----------|
| `user_summary` | **必填**。一句话概括用户偏好（英文） |
| `query` | 用户原文 |
| `keywords` | 从需求中提取英文关键词数组 |
| `category` | 识别品类：`electronics` / `software_saas` / `education` / `travel_hospitality` / `financial_service` |
| `action` | 判断阶段：`discover`（随便看看）/ `compare`（对比选择）/ `purchase`（准备买） |
| `budget_max` | 如用户提到预算，提取数字 |
| `features` | 提取期望特性（英文） |
| `limit` | 默认 5，用户要求更多时调大 |

### 获取品类 schema

调用 `aon_get_category_schema`：
- 传 `category` = 具体品类名，获取该品类的决策因子
- 传 `category` = `"all"`，列出所有支持的品类

注意：当前 schema helper 只内置 `electronics`、`software_saas`、`education` 三类。如果用户需求落在 `travel_hospitality` 或 `financial_service`，不要先卡在 schema helper，直接调用 `aon_search_offers`。

## 结果展示格式

搜索到结果后，以用户语言展示：
- 每个 offer 一个段落，包含名称、价格、核心卖点、链接
- 如有多个结果，简要对比差异
- 末尾附一句总结推荐

## 用户输入

$ARGUMENTS