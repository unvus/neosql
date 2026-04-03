[한국어](README_ko.md) | [English](README.md) | **中文**

<div align="center">

# NeoSQL

**支持 ERD 设计、表管理、SQL 编辑、Schema 变更追踪和源代码自动生成的一站式数据库开发平台**

[![License](https://img.shields.io/badge/license-Commercial-blue?style=for-the-badge)](https://neosql.unvus.com/)
[![Platforms](https://img.shields.io/badge/platforms-Windows%20%7C%20macOS%20%7C%20Web-lightgrey?style=for-the-badge)](#使用环境)
[![Deployment](https://img.shields.io/badge/deployment-Desktop%20%7C%20Web%20%7C%20Offline-success?style=for-the-badge)](#各环境功能对比)

[官网](https://neosql.unvus.com/) &middot; [下载](#-下载) &middot; [问题与反馈](#-问题与反馈)

</div>

---

## 概述

NeoSQL 不仅是一个简单的 ERD 绘制工具，它将数据库元数据查询、ERD 设计与可视化、表详细管理、SQL 编辑、Schema 变更追踪、基于模板的源代码生成整合到一个统一的工作流程中，是一个全方位的数据库开发平台。

同时支持 Web、桌面和离线环境，可以灵活适配从隔离网络到基于在线同步的协作环境，满足组织的安全策略和运营方式。此外，通过支持 MCP（Model Context Protocol）标准，可以在不直接暴露数据库连接信息的前提下，与 AI 开发工具进行集成。

## :sparkles: NeoSQL 提供的价值

- :white_check_mark: 基于真实数据库元数据，标准化开发产出物。
- :white_check_mark: 同时处理 ERD 和实际 Schema，缩小设计与实现之间的差距。
- :white_check_mark: 表编辑、SQL 执行、代码生成在一个工具中连续完成。
- :white_check_mark: 自动化重复性代码和后端产出物的生成，提高开发效率。
- :white_check_mark: 追踪 Schema 变更，系统化后续 DDL 工作流程。
- :white_check_mark: 在与 AI 开发工具集成的同时，保持数据库连接信息的安全性。
- :white_check_mark: 在一个产品体系内支持 Web、桌面、本地部署和隔离网络环境。

## :rocket: 主要功能

| | 功能 |
|:---:|---------|
| :mag: | 查询所支持数据库的表、列、键、关系元数据 |
| :art: | 基于真实 Schema 构建和可视化 ERD |
| :pencil2: | 以列、索引、外键、约束为核心的表详细编辑 |
| :keyboard: | 包含自动补全、语法高亮和结果查看的 SQL 编辑器 |
| :gear: | 基于 Velocity 模板的源代码生成 |
| :file_folder: | 桌面端直接生成文件，Web 端支持 ZIP 下载 |
| :wrench: | 支持针对各 DBMS 特性的 DDL 生成流程 |
| :robot: | 基于 MCP 的 AI 工具集成及基于项目 ID 的安全访问 |
| :shield: | DML 执行后支持手动 Commit/Rollback 审查流程 |
| :cloud: | 支持离线文件存储和在线同步方式 |

## :star2: 产品特性

### :art: ERD 及 Schema 可视化

NeoSQL 提供基于 ERD 的工作环境，可以直观地查看和审查表及其关系。不仅适用于新设计，还适用于对现有数据库进行逆向工程、理解结构和评估变更影响。

### :building_construction: 企业级部署支持

NeoSQL 的设计以企业内部部署和运营为前提。可以广泛支持桌面安装部署、Web 部署、本地部署环境以及隔离网络环境。

### :handshake: 协同编辑与协作同步

在 NeoSQL 的 Online 模式下，多个用户可以通过 Sync Server 和 PouchDB/CouchDB 同步架构共享同一项目。ERD、表配置、连接信息、转换设置等协作数据在设备间同步，其他用户的变更也可以在工作界面中检测到，并可以重新加载或审查。

### :lock: AI 集成与安全执行流程

NeoSQL 支持 MCP（Model Context Protocol）标准，可与 Claude、Cursor、VS Code 等 AI 开发工具集成。数据库连接信息不直接包含在 AI 配置文件中，而是通过项目 ID 进行引用。DML 执行结果也不会自动提交，用户可以在 SQL 编辑器中自行决定 Commit 或 Rollback。

## :computer: 使用环境

NeoSQL 提供三种使用方式，根据用户的网络环境和数据库访问条件，适合的方式有所不同。

### 应该选择哪种环境？

| 场景 | 推荐环境 |
|------|:--------:|
| 需要直接连接内部数据库，并需要团队协作 | **Desktop (Online)** |
| 互联网/外部访问被限制的隔离网络环境 | **Desktop (Offline)** |
| 仅使用公有数据库（云数据库等），希望无需安装直接使用 | **Web App** |

> [!NOTE]
> 大多数内部数据库因防火墙策略仅允许从开发者 PC 访问。此时必须使用 **Desktop 应用**。Web App 仅可连接公网可访问的数据库。

### 各环境功能对比

| 功能 | Web App | Desktop (Online) | Desktop (Offline) |
|------|:-------:|:-----------------:|:-----------------:|
| **是否需要安装** | 无需安装（浏览器） | Windows / macOS | Windows / macOS |
| **内部数据库直连** | - | O | O |
| **公有数据库连接** | O | O | O |
| **团队协作** | O | O | 通过 SCM（Git 等） |
| **ERD 协同编辑** | O | O | - |
| **数据同步** | O | O | 通过 SCM（Git 等） |
| **离线/隔离网络** | - | - | O |
| **MCP（AI 工具集成）** | - | O | O |
| **认证方式** | OAuth | OAuth | 许可证密钥 |

## :floppy_disk: 支持的数据库

| Database | |
|----------|:-:|
| MySQL | ![MySQL](https://img.shields.io/badge/MySQL-4479A1?style=flat-square&logo=mysql&logoColor=white) |
| MariaDB | ![MariaDB](https://img.shields.io/badge/MariaDB-003545?style=flat-square&logo=mariadb&logoColor=white) |
| PostgreSQL | ![PostgreSQL](https://img.shields.io/badge/PostgreSQL-4169E1?style=flat-square&logo=postgresql&logoColor=white) |
| Oracle | ![Oracle](https://img.shields.io/badge/Oracle-F80000?style=flat-square&logo=oracle&logoColor=white) |
| SQL Server | ![SQL Server](https://img.shields.io/badge/SQL%20Server-CC2927?style=flat-square&logo=microsoftsqlserver&logoColor=white) |
| SQLite | ![SQLite](https://img.shields.io/badge/SQLite-003B57?style=flat-square&logo=sqlite&logoColor=white) |
| H2 | ![H2](https://img.shields.io/badge/H2-0000BB?style=flat-square) |

## :bulb: 主要应用场景

- :repeat: CRUD 及持久层代码自动生成
- :rewind: 遗留数据库逆向工程
- :clipboard: 项目初期数据模型设计及结构审查
- :straight_ruler: 基于公共模板的开发标准化
- :bar_chart: Schema 变更分析及迁移工作流优化
- :office: 提升管理多个数据库的组织内部开发效率

## :package: 下载

请在 [Releases](../../releases) 页面下载最新的 Desktop 应用。

| Platform | Installer |
|----------|-----------|
| **Windows** | `.exe` 安装程序 |
| **macOS** | `.dmg` 安装程序 |

## :speech_balloon: 问题与反馈

Bug 报告、功能请求和使用咨询请在本仓库的 [Issues](../../issues) 中提交。

- 提交 Issue 时，请注明使用环境（Web/Desktop、操作系统、数据库类型），以便更快地处理。

## :page_facing_up: 许可证

NeoSQL 以商业许可证提供。使用范围、再分发权限、维护范围和部署条件以单独的协议或供应政策为准。

有关许可证、采购、技术支持和企业部署的咨询，请通过[官网](https://neosql.unvus.com/)联系我们。
