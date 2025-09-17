# 🤖 Gemini CLI GitHub Extensions

Welcome to the Gemini CLI GitHub Extensions! This project provides a set of custom commands for the Gemini CLI, designed to supercharge your GitHub workflow. 🚀

These extensions bring the power of Gemini AI directly into your development process, helping you plan, implement, and ship new features and bug fixes with ease.

## ✨ Features

-   **Plan Generation**: Automatically create comprehensive implementation plans from GitHub issues or feature descriptions.
-   **Guided Implementation**: Let Gemini guide you through code implementation, step by step.
-   **Effortless PRs**: Create detailed pull requests with pre-populated information from your git history.
-   **Seamless GitHub Integration**: Works with the `gh` CLI to manage issues and pull requests.

## 📦 Installation

To add these extensions to your existing project, run the following command in the root of your repository:

```bash
git clone --depth 1 https://github.com/scriptmunkee/github-gemini-cli-extensions.git .github-gemini-tmp && rsync -av .github-gemini-tmp/.gemini/ ./.gemini/ && rsync -av .github-gemini-tmp/.github/ ./.github/ && rm -rf .github-gemini-tmp
```

## ⚙️ Dependencies

This project requires the following dependencies to be installed on your system:

-   [**Google Gemini CLI**](https://github.com/google-gemini/gemini-cli): The core CLI for interacting with Gemini.
-   [**GitHub CLI (`gh`)**](https://cli.github.com/): For all interactions with GitHub.

---

## 🛠️ What's Included

This repository contains two main components: Gemini Commands and GitHub Templates. They are designed to work together to provide a seamless development workflow.

### Gemini Commands

The `.gemini/commands` directory contains a set of powerful commands that integrate with your GitHub workflow. 

#### Command Groups

The commands are grouped by functionality and work together in a sequential workflow:

**1. Planning & Issue Management**

These commands are the starting point of your workflow. You can either start by creating a new issue, resolving an existing one, or planning a new feature.

-   **`/issue:create`**: Use this command to create a new GitHub issue from your terminal. It will guide you through the process of creating a well-structured issue based on the Github templates.
-   **`/issue:resolve`**: When you need to tackle an existing GitHub issue, this command will analyze the issue and generate an implementation plan to resolve it.
    -   **Input**: A GitHub issue number or URL.
    -   **Artifact**: A markdown file in `docs/planning/` containing the implementation plan.
-   **`/planning:new`**: Use this command to generate a detailed implementation plan for a new feature. Gemini will analyze your codebase and create a step-by-step plan to guide you.
    -   **Input**: A description of the feature you want to build.
    -   **Artifact**: A markdown file in `docs/planning/` containing the implementation plan.

**2. Implementation**

Once you have a plan, this command will help you execute it.

-   **`/implement`**: This command takes an implementation plan and guides you through the process of writing the code. It will help you stay on track and ensure that you are following the plan.
    -   **Input**: The path to a markdown file containing an implementation plan.

**3. Pull Request**

When your code is ready, this command will help you create a pull request.

-   **`/pr:create`**: This command will create a pull request for you, pre-populating the details from your git history. It will use the pull request template to create a well-structured PR.

### GitHub Templates

The `.github` directory contains templates that are automatically used by GitHub when creating new issues and pull requests. These templates are also used by the Gemini commands to create a consistent and structured workflow.

-   **Issue Templates**: Located in the `.github/ISSUE_TEMPLATE` directory, these templates provide a starting point for creating different types of issues:
    -   **`bug_report.md`**: Use this template to create a detailed bug report. It includes sections for describing the bug, how to reproduce it, and the expected behavior.
    -   **`feature_request.md`**: When you have an idea for a new feature, use this template to create a feature request. It includes sections for describing the feature, the problem it solves, and any alternative solutions.
    -   **`developer_task.md`**: This template is for creating a developer task. It includes sections for describing the task, the acceptance criteria, and any technical details.

-   **Pull Request Template**: The `.github/pull_request_template.md` file is used when creating a new pull request. It helps you create a detailed PR with sections for describing the changes, linking to related issues, and explaining how to test the changes. The `/pr:create` command uses this template to pre-populate the pull request with information from your git history.

## 🚀 How to Use

Here’s a walkthrough of how to use the Gemini CLI GitHub Extensions to streamline your development workflow. This guide is for both new and experienced developers.

### Workflow Example: From Issue to Pull Request

This example shows how to use the commands to resolve a GitHub issue and create a pull request.

**1. Start with an Issue**

Let's say you want to work on GitHub issue #42. You can use the `/issue:resolve` command to get started.

```bash
> /issue:resolve 42
```

Gemini will analyze the issue and create a detailed implementation plan. The plan will be saved as a markdown file in the `docs/planning/` directory.

**2. Implement the Plan**

Once you have the plan, you can use the `/implement` command to start coding. Gemini will guide you through the implementation, one step at a time.

```bash
> /implement @docs/planning/issue-42-plan.md
```

**3. Create a Pull Request**

After you have implemented the plan and committed your changes, you can use the `/pr:create` command to create a pull request. Gemini will pre-populate the pull request with information from your git history and the pull request template.

```bash
> /pr:create
```

### Alternative Workflow: Planning a New Feature

If you are not starting from an issue, you can use the `/planning:new` command to create a plan for a new feature.

```bash
> /planning:new "Implement a new login page with passwordless authentication"
```

This will generate a plan that you can then use with the `/implement` command.

### Creating a New Issue

You can also create a new issue directly from your terminal using the `/issue:create` command.

```bash
> /issue:create "The login button is not working on the mobile app"
```

Gemini will guide you through the process of creating a well-structured issue using the templates in the `.github/ISSUE_TEMPLATE` directory.

---

## 📚 Documentation

For more information on creating your own Gemini CLI extensions, check out the official documentation:

-   [**Gemini CLI Extensions**](https://github.com/google-gemini/gemini-cli/blob/main/docs/extension.md)
-   [**GitHub Template Docs**](https://docs.github.com/en/communities/using-templates-to-encourage-useful-issues-and-pull-requests/about-issue-and-pull-request-templates)

---

Happy coding! 🎉
