[![banner](https://raw.githubusercontent.com/nevermined-io/assets/main/images/logo/banner_logo.png)](https://nevermined.io)
[![Testing](https://github.com/nevermined-io/nvm-tools-actions/actions/workflows/testing.yml/badge.svg)](https://github.com/nevermined-io/nvm-tools-actions/actions/workflows/testing.yml)

# nvm-tools-actions

This action starts a Nevermined local development cluster for use in the github CI.

When using this action the `nvm-tools` command will also be available to all steps.

## Usage

```yaml
- uses: nevermined-io/nvm-tools-actions@v0.1.0
  with:
    # Github personal access token with read access to private nevermined-io organization repos
    # Required: true
    token: ""

    # Contracts version to use.
    # Default: 'latest'
    # Required: false
    contracts-version: ""

    # Node version to use.
    # Default: 'latest'
    # Required: false
    node-version: ""

    # Marketplace-api version to use.
    # Default: 'latest'
    # Required: false
    marketplace-version: ""
```

## Scenarios

- [Use latest version of all nevermined components](#Use-latest-version-of-all-nevermined-components)
- [Use development version of nevermined contracts](#Use-development-version-of-nevermined-contracts)

### Use latest version of all nevermined components

```yaml
- uses: nevermined-io/nvm-tools-actions@v0.1.0
  with:
    token: ${{ secrets.API_TOKEN_GITHUB }}

- name: Copy artifacts
  run: nvm-tools copy-artifacts ./artifacts
```

### Use development version of nevermined contracts

```yaml
- uses: nevermined-io/nvm-tools-actions@v0.1.0
  with:
    token: ${{ secrets.API_TOKEN_GITHUB }}
    contracts-version: "development"
```
