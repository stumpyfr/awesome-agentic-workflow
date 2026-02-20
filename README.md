# Awesome GitHub Agentic Workflows [![Awesome](https://awesome.re/badge.svg)](https://awesome.re)

> A curated list of awesome resources, examples, and tools for GitHub Agentic Workflows (gh-aw)

GitHub Agentic Workflows is a revolutionary approach to automation that lets you write AI-powered workflows in natural language using Markdown files. These workflows run securely in GitHub Actions with access to MCP servers, tools, and the GitHub API.

## Contents

- [Official Resources](#official-resources)
- [Getting Started](#getting-started)
- [Example Workflows](#example-workflows)
- [Shared Components](#shared-components)
- [MCP Servers](#mcp-servers)
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

### Pull Request Automation

- [Grumpy Reviewer](https://github.com/github/gh-aw/blob/main/.github/workflows/grumpy-reviewer.md) - Strict code review with high standards
- [Copilot PR NLP Analysis](https://github.com/github/gh-aw/blob/main/.github/workflows/copilot-pr-nlp-analysis.md) - NLP analysis of pull request content
- [Breaking Change Checker](https://github.com/github/gh-aw/blob/main/.github/workflows/breaking-change-checker.md) - Identify potential breaking changes
- [PR Fix](https://github.com/github/gh-aw/blob/main/.github/workflows/pr-fix.md) - Automatically fix issues in pull requests

### Project Management

- [Daily Backlog Burner](https://github.com/github/gh-aw/blob/main/.github/workflows/daily-backlog-burner.md) - Process and triage backlog items daily
- [Org Health Report](https://github.com/github/gh-aw/blob/main/.github/workflows/org-health-report.md) - Generate organization health metrics
- [Daily QA](https://github.com/github/gh-aw/blob/main/.github/workflows/daily-qa.md) - Daily quality assurance checks

### Code Quality

- [CI Doctor](https://github.com/github/gh-aw/blob/main/.github/workflows/ci-doctor.md) - Diagnose and fix CI/CD issues
- [Schema Consistency Checker](https://github.com/github/gh-aw/blob/main/.github/workflows/schema-consistency-checker.md) - Validate schema consistency
- [Repository Quality Improver](https://github.com/github/gh-aw/blob/main/.github/workflows/repository-quality-improver.md) - Suggest repository improvements
- [Functional Programming Enhancer](https://github.com/github/gh-aw/blob/main/.github/workflows/functional-programming-enhancer.md) - Improve functional programming patterns
- [Go Module Usage Expert](https://github.com/github/gh-aw/blob/main/.github/workflows/go-fan.md) - Go module best practices
- [Typist](https://github.com/github/gh-aw/blob/main/.github/workflows/typist.md) - TypeScript type improvements

### Orchestration & Specialized

- [Workflow Generator](https://github.com/github/gh-aw/blob/main/.github/workflows/workflow-generator.md) - Generate new workflows from descriptions
- [Q](https://github.com/github/gh-aw/blob/main/.github/workflows/q.md) - Interactive Q&A workflow for assistance
- [Daily Accessibility Review](https://github.com/github/gh-aw/blob/main/.github/workflows/daily-accessibility-review.md) - Daily accessibility checks
- [Daily Performance Improver](https://github.com/github/gh-aw/blob/main/.github/workflows/daily-perf-improver.md) - Performance optimization suggestions

## Shared Components

### Custom Safe Outputs

### MCP Wrappers

- [MCP Inspector](https://github.com/github/gh-aw/blob/main/.github/workflows/mcp-inspector.md) - Inspect MCP server capabilities
- [GitHub MCP Tools Report](https://github.com/github/gh-aw/blob/main/.github/workflows/github-mcp-tools-report.md) - Report on GitHub MCP tools

### Reusable Templates

Browse the [shared workflows directory](https://github.com/github/gh-aw/tree/main/.github/workflows/shared) for reusable components and templates you can import into your workflows.

## MCP Servers

### Official MCP Servers

- [Filesystem MCP](https://github.com/modelcontextprotocol/servers/tree/main/src/filesystem) - File system operations
- [GitHub MCP](https://github.com/modelcontextprotocol/servers/tree/main/src/github) - GitHub API integration
- [PostgreSQL MCP](https://github.com/modelcontextprotocol/servers/tree/main/src/postgres) - Database operations
- [Slack MCP](https://github.com/modelcontextprotocol/servers/tree/main/src/slack) - Slack integration

### Community MCP Servers

- **Atlassian MCP** - Jira and Confluence integration (used in this repo)
- [MCP Servers Repository](https://github.com/modelcontextprotocol/servers) - Official collection of MCP servers
- Submit your MCP server integrations via PR!

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
