# Git Flow

This document describes the Git Flow workflow used in this project. Git Flow is a branching model that helps organize and manage software development.

## Main Branches

### Main
- **Description**: The `main` branch is the production branch. It contains stable code that has been fully tested and is ready for release.
- **Usage**: Only for stable releases and final versions.
- **Naming**: `main`

### Homolog
- **Description**: The `homolog` branch is used for homologation testing. It is a nearly production-ready copy that allows for validation before release.
- **Usage**: For deployment in the homologation environment where final tests are conducted.
- **Naming**: `homolog`

### Develop
- **Description**: The `develop` branch is the main development branch. All new features and fixes are integrated here before being pushed to `homolog` and `main`.
- **Usage**: For integrating new features and fixes.
- **Naming**: `develop`

## Supporting Branches

### Feature Branches
- **Description**: Used to develop new features that are still in progress.
- **Usage**: Created from `develop` and merged back into `develop` when the feature is complete.
- **Naming**: `feature/<feature-name>`
- **Example**: `feature/database-postgres-init`

### Bugfix Branches
- **Description**: Used to fix bugs in the `develop` branch.
- **Usage**: Created from `develop` and merged back into `develop` after the bug is fixed.
- **Naming**: `bugfix/<bug-name>`
- **Example**: `bugfix/login-error`

### Release Branches
- **Description**: Used to prepare a new production release. They allow for minor bug fixes and preparing meta-data for a release.
- **Usage**: Created from `develop` and merged into both `main` and `develop` after completion.
- **Naming**: `release/<version>`
- **Example**: `release/1.0.0`

### Hotfix Branches
- **Description**: Used to quickly fix production bugs. They bypass the `develop` branch.
- **Usage**: Created from `main` and merged back into both `main` and `develop`.
- **Naming**: `hotfix/<hotfix-name>`
- **Example**: `hotfix/critical-login-issue`

### Support Branches
- **Description**: Used to maintain and fix issues in older versions of the software.
- **Usage**: Created from a specific tag on the `main` branch and merged back into `main` after the fix.
- **Naming**: `support/<version>`
- **Example**: `support/1.0.x`
<!-- 
## Branch Workflow

1. **Creating a New Branch**
   ```bash
   git checkout -b feature/<feature-name> develop

2. **Committing Changes**

```bash
Copy code
git add .
git commit -m ":sparkles: feature(<feature-name>): Add new feature"
Pushing the Branch

bash
Copy code
git push --set-upstream origin feature/<feature-name>
Merging a Branch

**Feature/Bugfix to Develop**

bash
Copy code
git checkout develop
git merge feature/<feature-name>
Release to Main and Develop

bash
Copy code
git checkout main
git merge release/<version>
git checkout develop
git merge release/<version>
Hotfix to Main and Develop

bash
Copy code
git checkout main
git merge hotfix/<hotfix-name>
git checkout develop
git merge hotfix/<hotfix-name>

**Commit Message Conventions**
Use emojis and structured messages for commits to maintain readability and consistency.

New Feature: :sparkles: feature(<module>): Description
Bug Fix: :bug: fix(<module>): Description
Refactor: :art: refactor(<module>): Description
Documentation: :memo: docs(<module>): Description
Configuration: :wrench: config(<module>): Description
Dependencies: :package: deps(<module>): Description
Example Commits
bash
Copy code
git commit -m ":sparkles: feature(database): Add PostgreSQL support"
git commit -m ":bug: fix(auth): Resolve login error"
git commit -m ":memo: docs: Update README with setup instructions"
Git Flow Diagram
Below is a visual representation of the Git Flow process, showing how new branches are created and merged.

plaintext
Copy code
*---*------------------------*-------------------* Main
    |                        |
    *----*-------------------*-------------------* Homolog
         |                   |
         *----*-------------*-------------------* Develop
              |             |
              *----*--------*-------------------* Feature (feature/database-postgres-init)
Main: The main branch for production.
Homolog: The branch for homologation testing, created from main.
Develop: The main development branch, created from homolog.
Feature: New feature branches, created from develop. -->
