# ci-templates

Reusable GitHub Actions workflows for my projects.

## Workflows

### `docker-ci.yaml`

Builds a Docker image, runs tests inside it and, on a new release, publishes the image to GHCR.

```yaml
name: CI
on:
  push:
    branches: [main]
  pull_request:

permissions:
  contents: write
  pull-requests: write
  packages: write

jobs:
  ci:
    uses: drewg3r/ci-templates/.github/workflows/docker-ci.yaml@main
    with:
      test-command: "pytest"
      # context: "."  # optional, Docker build context
```
