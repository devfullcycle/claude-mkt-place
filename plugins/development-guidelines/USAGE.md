# Development Guidelines Plugin

## Objective

The Development Guidelines plugin generates comprehensive, language-specific development guideline documents for any programming language. It follows a standardized template structure and creates production-ready guidelines based on authoritative sources, industry best practices, and language-specific characteristics.

## Installation

### Prerequisites

First, add the marketplace to Claude Code:

```bash
/plugin marketplace add devfullcycle/claude-mkt-place
```

### Install Plugin

Then install the Development Guidelines plugin:

```bash
/plugin install development-guidelines@devfullcycle
```

## Available Commands

### `/generate-development-guideline`

**Description**: Generates comprehensive development guideline documents for any programming language, following a standardized template structure. The command performs extensive research, analyzes language characteristics, and creates a complete guideline document with code examples, best practices, and tool recommendations.

**Syntax**:
```bash
/generate-development-guideline <language-name> [--param=value ...]
```

**Parameters** (all optional):
- `--orm=<name>` - ORM or query builder (e.g., prisma, sqlalchemy, sqlc, gorm, hibernate)
- `--web=<name>` - Web framework (e.g., express, fastapi, chi, spring-boot, gin, flask)
- `--framework=<name>` - Main framework (e.g., laravel, nestjs, langgraph, langchain, spring, django)
- `--db=<name>` - Database driver (e.g., pgx, asyncpg, mysql2, jdbc, psycopg2)
- `--testing=<name>` - Testing framework (e.g., jest, pytest, testify, junit, vitest)
- `--logging=<name>` - Logging library (e.g., winston, structlog, zap, logrus, log4j)
- `--validation=<name>` - Validation library (e.g., zod, pydantic, validator, joi)
- `--http=<name>` - HTTP client (e.g., axios, requests, resty, okhttp, httpx)
- `--di=<name>` - Dependency injection (e.g., inversify, wire, spring, dagger)
- `--async=<name>` - Async runtime (e.g., tokio, asyncio, async-std, gevent)
- `--serialization=<name>` - Serialization library (e.g., serde, jackson, gson, msgpack)

**Examples**:
```bash
# Generate basic guideline for a language
/generate-development-guideline Python
/generate-development-guideline TypeScript
/generate-development-guideline Rust
/generate-development-guideline Go

# Generate with specific library preferences
/generate-development-guideline Go --orm=sqlc --web=chi --db=pgx --testing=testify

/generate-development-guideline TypeScript --orm=prisma --web=express --testing=jest --validation=zod

/generate-development-guideline Python --orm=sqlalchemy --web=fastapi --logging=structlog --testing=pytest

/generate-development-guideline Rust --orm=diesel --web=axum --async=tokio --serialization=serde
```

**Workflow**:

1. **Parameter Parsing Phase**: Extracts library preferences from command parameters and auto-populates essential tools (testing, formatting, linting, logging)

2. **Research Phase**: Searches the web for:
   - Official language documentation and tutorials
   - Industry style guides (Google, Uber, Airbnb, Microsoft, Meta, Netflix, etc.)
   - Popular framework conventions
   - Well-established community standards
   - Library metadata (for specified libraries)

3. **Analysis Phase**: Determines which optional sections apply:
   - Static typing features
   - Concurrency primitives
   - Interface mechanisms
   - Profiling tools
   - Docker ecosystem fit

4. **Generation Phase**: Creates a complete guideline document with:
   - "Project Stack" section (if parameters provided)
   - Sequential section numbering (no gaps)
   - Real code examples using standard library or language-native features
   - Actual tool names and commands
   - Links to authoritative sources
   - Language-specific best practices

5. **Validation Phase**: Verifies:
   - No numbering gaps
   - All content is complete
   - Examples are accurate
   - Code examples use stdlib only
   - Document is 1000-1500 lines

**Output**:

The command creates a file named `<language>-development-guidelines.md` with:

- "Project Stack" section listing specified libraries for reference (if parameters provided)
- 20-26 sections (depending on optional sections included)
- Complete code examples using standard library or language-native features
- Command references
- Best practices (language-level, not framework-specific)
- Tool recommendations
- Comprehensive checklist
- Curated references

**Output Structure**:
```
{language}-development-guidelines.md
├── Project Stack (if parameters provided)
├── 1. Principles
├── 2. Project Init
├── 3. Structure
├── 4. Docker (optional)
├── 5. Nomenclature
├── 6. Types (optional)
├── 7. Functions
├── 8. Errors
├── 9. Concurrency (optional)
├── 10. Interfaces (optional)
├── 11. Tests
├── 12. Mocks (optional)
├── 13. Integration Tests
├── 14. Load Testing (optional)
├── 15. Profiling (optional)
├── 16. Benchmarks (optional)
├── 17. Optimization (optional)
├── 18. Documentation
├── 19. Security
├── 20. Performance
├── 21. Comments
├── 22. Database
├── 23. Logs
├── 24. Golden Rules
├── 25. Checklist
└── 26. References
```

## Key Features

- **Library Parameters**: Specify your preferred stack for reference via command-line parameters
- **Automatic Section Numbering**: Handles optional sections and renumbers automatically
- **Research-Backed**: All recommendations based on authoritative sources
- **Language-Specific**: Adapts to each language's unique characteristics
- **Quality Validation**: Built-in checklist ensures completeness and accuracy
- **Language-Generic Focus**: Guideline remains about the language, NOT framework-specific
- **Practical Examples**: Code examples use standard library or language-native features
- **Auto-Populate Tools**: Essential tools (testing, formatting, linting) auto-selected if not specified

## Quality Guarantees

The generated document will have:

- ✅ Sequential section numbering (no gaps)
- ✅ No placeholder content
- ✅ Real, working code examples using standard library or language-native features
- ✅ Accurate tool and library names
- ✅ Valid, authoritative references
- ✅ No contradictions or ambiguities
- ✅ Consistent terminology
- ✅ Practical, actionable guidance
- ✅ "Project Stack" section at document start (if parameters provided)
- ✅ Language-generic (NOT framework-specific)
- ✅ Document size: 1000-1500 lines
- ✅ Minimum 20 code blocks, 5 good vs bad examples, 15 commands

## Important Notes

### Language vs. Framework Guidelines

**This command creates LANGUAGE guidelines, NOT framework guidelines.**

**What this means**:
- The guideline focuses on language-level patterns, idioms, and best practices
- Specified libraries are listed in "Project Stack" section for reference only
- Code examples use **standard library or language-native features**
- Framework-specific details are NOT included in code examples
- Principles apply **regardless of library choice**

**Example**: A TypeScript guideline with `--orm=prisma`:
- ✅ Lists Prisma in "Project Stack" section for reference
- ✅ Code examples use standard PostgreSQL driver (pg library)
- ✅ Explains TypeScript type safety patterns (language-level)
- ✅ Database best practices apply to ALL ORMs
- ❌ NOT a "Prisma guideline for TypeScript developers"

### When to Use Parameters

**Use parameters when**:
- You have a specific project stack in mind
- You want those libraries documented in "Project Stack" section for quick reference
- You want to document your team's technology choices

**Don't use parameters when**:
- You want a 100% language-generic guideline
- You're learning the language and don't know the ecosystem yet
- You don't have specific library preferences

## Support

If the command produces incorrect results:
- Check that the language name is spelled correctly
- Verify internet connectivity for research phase
- Review the validation report for any failures
- Verify parameter syntax: `--key=value` (no spaces around `=`)
- Check that specified libraries are appropriate for the language

