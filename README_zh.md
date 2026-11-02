[English](README.md) | [한국어](README_ko.md) | **中文**

<div align="center">

# NeoSQL

**集 ERD 设计、数据标准化、SQL 执行、AI 辅助分析、模式变更管理与仪表盘于一体的数据库开发平台**

[![License](https://img.shields.io/badge/license-Commercial-blue?style=for-the-badge)](https://neosql.unvus.com/)
[![Platforms](https://img.shields.io/badge/platforms-Windows%20%7C%20macOS%20%7C%20Web-lightgrey?style=for-the-badge)](#使用环境)
[![Projects](https://img.shields.io/badge/projects-Local%20%7C%20Account-success?style=for-the-badge)](#选择项目类型)

[官网](https://neosql.unvus.com/) &middot; [下载](https://neosql.unvus.com/) &middot; [NeoSQL MCP](https://github.com/unvus/neosql-mcp) &middot; [问题与反馈](#问题与反馈)

</div>

---

文档内容截至：**2026-11-02**

## 概述

NeoSQL 将理解数据库结构、设计模式和处理实际数据的工作整合到同一环境中。您可以将现有数据库可视化为 ERD，管理表和数据库对象，编辑 SQL 查询结果，或将查询构建为仪表盘。

**数据字典与域**直接连接 ERD 设计界面，从逻辑名称生成标准物理名称，并一致地应用列的数据类型和属性。标准不仅保存在独立文档中，还可用于实际表和列的设计过程。

内置 **AI Assistant** 基于实际模式和执行上下文，辅助完成自然语言生成 SQL、数据查询与分析、查询调优和错误诊断。通过 **MCP（Model Context Protocol，模型上下文协议）**，外部 AI 开发工具可以使用 NeoSQL 的数据库工具并进行 ERD 操作。

NeoSQL 提供 Windows、macOS 桌面应用及 Web 应用。在桌面端，您可以**无需注册或登录，直接使用本地项目开始工作**。使用账号项目则可以与团队成员共享项目并同步工作内容。

## 主要功能

### ERD 设计与模式变更管理

- 读取实际数据库的表、列、键和关系，通过逆向工程构建 ERD
- 设计表和关系，编辑列、索引、外键和约束
- 跟踪 ERD 变更，预览并应用适用于各 DBMS 的 DDL
- 比较同一 DBMS 下不同模式中的表、视图等结构差异，并审查变更 DDL
- 导出 ERD 图片，通过模型库共享模型

### 基于数据字典与域的数据标准化

为减少同一含义的列在不同表中使用不同名称和类型的问题，NeoSQL 提供**管理标准词与缩写的数据字典**和**定义列属性的域包**。您可以为每个数据库连接指定标准，并在 ERD 中直接应用。

**从逻辑名称生成标准物理名称**

- 管理标准词的逻辑名称和英文缩写，同时定义同义词、禁用词、反义词和相关词
- 支持将逻辑名称拆分为已登记单词并组合缩写的**组合型字典**，以及精确匹配已登记名称的**完整术语型字典**
- 在 ERD 中输入表或列的逻辑名称时，按字典规则生成物理名称
- 为当前连接添加字典中缺少的单词，继续完成设计；已登记反义词时可创建配对列
- 在 ERD 中切换逻辑名称与物理名称显示，让业务人员和开发者审查同一模型

**通过域统一列属性**

- 将类型、长度、小数位数、是否允许 NULL、默认值、自增等可复用列属性定义为域
- 将单词与域关联，根据列逻辑名称的末尾单词推荐或应用域
- 只有一个候选时自动指定，有多个候选时由用户选择
- 使用各 DBMS 的类型映射，应用适合目标数据库的物理类型
- 修改域时预览其与关联列的差异，经审查后另行应用

例如，在字典中登记 `주문（订单）→ ORD` 和 `일시（日期时间）→ DTM`，并为日期时间单词关联日期时间域，即可从列逻辑名称 `주문일시` 生成物理名称 `ord_dtm`，并应用域的类型与属性。实际物理名称和类型取决于所选字典、命名设置及 DBMS 类型映射。

**共享公共标准，管理项目差异**

- 在 Store 中浏览、安装数据字典和域包，或自行创建，并通过 Excel 导入和导出
- 管理账号资源的成员与权限，让团队共同编辑和共享标准
- 为每个连接指定已发布的特定版本，审查新版变更后再升级
- 无需修改原始资源，即可仅为当前连接添加、修改或隐藏单词与域
- 查看相对于原始资源的新增、修改和删除状态，恢复原始内容，或将连接当前使用的标准克隆为新资源

本地项目也可使用官方包以及设备中保存的字典和域。账号资源的发布与共享和设备本地资源的管理有所区别；修改域不会自动改变实际数据库模式。审查设计变更后，可以继续通过 DDL 应用变更。

### SQL 编辑器与数据操作

- 语法高亮、SQL 格式化、基于模式的自动补全，以及基于执行历史的行内建议
- 每个标签页使用独立数据库会话，支持搜索和复用 SQL 执行历史
- 在结果网格中查询、修改和删除数据，导入和导出数据
- 支持 Auto Commit 与 Manual Commit 模式，显示未提交事务状态
- 查看执行计划，借助 AI 改进查询并分析错误

> 结果编辑、DDL 应用及 Commit/Rollback 等能力取决于 DBMS 和查询的支持范围。部分 DBMS 会隐式提交 DDL，或不支持通过事务回滚 DDL。

### 内置 AI Assistant 与外部 MCP 集成

- 使用自然语言编写 SQL，并基于实际查询结果分析数据
- 参考表、列、关系和执行计划进行查询调优与 SQL 错误诊断
- 在 AI 对话中创建和修改 ERD 及表设计
- 连接 OpenAI、Anthropic、Google Gemini、Ollama 等 AI 服务提供商
- 连接自托管 Ollama 服务器或 Ollama Cloud，查看服务器可用模型
- 使用保存在账号或设备上的服务提供商密钥，查看 AI 调用与 Token 用量
- 通过外部 MCP 客户端使用元数据查询、SQL 执行和 ERD 设计工具
- 通过全局或项目级 MCP 配置连接当前项目或指定项目

您可以设置 AI 可访问的连接和模式，以及数据查询与变更策略，并根据策略在执行前确认 SQL 和目标并批准操作。账号项目还支持角色权限、敏感列脱敏和 DDL 审批。

无需在 MCP 客户端配置中直接输入数据库密码。请注意，根据设置和批准范围，AI 功能可能会将模式信息或查询结果发送给您选择的 AI 服务提供商。

### 基于查询的仪表盘

- 将 SELECT 结果展示为数值卡片、表格及柱状图、折线图、面积图、饼图、散点图等图表
- 将 SQL 编辑器中的查询转换为仪表盘组件
- 调整组件位置与大小，设置查询时间范围和自动刷新间隔
- 使用针对不同 DBMS 的监控预设，查看会话、锁、性能、存储和模式质量等信息
- 按连接数据库的时区查询时间范围，并可选择按用户时区显示

本地项目和账号项目均可使用仪表盘。自动刷新仅在仪表盘标签页可见时运行，预设的可用性取决于 DBMS 和连接权限。

### DBMS 专属对象与详细管理

- 在各 DBMS 支持范围内查看和管理视图、索引、序列、例程、用户、权限等对象
- 支持 PostgreSQL RLS 策略模拟、Supabase 集成、空间数据和用户定义类型处理
- 选择 Databricks SQL Warehouse，查看 Delta 表属性和版本历史，并恢复表版本

### 团队协作与项目同步

账号项目支持邀请团队成员、设置角色权限，并同步 ERD 和项目设置等共享工作数据。您可以检测其他用户的变更，在工作界面中重新加载并审查。

## 使用环境

### 桌面端与 Web 端

| 类别 | 桌面端 | Web 应用 |
|------|--------|----------|
| 运行环境 | Windows、macOS（Apple Silicon 与 Intel） | 浏览器 |
| 登录 | 可无需账号开始使用 | 需要登录 |
| 数据库连接路径 | 从运行应用的电脑连接 | 从服务端连接 |
| 内网及本地数据库 | 连接电脑可访问的数据库 | 仅连接服务端可访问的数据库 |
| 本地项目 | 支持 | 不支持 |
| 账号项目与团队协作 | 支持 | 支持 |
| 通过 MCP 连接外部 AI 工具 | 支持 | 不支持 |
| AI 服务提供商密钥 | 设备本地密钥与账号密钥 | 账号密钥 |

> 对于仅能从内网或开发电脑访问的数据库，请使用桌面应用。

### 选择项目类型

| 类别 | 本地项目 | 账号项目 |
|------|----------|----------|
| 使用条件 | 桌面端，登录可选 | 桌面端或 Web 端，需要登录 |
| 项目数据 | 保存在当前设备 | 基于账号存储与同步 |
| 主要用途 | 个人工作、内网及隔离网络中的数据库操作 | 团队共享与跨设备工作 |
| ERD、SQL、仪表盘、数据字典 | 支持 | 支持 |
| 内置 AI | 需要设备可访问的 AI 服务提供商 | 需要可访问的 AI 服务提供商 |
| 团队成员、角色权限、DDL 审批、敏感列脱敏 | 不支持 | 支持 |

本地项目的基本数据库操作无需账号登录。在没有互联网的环境中，也可以操作设备可访问的数据库；AI 则需要该环境中可访问的服务提供商。下载公开 Store 资源和更新等在线功能需要网络连接。

不支持在本地项目与账号项目之间转换项目类型。

## 支持的数据库

| 数据库 | |
|--------|:-:|
| MySQL | ![MySQL](https://img.shields.io/badge/MySQL-4479A1?style=flat-square&logo=mysql&logoColor=white) |
| MariaDB | ![MariaDB](https://img.shields.io/badge/MariaDB-003545?style=flat-square&logo=mariadb&logoColor=white) |
| PostgreSQL | ![PostgreSQL](https://img.shields.io/badge/PostgreSQL-4169E1?style=flat-square&logo=postgresql&logoColor=white) |
| Oracle | ![Oracle](https://img.shields.io/badge/Oracle-F80000?style=flat-square&logo=oracle&logoColor=white) |
| SQL Server | ![SQL Server](https://img.shields.io/badge/SQL%20Server-CC2927?style=flat-square&logo=microsoftsqlserver&logoColor=white) |
| SQLite | ![SQLite](https://img.shields.io/badge/SQLite-003B57?style=flat-square&logo=sqlite&logoColor=white) |
| H2 | ![H2](https://img.shields.io/badge/H2-0000BB?style=flat-square) |
| Databricks | ![Databricks](https://img.shields.io/badge/Databricks-FF3621?style=flat-square&logo=databricks&logoColor=white) |
| Snowflake | ![Snowflake](https://img.shields.io/badge/Snowflake-29B5E8?style=flat-square&logo=snowflake&logoColor=white) |
| Google BigQuery | ![Google BigQuery](https://img.shields.io/badge/Google%20BigQuery-669DF6?style=flat-square&logo=googlebigquery&logoColor=white) |


各 DBMS 支持的对象、DDL、结果编辑和管理功能范围有所不同。NeoSQL 也提供针对基于 PostgreSQL 的 Supabase 的集成功能。

## 主要使用场景

- **理解现有系统**：将旧系统数据库的表和关系可视化为 ERD，并借助 AI 分析结构
- **数据标准化**：通过公共字典与域统一逻辑名称、物理名称和列属性，管理项目例外与版本
- **审查设计与变更**：确认域变更对列的影响，通过 DDL 审查 ERD 变更和模式差异
- **日常 SQL 开发**：在同一工作区编写和执行查询、编辑结果并复用历史记录
- **数据分析与监控**：使用自然语言探索数据，将重复查询构建为仪表盘
- **连接 AI 开发工具**：通过 MCP 让外部智能体使用 NeoSQL 的数据库上下文和执行工具
- **个人工作与团队协作**：从本地项目开始，或在账号项目中与团队成员共享模型和设置

## 下载

请通过 [NeoSQL 官网](https://neosql.unvus.com/)的下载按钮获取适用于您操作系统的最新桌面安装包。

| 平台 | 安装文件 |
|------|----------|
| Windows | `.exe` |
| macOS — Apple Silicon / Intel | `.dmg` |

Web 应用及产品信息请见[官网](https://neosql.unvus.com/)。

## 问题与反馈

错误报告、功能请求及使用问题请提交至本仓库的 [Issues](https://github.com/unvus/neosql/issues)。您也可以通过应用内的错误报告功能，在审查后附上截图和诊断信息提交报告，无需登录。

提交问题时，请注明应用版本、使用环境（桌面端/Web、操作系统）、数据库类型和复现步骤。请勿包含密码、API Key 或个人信息等敏感内容。

## 许可证

NeoSQL 采用商业许可证。使用范围、再分发权限、维护范围及部署条件以单独签订的协议或供应政策为准。

有关许可、产品引入、技术支持及企业部署的咨询，请访问[官网](https://neosql.unvus.com/)。
