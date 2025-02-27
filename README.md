# actions

## `conventional-commits`

Checks if the PR title follows the [Conventional Commits](https://www.conventionalcommits.org/en/v1.0.0/).

```yaml
on:
  pull_request:
    types:
      - opened
      - reopened
      - edited
      - synchronize

jobs:
  pr-title:
    runs-on: ubuntu-latest
    permissions:
      contents: read
      id-token: write
      packages: read
      pull-requests: write
      statuses: write
    steps:
      - uses: sethrylan/actions/conventional-commits@main
```
