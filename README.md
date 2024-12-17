# Bundle Audit Check Action

This is a GitHub action that runs `bundle-audit check --update`, and then, if vulnerabilities are detected, fail the current check. It's recommended to run it when a PR is modified and contains changes to `Gemfile.lock`.

## Example usage

```
name: PR Bundler Audit

on:
  pull_request:
    types: [opened, synchronize]
    paths:
      - 'Gemfile.lock'

jobs:
  bundle-audit:
    runs-on: ubuntu-latest

    steps:
      - name: Run PR Bundle Audit Action
        uses: planningcenter/bundle-audit-check-action@v1
```
