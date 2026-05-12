Unit V:

Continuous Integration (CI) with GitHub Actions
1. Introduction to Continuous Integration (CI)
What is Continuous Integration?

Continuous Integration (CI) is a software development practice where developers frequently merge their code changes into a shared repository. After every change, automated processes such as build, testing, and deployment are executed.

Goal of CI
Detect errors early
Improve code quality
Automate repetitive tasks
Speed up software development
Example

When a developer pushes code to GitHub:

Code is automatically compiled
Tests are executed
Errors are reported immediately
2. GitHub Actions
What is GitHub Actions?

GitHub Actions is a CI/CD automation tool provided by GitHub.

It allows developers to automate:

Building applications
Running tests
Deploying applications
Sending notifications
Managing workflows directly from GitHub repositories
3. Understanding Workflow Automation
Workflow Automation

Workflow automation means automatically performing tasks whenever a specific event occurs.

Example Tasks
Run tests after code push
Deploy website after successful build
Send email notifications
Check coding standards
Benefits
Saves time
Reduces manual work
Improves reliability
Faster development cycle
4. Events and Triggers
What are Events?

Events are activities that happen in a GitHub repository.

Examples of Events
Code push
Pull request creation
Issue creation
Scheduled time event
What are Triggers?

Triggers tell GitHub Actions when to run a workflow.

Syntax Example
on: push

This means:

Run workflow whenever code is pushed.
5. Workflow Directory Structure

GitHub Actions workflows are stored inside a special folder.

Directory Structure
Repository/
│
├── .github/
│     └── workflows/
│            └── main.yml
Explanation
.github → Special GitHub folder
workflows → Contains workflow files
.yml files → Workflow configuration files
6. Key Components of GitHub Actions
A. Workflows
Definition

A workflow is an automated process defined in a YAML file.

Features
Contains jobs
Runs automatically after triggers
Stored inside .github/workflows
Example
name: CI Workflow

on: push
B. Jobs
Definition

A job is a set of steps executed on the same runner.

Features
Workflows can contain multiple jobs
Jobs may run:
Sequentially
In parallel
Example
jobs:
  build:
C. Steps
Definition

Steps are individual tasks inside a job.

Examples
Install dependencies
Compile code
Run tests
Example
steps:
  - name: Checkout Code
D. Actions
Definition

Actions are reusable units of code used in workflows.

Purpose

They help automate common tasks.

Examples
Checkout repository
Setup Node.js
Upload artifacts
Example
uses: actions/checkout@v4
E. Runners
Definition

A runner is a server that executes workflows.

Types of Runners
GitHub-hosted runners
Self-hosted runners
Common Operating Systems
Ubuntu
Windows
macOS
Example
runs-on: ubuntu-latest
7. Workflow Triggers
A. Push Trigger
Definition

Runs workflow whenever code is pushed to repository.

Example
on:
  push:
Use Case
Automatic testing after code update
B. Pull Request Trigger
Definition

Runs workflow when a pull request is created or updated.

Example
on:
  pull_request:
Use Case
Verify code before merging
C. Schedule Trigger
Definition

Runs workflow automatically at scheduled times using cron syntax.

Example
on:
  schedule:
    - cron: '0 0 * * *'
Meaning
Runs every day at midnight
Use Cases
Daily backups
Automated reports
Scheduled testing
8. Complete Example Workflow
name: CI Example

on:
  push:
  pull_request:
  schedule:
    - cron: '0 0 * * *'

jobs:
  build:
    runs-on: ubuntu-latest

    steps:
      - name: Checkout Repository
        uses: actions/checkout@v4

      - name: Display Message
        run: echo "GitHub Actions Workflow Running"
9. Advantages of GitHub Actions
Easy integration with GitHub
Supports CI/CD
Automation of repetitive tasks
Faster software delivery
Supports multiple platforms
Large marketplace of actions
10. Summary
Component	Purpose
Workflow	Complete automation process
Job	Group of steps
Step	Individual task
Action	Reusable automation unit
Runner	Machine executing workflow
Trigger	Event starting workflow