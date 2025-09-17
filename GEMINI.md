# Project Overview

This project provides a set of custom commands for the Gemini CLI, designed to streamline a GitHub-based development workflow. The commands facilitate a structured process for planning, implementing, and creating pull requests for new features and bug fixes.

## Core Components

This repository contains two main components: Gemini Commands and GitHub Templates. They are designed to work together to provide a seamless development workflow.

### Gemini Commands

The `.gemini/commands` directory contains a set of powerful commands that integrate with your GitHub workflow. The commands are grouped by functionality and work together in a sequential workflow:

**1. Planning & Issue Management**

-   **`/issue:create`**: Guides the user through creating a well-structured GitHub issue using the templates.
-   **`/issue:resolve`**: Analyzes a GitHub issue and generates a detailed implementation plan.
    -   **Input**: A GitHub issue number or URL.
    -   **Artifact**: A markdown file in `docs/planning/` containing the implementation plan.
-   **`/planning:new`**: Analyzes the codebase and creates a comprehensive implementation plan for a new feature.
    -   **Input**: A description of the feature you want to build.
    -   **Artifact**: A markdown file in `docs/planning/` containing the implementation plan.

**2. Implementation**

-   **`/implement`**: Takes an implementation plan and guides the developer through the process of writing the code.
    -   **Input**: The path to a markdown file containing an implementation plan.

**3. Pull Request**

-   **`/pr:create`**: Creates a pull request, pre-populating the details from the git history and using the pull request template.

### GitHub Templates

The `.github` directory contains templates that are automatically used by GitHub when creating new issues and pull requests. These templates are also used by the Gemini commands to create a consistent and structured workflow.

-   **Issue Templates**: Located in the `.github/ISSUE_TEMPLATE` directory, these templates provide a starting point for creating different types of issues (bug reports, feature requests, and developer tasks).
-   **Pull Request Template**: The `.github/pull_request_template.md` file is used when creating a new pull request. It helps create a detailed PR with sections for describing the changes, linking to related issues, and explaining how to test the changes.

## Building and Running

This project is a collection of configuration files for the Gemini CLI. There is no build process. To use these commands, the `.gemini` and `.github` directories should be placed in the root of your project.

## Development Conventions

The project follows a convention of using `.toml` files to define custom Gemini CLI commands. Each command has a detailed prompt that instructs the Gemini model on how to behave. The prompts enforce a strict, structured workflow to ensure consistency and quality.

The project uses the `gh` (GitHub CLI) for all interactions with GitHub.

Implementation plans are stored in the `docs/planning` directory in Markdown format. These plans are a central part of the workflow, providing a single source of truth for implementation.