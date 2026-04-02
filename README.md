# NeoSQL

An all-in-one database development platform for ERD design, table management, SQL editing, schema change tracking, and automated source code generation.

![License](https://img.shields.io/badge/license-Commercial-blue)
![Platforms](https://img.shields.io/badge/platforms-Windows%20%7C%20macOS%20%7C%20Web-lightgrey)
![Deployment](https://img.shields.io/badge/deployment-Desktop%20%7C%20Web%20%7C%20Offline-success)

**Website**: https://neosql.unvus.com/

---

## Overview

NeoSQL goes beyond simple ERD tooling. It provides database metadata inspection, ERD design and visualization, detailed table management, SQL editing, schema change tracking, and template-based source code generation — all in a single, unified workflow.

It supports web, desktop, and offline environments, adapting flexibly from air-gapped networks to online collaboration with real-time synchronization. NeoSQL also integrates with AI development tools via MCP (Model Context Protocol), enabling AI workflows without directly exposing database credentials.

## Why NeoSQL

- Standardize development artifacts based on real database metadata.
- Bridge the gap between design and implementation by working with ERDs and live schemas together.
- Edit tables, run SQL, and generate code — all within one tool, in a continuous flow.
- Automate repetitive code and backend artifact generation to boost productivity.
- Track schema changes and streamline follow-up DDL workflows.
- Integrate with AI tools while keeping database credentials secure.
- Support web, desktop, on-premise, and air-gapped environments under a single product.

## Key Features

- Inspect table, column, key, and relationship metadata across supported databases
- Design and visualize ERDs based on real schemas
- Edit table details including columns, indexes, foreign keys, and constraints
- SQL editor with autocomplete, syntax highlighting, and result inspection
- Template-based source code generation using Velocity
- Direct file generation on desktop and ZIP download on web
- DDL generation tailored to each DBMS
- MCP-based AI tool integration with project-ID-based secure access
- Manual Commit/Rollback review flow after DML execution
- Offline file storage and online synchronization

## Highlights

### ERD & Schema Visualization

NeoSQL provides an ERD-based workspace for visually inspecting and reviewing tables and relationships. Useful for both new designs and reverse engineering existing databases to understand structure and assess change impact.

### Enterprise Deployment

Designed for enterprise-grade deployment and operation. Covers desktop installations, web deployments, on-premise environments, and air-gapped networks.

### Real-Time Collaboration

In Online mode, multiple users can share the same project through a Sync Server with PouchDB/CouchDB-based synchronization. ERDs, table configurations, connection settings, and conversion configs are synced across devices. Changes from other users are detected and can be reviewed or reloaded in real time.

### AI Integration with Safe Execution

NeoSQL supports the MCP (Model Context Protocol) standard for integration with AI tools such as Claude, Cursor, and VS Code. Database credentials are referenced by project ID rather than embedded in AI config files. DML results are not auto-committed — users explicitly decide to Commit or Rollback in the SQL editor.

## Usage Environments

NeoSQL can be used in three ways. The right choice depends on your network environment and database access requirements.

### Which environment should I choose?

| Situation | Recommended |
|-----------|-------------|
| Need direct access to internal databases with team collaboration | **Desktop (Online)** |
| Air-gapped or restricted network environment | **Desktop (Offline)** |
| Working with public databases only (cloud DB, etc.) and prefer no installation | **Web App** |

> **Note**: Most internal databases only allow access from the developer's own machine due to firewall policies. In this case, the **Desktop app** is required. The Web App can only connect to publicly accessible databases.

### Feature Comparison

| Feature | Web App | Desktop (Online) | Desktop (Offline) |
|---------|:-------:|:-----------------:|:-----------------:|
| **Installation** | Not required (browser) | Windows / macOS | Windows / macOS |
| **Internal DB access** | - | O | O |
| **Public DB access** | O | O | O |
| **Team collaboration** | O | O | via SCM (Git, etc.) |
| **Real-time ERD co-editing** | O | O | - |
| **Data sync** | O | O | via SCM (Git, etc.) |
| **Offline / air-gapped** | - | - | O |
| **MCP (AI tool integration)** | - | O | O |
| **Authentication** | OAuth | OAuth | License key |

## Supported Databases

- MySQL
- MariaDB
- PostgreSQL
- Oracle
- Microsoft SQL Server
- SQLite
- H2

## Use Cases

- Automated CRUD and persistence layer code generation
- Reverse engineering legacy databases
- Data model design and structural review for new projects
- Development standardization through shared templates
- Schema change analysis and streamlined migration workflows
- Improved productivity for organizations managing multiple databases

## Download

Download the latest Desktop app from the [Releases](../../releases) page.

- **Windows**: `.exe` installer
- **macOS**: `.dmg` installer

## Issues & Feedback

Bug reports, feature requests, and questions are managed in this repository's [Issues](../../issues).

- When filing an issue, please include your environment (Web/Desktop, OS, database type) for faster resolution.

## License

NeoSQL is provided under a commercial license. Usage scope, redistribution rights, maintenance coverage, and deployment terms are subject to separate agreements or supply policies.

For licensing, adoption, technical support, and enterprise deployment inquiries, please contact us through the [website](https://neosql.unvus.com/).
