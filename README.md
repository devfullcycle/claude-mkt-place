# Full Cycle Claude Marketplace

A collection of Claude Code plugins for software architecture and design documentation.

## Available Plugins

This marketplace provides four powerful plugins for architectural documentation and analysis:

- **[ADRs Management](./plugins/adrs-management/USAGE.md)** - Comprehensive Architecture Decision Records (ADRs) analysis, generation, and linking
- **[Diagrams Generator](./plugins/diagrams-generator/USAGE.md)** - Generate C4 and Mermaid diagrams from Feature Design Documents (FDDs)
- **[Project Analyzer](./plugins/project-analizer/USAGE.md)** - Comprehensive architectural analysis, component deep-dive, and dependency auditing
- **[Development Guidelines](./plugins/development-guidelines/USAGE.md)** - Generate comprehensive language-specific development guideline documents

## Installation

### Add Marketplace

To use these plugins, first add this marketplace to Claude Code:

```bash
/plugin marketplace add devfullcycle/claude-mkt-place
```

This command adds the GitHub repository as a plugin marketplace source.

### Install Plugins

After adding the marketplace, install individual plugins:

```bash
# Install ADRs Management plugin
/plugin install adrs-management@devfullcycle

# Install Diagrams Generator plugin
/plugin install diagrams-generator@devfullcycle

# Install Project Analyzer plugin
/plugin install project-analizer@devfullcycle

# Install Development Guidelines plugin
/plugin install development-guidelines@devfullcycle
```

**Note**: The marketplace identifier (`devfullcycle`) is derived from the GitHub organization/username. After adding the marketplace, you can also browse available plugins using:

```bash
/plugin
```

## Quick Start

### ADRs Management

Document architectural decisions systematically:

```bash
/adr-map                    # Phase 1: Map codebase
/adr-identify AUTH DATA     # Phase 2: Identify potential ADRs
/adr-generate BILLING       # Phase 3: Generate formal ADRs
/adr-link                   # Link ADRs with relationships
```

### Diagrams Generator

Create visual documentation from FDDs:

```bash
/c4-generate docs/features/payment-fdd.md
/mermaid-generate docs/features/auth-fdd.md
```

### Project Analyzer

Analyze project architecture and dependencies:

```bash
/generate-architectural-report
/run-dependency-audit
```

### Development Guidelines

Generate comprehensive development guidelines for any programming language:

```bash
/generate-development-guideline Python
/generate-development-guideline TypeScript --orm=prisma --web=express --testing=jest
/generate-development-guideline Go --orm=sqlc --web=chi --db=pgx
```

## Documentation

For detailed usage instructions, see each plugin's documentation:

- [ADRs Management Usage Guide](./plugins/adrs-management/USAGE.md)
- [Diagrams Generator Usage Guide](./plugins/diagrams-generator/USAGE.md)
- [Project Analyzer Usage Guide](./plugins/project-analizer/USAGE.md)
- [Development Guidelines Usage Guide](./plugins/development-guidelines/USAGE.md)
