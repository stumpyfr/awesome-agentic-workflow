# Awesome GitHub Agentic Workflows [![Awesome](https://awesome.re/badge.svg)](https://awesome.re)

> A curated list of awesome resources, examples, and tools for GitHub Agentic Workflows (gh-aw)

GitHub Agentic Workflows is a revolutionary approach to automation that lets you write AI-powered workflows in natural language using Markdown files. These workflows run securely in GitHub Actions with access to MCP servers, tools, and the GitHub API.

## Contents

- [Official Resources](#official-resources)
- [Getting Started](#getting-started)
- [Example Workflows](#example-workflows)
- [Shared Components](#shared-components)
- [Tools & Utilities](#tools--utilities)
- [Tutorials & Guides](#tutorials--guides)
- [Real-World Use Cases](#real-world-use-cases)
- [Security & Best Practices](#security--best-practices)
- [Community](#community)

## Official Resources

- [gh-aw CLI](https://github.com/github/gh-aw) - Official CLI extension for managing agentic workflows
- [Documentation](https://github.com/github/gh-aw/blob/main/.github/aw/github-agentic-workflows.md) - Complete reference documentation
- [Agent Factory Status](https://github.github.com/gh-aw/agent-factory-status/) - Live status of all workflows in production
- [Release Notes](https://github.com/github/gh-aw/releases) - Latest updates and breaking changes
- [MCP Specification](https://spec.modelcontextprotocol.io/) - Model Context Protocol specification

## Getting Started

### Installation

```bash
# Install gh-aw CLI extension
gh extension install github/gh-aw

# Initialize your repository
gh aw init
```

### Quick Start

1. Create a workflow file in `.github/workflows/my-workflow.md`
2. Add YAML frontmatter with triggers and permissions
3. Write your workflow logic in natural language
4. Compile to lock file: `gh aw compile my-workflow`
5. Commit and push to trigger the workflow

### First Workflow Example

```markdown
---
on:
  issues:
    types: [opened]
permissions:
  issues: write
safe-outputs:
  add-comment:
---

# Welcome Bot

When a new issue is opened, post a friendly welcome comment.

Add a comment thanking the user for opening the issue and letting them know
someone will review it soon.
```

### Learn More

- [Meet the Workflows Blog Series](https://github.com/github/gh-aw/blob/main/docs/src/content/docs/blog/2026-01-13-meet-the-workflows.md) - Comprehensive tour of production workflows
- [Example Workflows](#example-workflows) - Browse curated examples below

## Example Workflows

> **Browse 50+ production workflows** in the [gh-aw repository](https://github.com/github/gh-aw/tree/main/.github/workflows) or view the [Agent Factory Status](https://github.github.com/gh-aw/agent-factory-status/) page.

### Issue Management

- [Issue Triage Agent](https://github.com/github/gh-aw/blob/main/.github/workflows/issue-triage-agent.md) - Automatically label and assign issues based on content
- [Stale Repo Identifier](https://github.com/github/gh-aw/blob/main/.github/workflows/stale-repo-identifier.md) - Identify and report on inactive repositories
- [Auto Triage Issues](https://github.com/github/gh-aw/blob/main/.github/workflows/auto-triage-issues.md) - Automatically categorize and label new and existing unlabeled issues using keyword and pattern analysis
- [Sub-Issue Closer](https://github.com/github/gh-aw/blob/main/.github/workflows/sub-issue-closer.md) - Recursively close parent issues when all their sub-issues are completed
- [Issue Arborist](https://github.com/github/gh-aw/blob/main/.github/workflows/issue-arborist.md) - Prune and organize issue trees for better project tracking

### Pull Request Automation

- [Grumpy Reviewer](https://github.com/github/gh-aw/blob/main/.github/workflows/grumpy-reviewer.md) - Strict code review with high standards
- [Copilot PR NLP Analysis](https://github.com/github/gh-aw/blob/main/.github/workflows/copilot-pr-nlp-analysis.md) - NLP analysis of pull request content
- [Breaking Change Checker](https://github.com/github/gh-aw/blob/main/.github/workflows/breaking-change-checker.md) - Identify potential breaking changes
- [PR Fix](https://github.com/github/gh-aw/blob/main/.github/workflows/pr-fix.md) - Automatically fix issues in pull requests
- [PR Triage Agent](https://github.com/github/gh-aw/blob/main/.github/workflows/pr-triage-agent.md) - Categorize, assess risk, and prioritize agent-created pull requests with scoring and batch review recommendations
- [PR Nitpick Reviewer](https://github.com/github/gh-aw/blob/main/.github/workflows/pr-nitpick-reviewer.md) - Detail-oriented code review targeting style and convention issues that linters miss
- [Draft PR Cleanup](https://github.com/github/gh-aw/blob/main/.github/workflows/draft-pr-cleanup.md) - Automatically identify and clean up stale draft pull requests
- [Security Review](https://github.com/github/gh-aw/blob/main/.github/workflows/security-review.md) - Security-focused PR reviews to catch changes that weaken security posture or extend AWF boundaries

### Project Management

- [Daily Backlog Burner](https://github.com/github/gh-aw/blob/main/.github/workflows/daily-backlog-burner.md) - Process and triage backlog items daily
- [Org Health Report](https://github.com/github/gh-aw/blob/main/.github/workflows/org-health-report.md) - Generate organization health metrics
- [Daily QA](https://github.com/github/gh-aw/blob/main/.github/workflows/daily-qa.md) - Daily quality assurance checks

### Code Quality

- [CI Doctor](https://github.com/github/gh-aw/blob/main/.github/workflows/ci-doctor.md) - Diagnose and fix CI/CD issues
- [Schema Consistency Checker](https://github.com/github/gh-aw/blob/main/.github/workflows/schema-consistency-checker.md) - Validate schema consistency
- [Repository Quality Improver](https://github.com/github/gh-aw/blob/main/.github/workflows/repository-quality-improver.md) - Suggest repository improvements
- [Functional Pragmatist](https://github.com/github/gh-aw/blob/main/.github/workflows/functional-pragmatist.md) - Improve functional programming patterns
- [Go Module Usage Expert](https://github.com/github/gh-aw/blob/main/.github/workflows/go-fan.md) - Go module best practices
- [Typist](https://github.com/github/gh-aw/blob/main/.github/workflows/typist.md) - TypeScript type improvements
- [Code Simplifier](https://github.com/github/gh-aw/blob/main/.github/workflows/code-simplifier.md) - Analyze recently modified code and create pull requests with clarity and maintainability improvements
- [Duplicate Code Detector](https://github.com/github/gh-aw/blob/main/.github/workflows/duplicate-code-detector.md) - Identify duplicated patterns across the codebase using semantic analysis and suggest refactoring opportunities
- [Static Analysis Report](https://github.com/github/gh-aw/blob/main/.github/workflows/static-analysis-report.md) - Generate comprehensive static analysis reports for the codebase
- [Super Linter](https://github.com/github/gh-aw/blob/main/.github/workflows/super-linter.md) - Run multi-language linting across the entire repository

### Orchestration & Specialized

- [Workflow Generator](https://github.com/github/gh-aw/blob/main/.github/workflows/workflow-generator.md) - Generate new workflows from descriptions
- [Q](https://github.com/github/gh-aw/blob/main/.github/workflows/q.md) - Interactive Q&A workflow for assistance
- [Daily Accessibility Review](https://github.com/github/gh-aw/blob/main/.github/workflows/daily-accessibility-review.md) - Daily accessibility checks
- [Daily Performance Improver](https://github.com/github/gh-aw/blob/main/.github/workflows/daily-perf-improver.md) - Performance optimization suggestions

### Security

- [Code Scanning Fixer](https://github.com/github/gh-aw/blob/main/.github/workflows/code-scanning-fixer.md) - Automatically fix code scanning alerts by creating pull requests with remediation
- [Security Compliance](https://github.com/github/gh-aw/blob/main/.github/workflows/security-compliance.md) - Check repository compliance against security standards and policies
- [Daily Malicious Code Scan](https://github.com/github/gh-aw/blob/main/.github/workflows/daily-malicious-code-scan.md) - Daily scan for malicious code patterns and supply chain threats
- [Daily Security Red Team](https://github.com/github/gh-aw/blob/main/.github/workflows/daily-security-red-team.md) - Daily adversarial security testing from a red team perspective
- [Daily Semgrep Scan](https://github.com/github/gh-aw/blob/main/.github/workflows/daily-semgrep-scan.md) - Daily static security analysis using Semgrep rules

### Documentation

- [Daily Doc Updater](https://github.com/github/gh-aw/blob/main/.github/workflows/daily-doc-updater.md) - Automatically keep documentation in sync with code changes
- [Technical Doc Writer](https://github.com/github/gh-aw/blob/main/.github/workflows/technical-doc-writer.md) - Generate technical documentation from code analysis
- [Developer Docs Consolidator](https://github.com/github/gh-aw/blob/main/.github/workflows/developer-docs-consolidator.md) - Consolidate and normalize scattered developer documentation
- [Docs Noob Tester](https://github.com/github/gh-aw/blob/main/.github/workflows/docs-noob-tester.md) - Validate documentation from a newcomer's perspective to find gaps and confusing sections

### Analytics & Reporting

- [Copilot Session Insights](https://github.com/github/gh-aw/blob/main/.github/workflows/copilot-session-insights.md) - Analyze Copilot session data to surface usage patterns and insights
- [Daily Code Metrics](https://github.com/github/gh-aw/blob/main/.github/workflows/daily-code-metrics.md) - Track daily code quality trends across the repository
- [Metrics Collector](https://github.com/github/gh-aw/blob/main/.github/workflows/metrics-collector.md) - Collect and aggregate workflow execution metrics for trend analysis

## Shared Components

### Custom Safe Outputs

- [Safe Output App Config](https://github.com/github/gh-aw/blob/main/.github/workflows/shared/safe-output-app.md) - Shared GitHub App authentication configuration for safe outputs
- [Daily Safe Outputs Conformance](https://github.com/github/gh-aw/blob/main/.github/workflows/daily-safe-outputs-conformance.md) - Daily automated conformance checks against the Safe Outputs specification
- [Daily Safe Output Optimizer](https://github.com/github/gh-aw/blob/main/.github/workflows/daily-safe-output-optimizer.md) - Analyze gateway logs for safe output errors and create issues to improve tool descriptions
- [Weekly Safe Outputs Spec Review](https://github.com/github/gh-aw/blob/main/.github/workflows/weekly-safe-outputs-spec-review.md) - Weekly alignment check between the Safe Outputs specification and its conformance checker

### MCP Wrappers

- [MCP Inspector](https://github.com/github/gh-aw/blob/main/.github/workflows/mcp-inspector.md) - Inspect MCP server capabilities
- [GitHub MCP Tools Report](https://github.com/github/gh-aw/blob/main/.github/workflows/github-mcp-tools-report.md) - Report on GitHub MCP tools
- [arXiv MCP](https://github.com/github/gh-aw/blob/main/.github/workflows/shared/mcp/arxiv.md) - Access arXiv research papers for searching, fetching metadata, and retrieving PDFs
- [AST Grep MCP](https://github.com/github/gh-aw/blob/main/.github/workflows/shared/mcp/ast-grep.md) - Structural code search and pattern matching using AST analysis
- [Azure MCP](https://github.com/github/gh-aw/blob/main/.github/workflows/shared/mcp/azure.md) - Read-only access to 40+ Azure services including Key Vault, Storage, and AI Foundry
- [Brave Search MCP](https://github.com/github/gh-aw/blob/main/.github/workflows/shared/mcp/brave.md) - Web and news search via the Brave Search API
- [Chroma MCP](https://github.com/github/gh-aw/blob/main/.github/workflows/shared/mcp/chroma.md) - Vector database with semantic search and persistent document storage
- [Context7 MCP](https://github.com/github/gh-aw/blob/main/.github/workflows/shared/mcp/context7.md) - Fetch up-to-date library documentation and API references
- [Datadog MCP](https://github.com/github/gh-aw/blob/main/.github/workflows/shared/mcp/datadog.md) - Query Datadog monitoring data for metrics, logs, and incidents
- [DeepWiki MCP](https://github.com/github/gh-aw/blob/main/.github/workflows/shared/mcp/deepwiki.md) - Access deep wiki information about GitHub repositories
- [Drain3 MCP](https://github.com/github/gh-aw/blob/main/.github/workflows/shared/mcp/drain3.md) - Log template mining and pattern analysis using the Drain3 algorithm
- [Jupyter MCP](https://github.com/github/gh-aw/blob/main/.github/workflows/shared/mcp/jupyter.md) - Execute code and manage Jupyter notebooks programmatically
- [MarkItDown MCP](https://github.com/github/gh-aw/blob/main/.github/workflows/shared/mcp/markitdown.md) - Convert documents (PDF, Office, HTML) to Markdown
- [Notion MCP](https://github.com/github/gh-aw/blob/main/.github/workflows/shared/mcp/notion.md) - Integrate with Notion workspaces for pages, databases, and blocks
- [Semgrep MCP](https://github.com/github/gh-aw/blob/main/.github/workflows/shared/mcp/semgrep.md) - Static analysis and security scanning with custom and built-in rules
- [Sentry MCP](https://github.com/github/gh-aw/blob/main/.github/workflows/shared/mcp/sentry.md) - Query Sentry for error tracking, issues, and performance data
- [Memory Server MCP](https://github.com/github/gh-aw/blob/main/.github/workflows/shared/mcp/server-memory.md) - Persistent key-value memory store for agents across workflow runs
- [Slack MCP](https://github.com/github/gh-aw/blob/main/.github/workflows/shared/mcp/slack.md) - Send messages, read channels, and interact with Slack workspaces
- [Tavily Search MCP](https://github.com/github/gh-aw/blob/main/.github/workflows/shared/mcp/tavily.md) - AI-optimized web search with structured results via the Tavily API

### Reusable Templates

Browse the [shared workflows directory](https://github.com/github/gh-aw/tree/main/.github/workflows/shared) for reusable components and templates you can import into your workflows.

Notable shared templates:

- [GitHub Queries Safe Input](https://github.com/github/gh-aw/blob/main/.github/workflows/shared/github-queries-safe-input.md) - Pre-built safe input patterns for common GitHub API queries
- [PR Data Safe Input](https://github.com/github/gh-aw/blob/main/.github/workflows/shared/pr-data-safe-input.md) - Safe input templates for pull request data retrieval
- [MCP Debug Utilities](https://github.com/github/gh-aw/blob/main/.github/workflows/shared/mcp-debug.md) - Debugging tools and patterns for MCP server interactions
- [Python Data Visualization](https://github.com/github/gh-aw/blob/main/.github/workflows/shared/python-dataviz.md) - Reusable Python visualization patterns for generating charts and graphs
- [Metrics Patterns](https://github.com/github/gh-aw/blob/main/.github/workflows/shared/metrics-patterns.md) - Common metrics collection and reporting templates
- [Token Cost Analysis](https://github.com/github/gh-aw/blob/main/.github/workflows/shared/token-cost-analysis.md) - Analyze and optimize AI model token usage and costs
- [Ollama Threat Scan](https://github.com/github/gh-aw/blob/main/.github/workflows/shared/ollama-threat-scan.md) - Threat scanning using locally-run Ollama models

## Tools & Utilities

### CLI Tools

- `gh aw init` - Initialize repository for agentic workflows
- `gh aw compile` - Generate lock files from markdown workflows
- `gh aw logs` - View workflow execution logs
- `gh aw audit` - Audit workflow runs and analyze failures
- `gh aw fix` - Apply codemods to fix deprecated syntax
- `gh aw update` - Update workflows from source repositories
- `gh aw status` - Show workflow compilation status

### Development Tools

- [Agent Performance Analyzer](https://github.com/github/gh-aw/blob/main/.github/workflows/agent-performance-analyzer.md) - Analyze agent execution metrics
- [Copilot Agent Analysis](https://github.com/github/gh-aw/blob/main/.github/workflows/copilot-agent-analysis.md) - Deep analysis of Copilot agent behavior
- [Prompt Clustering Analysis](https://github.com/github/gh-aw/blob/main/.github/workflows/prompt-clustering-analysis.md) - Cluster and analyze prompts
- [Ubuntu Image Analyzer](https://github.com/github/gh-aw/blob/main/.github/workflows/ubuntu-image-analyzer.md) - Analyze Ubuntu runner images

## Tutorials & Guides

### Official Tutorials

- [Creating Your First Workflow](https://github.com/github/gh-aw/blob/main/.github/aw/create-agentic-workflow.md)
- [Updating Workflows](https://github.com/github/gh-aw/blob/main/.github/aw/update-agentic-workflow.md)
- [Debugging Workflows](https://github.com/github/gh-aw/blob/main/.github/aw/debug-agentic-workflow.md)
- [Upgrading Workflows](https://github.com/github/gh-aw/blob/main/.github/aw/upgrade-agentic-workflows.md)

### Blog Posts

- [Meet the Workflows](https://github.com/github/gh-aw/blob/main/docs/src/content/docs/blog/2026-01-13-meet-the-workflows.md) - Introduction to agentic workflows
- [Tool Infrastructure Workflows](https://github.com/github/gh-aw/blob/main/docs/src/content/docs/blog/2026-01-13-meet-the-workflows-tool-infrastructure.md) - MCP server inspection and tools
- [Continuous Improvement Workflows](https://github.com/github/gh-aw/blob/main/docs/src/content/docs/blog/2026-01-13-meet-the-workflows-continuous-improvement.md) - Code quality and refactoring
- [Advanced Analytics Workflows](https://github.com/github/gh-aw/blob/main/docs/src/content/docs/blog/2026-01-13-meet-the-workflows-advanced-analytics.md) - Session analysis and insights

### Video Tutorials

- Coming soon! (Submit your videos via PR)

## Real-World Use Cases

### Open Source Projects

- **[gh-aw Repository](https://github.com/github/gh-aw)** - The official repository with 50+ production workflows
- **This Repository** - Jira/Confluence integration for PR validation

### Company Implementations

- Coming soon! (Share your use cases via PR)

### Case Studies

- Coming soon! (Submit case studies via PR)

## Security & Best Practices

### Permission Guidelines

- **Principle of Least Privilege** - Request only necessary permissions
- **Read vs Write** - Use read permissions when possible
- **Token Scoping** - Scope tokens to specific resources

### Network Security

- **Agent Workflow Firewall (AWF)** - All workflows run in sandboxed environment
- **Explicit Network Access** - Declare allowed domains in frontmatter
- **Network Allowlist** - Use `network.allowed` for external API calls

### Safe Outputs

- **Structured Communication** - Use safe-outputs for GitHub API calls
- **No Template Injection** - Avoid direct user input in GitHub API calls
- **Output Validation** - Validate data before posting to GitHub

### Example Secure Workflow

```yaml
---
on:
  pull_request:
    types: [opened]
permissions:
  pull-requests: write
  contents: read
network:
  allowed:
    - defaults
    - api.example.com
safe-outputs:
  add-comment:
    max: 1
---
```

## Community

### Official Channels

- [GitHub Discussions](https://github.com/github/gh-aw/discussions) - Ask questions and share ideas
- [GitHub Issues](https://github.com/github/gh-aw/issues) - Report bugs and request features

### Community Resources

- [Awesome List Discussions](https://github.com/stumpyfr/test_jira-mcp/discussions) - Discuss this awesome list
- Coming soon! (Add your community channels via PR)

## Contributing

Contributions are welcome! Please read the [contributing guidelines](CONTRIBUTING.md) first.

To add a resource:
1. Check it's not already included
2. Fork this repository
3. Add your resource in the appropriate category
4. Submit a pull request

## License

[![CC0](https://mirrors.creativecommons.org/presskit/buttons/88x31/svg/cc-zero.svg)](https://creativecommons.org/publicdomain/zero/1.0/)

To the extent possible under law, Niels Freier has waived all copyright and related or neighboring rights to this work.
