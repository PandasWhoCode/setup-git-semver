# setup-git-semver

A GitHub Action to set up the [git-semver](https://github.com/PSanetra/git-semver) tool in your GitHub workflows. This action installs and configures `git-semver` for versioning and semantic versioning tasks, allowing you to use it seamlessly in your CI/CD pipeline.
The latest version uses [andrewb1269hg/git-semver](https://github.com/andrewb1269hg/git-semver)

## Usage

You can use this action in your GitHub workflow to set up `git-semver`. Below is an example of how to use the action:

### Basic Example

```yaml
name: Set up Git-Semver

on:
  push:
    branches:
      - main
  workflow_dispatch:

jobs:
  setup-git-semver:
    runs-on: ubuntu-latest

    steps:
      - name: Checkout code
        uses: actions/checkout@v2

      - name: Set up git-semver
        uses: DJ-BBot/setup-git-semver@v1
        with:
          version: 'latest'

      - name: Use git-semver
        run: git-semver
