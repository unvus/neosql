**English** | [한국어](README_GITHUB_ko.md) | [中文](README_GITHUB_zh.md)

<div align="center">

# NeoSQL

**An all-in-one database development platform for ERD design, table management, SQL editing, schema change tracking, and automated source code generation.**

[![License](https://img.shields.io/badge/license-Commercial-blue?style=for-the-badge)](https://neosql.unvus.com/)
[![Platforms](https://img.shields.io/badge/platforms-Windows%20%7C%20macOS%20%7C%20Web-lightgrey?style=for-the-badge)](#usage-environments)
[![Deployment](https://img.shields.io/badge/deployment-Desktop%20%7C%20Web%20%7C%20Offline-success?style=for-the-badge)](#feature-comparison)

[Website](https://neosql.unvus.com/) &middot; [Download](#-download) &middot; [Issues & Feedback](#-issues-and-feedback)

</div>

---

## Overview

NeoSQL goes beyond traditional ERD tools. It brings together database metadata inspection, ERD design and visualization, detailed table management, SQL editing, schema change tracking, and template-based source code generation in a single, unified workflow.

It supports web, desktop, and offline environments, making it suitable for everything from air-gapped deployments to real-time online collaboration. NeoSQL also supports integration with AI development tools through MCP (Model Context Protocol), enabling AI-assisted workflows without directly exposing database connection details.

## :sparkles: What NeoSQL Delivers

- :white_check_mark: Standardize development outputs based on real database metadata.
- :white_check_mark: Reduce the gap between design and implementation by working with ERDs and actual schemas side by side.
- :white_check_mark: Edit tables, run SQL, and generate code within a single workflow.
- :white_check_mark: Improve productivity by automating repetitive code generation and backend deliverables.
- :white_check_mark: Track schema changes and streamline follow-up DDL workflows.
- :white_check_mark: Integrate with AI development tools while keeping database connection details secure.
- :white_check_mark: Support web, desktop, on-premise, and air-gapped environments within a single platform.

## :rocket: Key Features

| | Feature |
|:---:|---------|
| :mag: | Inspect table, column, key, and relationship metadata for supported databases |
| :art: | Design and visualize ERDs based on actual schemas |
| :pencil2: | Edit table details, including columns, indexes, foreign keys, and constraints |
| :keyboard: | Use a SQL editor with autocomplete, syntax highlighting, and result inspection |
| :gear: | Generate source code with Velocity-based templates |
| :file_folder: | Generate files directly in the desktop app or download them as ZIP files in the web app |
| :wrench: | Support DDL generation workflows tailored to each DBMS |
| :robot: | Integrate with MCP-compatible AI tools using secure project-ID-based access |
| :shield: | Review DML execution results with manual commit/rollback control |
| :cloud: | Support both offline file storage and online synchronization |

## :star2: Highlights

### :art: ERD and Schema Visualization

NeoSQL provides an ERD-based workspace for visually inspecting and reviewing tables and relationships. It is useful not only for new database design, but also for reverse engineering existing databases, understanding their structure, and evaluating the impact of schema changes.

### :building_construction: Enterprise-Ready Deployment

NeoSQL is designed for enterprise deployment and operation. It supports desktop installations, web deployments, on-premise environments, and air-gapped networks, making it flexible enough to fit a wide range of security and infrastructure requirements.

### :handshake: Collaborative Editing and Synchronization

In Online mode, multiple users can work on the same project through a synchronization architecture based on Sync Server and PouchDB/CouchDB. ERDs, table settings, connection information, and transformation settings are synchronized across devices. Changes made by other users can also be detected, reviewed, and reloaded from within the workspace.

### :lock: AI Integration with a Controlled Execution Flow

NeoSQL supports the MCP (Model Context Protocol) standard, allowing integration with AI development tools such as Claude, Cursor, and VS Code. Database connection details are referenced by project ID rather than embedded directly in AI tool configuration files. In addition, DML execution results are not committed automatically, so users can explicitly choose whether to commit or roll back changes in the SQL editor.

## :computer: Usage Environments

NeoSQL can be used in three different ways, depending on your network environment and database access requirements.

### Which environment should I choose?

| Situation | Recommended |
|-----------|:-----------:|
| You need direct access to internal databases with team collaboration | **Desktop (Online)** |
| You work in an air-gapped or restricted network environment | **Desktop (Offline)** |
| You only use publicly accessible databases (such as cloud databases) and want to get started without installation | **Web App** |

> [!NOTE]
> In most enterprise environments, internal databases are only accessible from a developer’s local machine due to firewall policies. In such cases, you must use the **Desktop app**. The **Web App** can only connect to publicly accessible databases.

### Feature Comparison

| Feature | Web App | Desktop (Online) | Desktop (Offline) |
|---------|:-------:|:----------------:|:-----------------:|
| **Installation required** | No (browser-based) | Windows / macOS | Windows / macOS |
| **Direct access to internal databases** | No | Yes | Yes |
| **Access to public databases** | Yes | Yes | Yes |
| **Team collaboration** | Yes | Yes | Via SCM (Git, etc.) |
| **Real-time collaborative ERD editing** | Yes | Yes | No |
| **Data synchronization** | Yes | Yes | Via SCM (Git, etc.) |
| **Offline / air-gapped support** | No | No | Yes |
| **MCP (AI tool integration)** | No | Yes | Yes |
| **Authentication method** | OAuth | OAuth | License key |

## :floppy_disk: Supported Databases

| Database | |
|----------|:-:|
| MySQL | ![MySQL](https://img.shields.io/badge/MySQL-4479A1?style=flat-square&logo=mysql&logoColor=white) |
| MariaDB | ![MariaDB](https://img.shields.io/badge/MariaDB-003545?style=flat-square&logo=mariadb&logoColor=white) |
| PostgreSQL | ![PostgreSQL](https://img.shields.io/badge/PostgreSQL-4169E1?style=flat-square&logo=postgresql&logoColor=white) |
| Oracle | ![Oracle](https://img.shields.io/badge/Oracle-F80000?style=flat-square&logo=oracle&logoColor=white) |
| SQL Server | ![SQL Server](https://img.shields.io/badge/SQL%20Server-CC2927?style=flat-square&logo=microsoftsqlserver&logoColor=white) |
| SQLite | ![SQLite](https://img.shields.io/badge/SQLite-003B57?style=flat-square&logo=sqlite&logoColor=white) |
| H2 | ![H2](https://img.shields.io/badge/H2-0000BB?style=flat-square) |

## :bulb: Common Use Cases

- :repeat: Automated generation of CRUD and persistence-layer code
- :rewind: Reverse engineering of legacy databases
- :clipboard: Initial data model design and structural review for new projects
- :straight_ruler: Standardization of development outputs through shared templates
- :bar_chart: Schema change analysis and migration workflow optimization
- :office: Improved internal development productivity for organizations managing multiple databases

## :package: Download

You can download the latest Desktop app from the [Releases](../../releases) page.

| Platform | Installer |
|----------|-----------|
| **Windows** | `.exe` installer |
| **macOS** | `.dmg` installer |

## :speech_balloon: Issues and Feedback

Bug reports, feature requests, and usage questions can be submitted through the [Issues](../../issues) section of this repository.

- When opening an issue, please include your environment details (Web/Desktop, OS, and database type) to help us respond more quickly.

## :page_facing_up: License

NeoSQL is provided under a commercial license. The scope of use, redistribution rights, maintenance coverage, and deployment terms are subject to separate agreements or commercial policies.

For inquiries about licensing, purchasing, technical support, or enterprise deployment, please contact us through the [website](https://neosql.unvus.com/).
