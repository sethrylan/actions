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
      pull-requests: write
    steps:
      - uses: sethrylan/actions/conventional-commits@main
```


## `transistor-subscribers`

Checks if every transistor subscriber to a show is a GitHub organization member.

```yaml
jobs:
  check-org-members:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - uses: sethrylan/actions/transistor-subscriber-check@main
        with:
          github_token: ${{ secrets.ORG_PAT }}
          api_key: ${{ secrets.TRANSISTOR_API_KEY }}
          show_id: my-show-id
          organization: my-org-id
```
