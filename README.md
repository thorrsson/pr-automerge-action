# Pull Request auto merge action
[![](https://github.com/thorrsson/pr-automerge-action/workflows/Node.js%20CI/badge.svg)](https://github.com/thorrsson/pr-automerge-action/actions?query=workflow%3A%22Node.js+CI%22) [![Maintainability](https://api.codeclimate.com/v1/badges/60f9b3a6b4177a0bfe77/maintainability)](https://codeclimate.com/github/thorrsson/pr-automerge-action/maintainability)

GitHub Action to automatically merge pull requests.

## Inputs

### merge-method

Pull request merge method: "merge", "squash", "rebase". Default is "squash".

### base-ref

Base ref branch to filter pull requests. Default is "dev".

## Example usage

```yaml
name: PRs auto merge

on:
  schedule:
    # Every friday every hour between 12 and 15 UTC
    - cron: "0 12-15 * * 5"

jobs:
  pr-automerge:
    runs-on: ubuntu-latest
    steps:
    - uses: thorrsson/pr-automerge-action@v1.1.0
      env:
        GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
      with:
        merge-method: 'squash' # Default 'squash'
        base-ref: 'dev' # Default 'dev'
```

## Bug or feedback?
Please open an issue.

## Authors
- [thorrsson](https://github.com/thorrsson)
- [Davide Violante](https://github.com/DavideViolante)