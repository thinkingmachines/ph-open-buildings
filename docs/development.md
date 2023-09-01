# Development Lifecycle

``` @TODO: Replace Example with your Team's Dev Workflow ```

## Trunk Based Development

![Trunk Based Development](https://trunkbaseddevelopment.com/trunk1b.png)

The github-starter project follows the concept of Trunk-based Development, wherein User Stories are worked on PRs. PRs then get merged to `master` once approved by the team.

The master branch serves as the most up-to-date version of the code base. For releases, whenever we deploy, we create a `release/<version>` branch, which is based off of `master` at a given point in time, and serves as the branch to be deployed

### Naming Format

``` @TODO: Update according to Team's agreement ```

**Branch Names:**
- To `<dev>` Branch:
    - `feature/<issue-id>-<header>`
    - `fix/<issue-id>-<header>`
- To `<prod/master>` Branch:
    - `release/<version>`
    - `release/<version>-<hotfix>`

**PR Title:** `[<Feature/Fix/Release/Hotfix>](<issue-id>) <Short desc>`

**PR Template:** [pull_request_template.md](../.github/pull_request_template.md)

### Development Workflow
``` @TODO: Development workflow being used by the devs. Eg: Make changes in local, push to dev for testing, make a PR, deploy after merging```

## Local Development
``` Note: This should contain all information for new devs to set up and make changes```
### File Structure Walkthrough
``` @TODO: Fill with a brief walkthrough of the codebase ```
- `docs/` - This folder contains all Markdown files for creating Backstage TechDocs.
- `infra/` - This folder contains all infra definitions through Terraform.

### Pre-requisites
``` @TODO: Fill with pre-reqs such as access to Cloud Platform, Bitwarden Collection, Github etc ```

### Cloning and Installation
``` @TODO: Fill with set-up/installation guide. Feel free to subdivide to sections or multiple MD files through mkdocs.yml ```

### Environment Setup
``` @TODO: Fill with instructions for exporting local env variables. Distinguish variables being used in local vs dev vs prod ```

### Running the Application
``` @TODO: Fill with steps on running the app locally.  Feel free to subdivide to sections or multiple MD files through mkdocs.yml ```
