**English** | [한국어](README_ko.md) | [中文](README_zh.md)

<div align="center">

# NeoSQL

**A database development platform connecting ERD design and data standardization, SQL execution, AI-powered analysis, schema change management, and dashboards**

[![License](https://img.shields.io/badge/license-Commercial-blue?style=for-the-badge)](https://neosql.unvus.com/)
[![Platforms](https://img.shields.io/badge/platforms-Windows%20%7C%20macOS%20%7C%20Web-lightgrey?style=for-the-badge)](#environments)
[![Projects](https://img.shields.io/badge/projects-Local%20%7C%20Account-success?style=for-the-badge)](#choosing-a-project-type)

[Website](https://neosql.unvus.com/) &middot; [Download](https://neosql.unvus.com/) &middot; [NeoSQL MCP](https://github.com/unvus/neosql-mcp) &middot; [Issues & Feedback](#issues-and-feedback)

</div>

---

Documentation as of: **2026-11-02**

## Overview

NeoSQL brings understanding database structures, designing schemas, and working with real data into one environment. Visualize existing databases as ERDs, manage tables and database objects, edit SQL query results, and turn queries into dashboards.

**Data dictionaries and domains** connect to the ERD design workspace to generate standard physical names from logical names and consistently apply column data types and properties. Put standards to work while designing actual tables and columns, rather than keeping them only in separate documents.

The built-in **AI Assistant** helps with natural language SQL generation, data retrieval and analysis, query tuning, and error diagnosis using actual schemas and execution context. Through **MCP (Model Context Protocol)**, external AI development tools can use NeoSQL's database tools and work with ERDs.

Available as a Desktop app for Windows and macOS and as a Web App, NeoSQL lets you **start with a local project without signing up or signing in** on Desktop. Account projects let you share projects with teammates and synchronize your work.

## Key Features

### ERD Design and Schema Change Management

- Reverse-engineer ERDs from database tables, columns, keys, and relationships
- Design tables and relationships; edit columns, indexes, foreign keys, and constraints
- Track ERD changes and preview and apply DBMS-specific DDL
- Compare tables, views, and other schema structures within the same DBMS and review change DDL
- Export ERD images and share models through the gallery

### Data Standardization with Data Dictionaries and Domains

To reduce inconsistent names and types for columns with the same meaning, NeoSQL provides **data dictionaries for standard words and abbreviations** and **domain packs for column properties**. Assign standards to each database connection and apply them directly in the ERD.

**From logical names to standard physical names**

- Manage logical names and English abbreviations for standard words, along with synonyms, forbidden words, antonyms, and related words
- Use **compositional dictionaries** to split logical names into registered words and combine their abbreviations, or **complete-term dictionaries** to match registered names exactly
- Generate physical names according to dictionary rules when entering logical table and column names in the ERD
- Add missing words for a specific connection to continue designing, and create paired columns when antonyms are registered
- Display logical or physical names in the ERD so business stakeholders and developers can review the same model

**Consistent column properties through domains**

- Define reusable column properties in domains, including type, length, decimal places, nullability, default values, and auto-increment
- Link words to domains and suggest or apply domains based on the last word in a column's logical name
- Automatically assign a single candidate, or let the user choose when multiple candidates exist
- Apply physical types appropriate to the database using DBMS-specific type mappings
- Preview differences between a modified domain and its associated columns, then apply changes separately after review

For example, register `주문 (order) → ORD` and `일시 (date/time) → DTM`, and link the date/time word to a date/time domain. The logical column name `주문일시` can then produce the physical name `ord_dtm` and inherit the domain's type and properties. Actual physical names and types depend on the selected dictionary, naming settings, and DBMS-specific mappings.

**Share common standards and manage project-specific differences**

- Discover and install data dictionaries and domain packs from the Store or create your own; import and export them in Excel
- Manage members and permissions for account assets to edit and share standards as a team
- Pin a published version per connection and review changes before upgrading to a new version
- Add, modify, or hide words and domains for a specific connection without changing the original
- Review additions, changes, and deletions against the original; revert to the original or clone the connection's current standards into new assets

Local projects can also use official packs and dictionaries and domains stored on the device. Publishing and sharing account assets are distinct from managing device-local assets. Domain changes do not automatically alter the actual database schema; after reviewing design changes, you can proceed to DDL application.

### SQL Editor and Data Workflows

- Syntax highlighting, SQL formatting, schema-aware autocomplete, and inline suggestions from execution history
- Independent database sessions per tab and searchable, reusable SQL execution history
- View, update, and delete data in the result grid; import and export data
- Auto Commit and Manual Commit modes with uncommitted transaction indicators
- Inspect execution plans and use AI for query improvement and error analysis

> Result editing, DDL application, and Commit/Rollback depend on the DBMS and query. Some database systems implicitly commit DDL or do not allow it to be rolled back in a transaction.

### Built-in AI Assistant and External MCP Integration

- Write SQL in natural language and analyze data using actual query results
- Tune queries and diagnose SQL errors using tables, columns, relationships, and execution plans
- Create and modify ERDs and table designs in AI conversations
- Connect AI providers including OpenAI, Anthropic, Google Gemini, and Ollama
- Connect to self-hosted Ollama servers or Ollama Cloud and browse available models
- Use provider keys saved to your account or device and review AI call and token usage
- Use metadata lookup, SQL execution, and ERD design tools from external MCP clients
- Connect to the current or a specified project with global or project-specific MCP configuration

Configure the connections and schemas AI can access and the policies for reading and changing data. Depending on those policies, you can review and approve the SQL and its target before execution. Account projects also support role-based permissions, sensitive-column masking, and DDL approval.

You do not need to enter database passwords directly in MCP client configuration. Please be aware that AI features may send schema information or query results to your selected AI provider, depending on your settings and approvals.

### Query-based Dashboards

- Visualize SELECT results as number cards, tables, and bar, line, area, pie, scatter, and other charts
- Turn SQL editor queries into dashboard tiles
- Arrange and resize tiles; configure query periods and automatic refresh intervals
- Use DBMS-specific monitoring presets for sessions, locks, performance, storage, and schema quality
- Query periods in the connected database's timezone, with options to display values in your timezone

Dashboards are available in both local and account projects. Automatic refresh runs while the dashboard tab is visible. Preset availability depends on the DBMS and connection permissions.

### DBMS-specific Objects and Detailed Management

- Browse and manage views, indexes, sequences, routines, users, permissions, and other objects within each DBMS's supported scope
- Use PostgreSQL RLS policy simulation, Supabase integration, spatial data, and user-defined types
- Select Databricks SQL Warehouses, inspect Delta table properties and version history, and restore table versions

### Team Collaboration and Project Synchronization

Account projects let you invite teammates, configure role-based permissions, and synchronize shared work such as ERDs and project settings. Changes made by other users can be detected, reloaded, and reviewed in your workspace.

## Environments

### Desktop and Web

| Category | Desktop | Web App |
|----------|---------|---------|
| Runtime | Windows, macOS (Apple Silicon and Intel) | Browser |
| Sign-in | Start without an account | Required |
| Database connection path | From the PC running the app | From the service server |
| Internal-network and local databases | Databases accessible from your PC | Only databases accessible from the service server |
| Local projects | Supported | Not supported |
| Account projects and team collaboration | Supported | Supported |
| External AI tools via MCP | Supported | Not supported |
| AI provider keys | Device-local and account keys | Account keys |

> Use the Desktop app for databases accessible only from your internal network or development PC.

### Choosing a Project Type

| Category | Local Project | Account Project |
|----------|---------------|-----------------|
| Requirements | Desktop; sign-in optional | Desktop or Web; sign-in required |
| Project data | Stored on the device | Account-based storage and synchronization |
| Primary use | Individual work and databases on internal or isolated networks | Team sharing and work across devices |
| ERD, SQL, dashboards, data dictionaries | Supported | Supported |
| Built-in AI | Requires a provider accessible from the device | Requires an accessible provider |
| Team members, role permissions, DDL approval, sensitive-column masking | Not supported | Supported |

Basic database work in local projects does not require account sign-in. You can work without internet access with databases reachable from your device; AI requires a provider reachable in that environment. Online features such as downloading public Store assets and updates require a network connection.

Converting between local and account project types is not supported.

## Supported Databases

| Database | |
|----------|:-:|
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


Supported objects, DDL, result editing, and management features vary by DBMS. Integration features for PostgreSQL-based Supabase are also available.

## Common Use Cases

- **Understand existing systems**: Visualize legacy database tables and relationships as ERDs and analyze their structure with AI
- **Data standardization**: Align logical names, physical names, and column properties with shared dictionaries and domains, while managing project-specific exceptions and versions
- **Review designs and changes**: Check how domain changes affect columns and review ERD changes and schema differences through DDL
- **Everyday SQL development**: Write and run queries, edit results, and reuse history in one workspace
- **Data analysis and monitoring**: Explore data in natural language and turn recurring queries into dashboards
- **Connect AI development tools**: Give external agents access to NeoSQL's database context and execution tools through MCP
- **Individual work and team collaboration**: Start locally or share models and settings with teammates in account projects

## Download

Get the latest Desktop installer for your operating system using the download buttons on the [NeoSQL website](https://neosql.unvus.com/).

| Platform | Installer |
|----------|-----------|
| Windows | `.exe` |
| macOS — Apple Silicon / Intel | `.dmg` |

Visit the [website](https://neosql.unvus.com/) for the Web App and product information.

## Issues and Feedback

Use this repository's [Issues](https://github.com/unvus/neosql/issues) for bug reports, feature requests, and questions. You can also report bugs from inside the app, reviewing and attaching screenshots and diagnostic information without signing in.

Please include your app version, environment (Desktop/Web, OS), database type, and steps to reproduce. Exclude sensitive information such as passwords, API keys, and personal data.

## License

NeoSQL is available under a commercial license. Usage scope, redistribution, maintenance coverage, and deployment terms are governed by separate agreements or supply policies.

For licensing, adoption, technical support, and enterprise deployment inquiries, visit the [website](https://neosql.unvus.com/).
