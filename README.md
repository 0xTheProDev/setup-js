<!-- markdownlint-configure-file { "MD033": false } -->

# setup-js

[![License](https://img.shields.io/github/license/0xTheProDev/setup-js?style=for-the-badge&label=license)](https://github.com/0xTheProDev/setup-js/blob/main/LICENSE)
[![Open Issues](https://img.shields.io/github/issues-raw/0xTheProDev/setup-js?style=for-the-badge)](https://github.com/0xTheProDev/setup-js/issues)
[![Closed Issues](https://img.shields.io/github/issues-closed-raw/0xTheProDev/setup-js?style=for-the-badge)](https://github.com/0xTheProDev/setup-js/issues?q=is%3Aissue+is%3Aclosed)
[![Open Pulls](https://img.shields.io/github/issues-pr-raw/0xTheProDev/setup-js?style=for-the-badge)](https://github.com/0xTheProDev/setup-js/pulls)
[![Closed Pulls](https://img.shields.io/github/issues-pr-closed-raw/0xTheProDev/setup-js?style=for-the-badge)](https://github.com/0xTheProDev/setup-js/pulls?q=is%3Apr+is%3Aclosed)
[![Contributors](https://img.shields.io/github/contributors/0xTheProDev/setup-js?style=for-the-badge)](https://github.com/0xTheProDev/setup-js/graphs/contributors)
[![Activity](https://img.shields.io/github/last-commit/0xTheProDev/setup-js?style=for-the-badge&label=most%20recent%20activity)](https://github.com/0xTheProDev/setup-js/pulse)

## Description

Github Action to Setup Workspace with appropriate Runtime and Package Manager, along with Project dependencies for JavaScript and TypeScript projects.

## Usage

- **Setup Basic NPM workspace:**

```yaml
---
name: Test

on:
  push:
    branches:
      - main
  pull_request:
  workflow_dispatch:

concurrency: ${{ github.workflow }}-${{ github.ref }}

permissions:
  contents: read

jobs:
  test:
    runs-on: ubuntu-latest
    steps:
      - name: Checkout
        uses: actions/checkout@v4

      - name: Setup Workspace
        uses: 0xTheProDev/setup-js@v1
```

- **Setup Specific Node Version (v22.x):**

```yaml
---
name: Test

on:
  push:
    branches:
      - main
  pull_request:
  workflow_dispatch:

concurrency: ${{ github.workflow }}-${{ github.ref }}

permissions:
  contents: read

jobs:
  test:
    runs-on: ubuntu-latest
    steps:
      - name: Checkout
        uses: actions/checkout@v4

      - name: Setup Workspace
        uses: 0xTheProDev/setup-js@v1
        with:
          version: 22.x
```

- **Setup Specific Node Version (read from .nvmrc):**

```yaml
---
name: Test

on:
  push:
    branches:
      - main
  pull_request:
  workflow_dispatch:

concurrency: ${{ github.workflow }}-${{ github.ref }}

permissions:
  contents: read

jobs:
  test:
    runs-on: ubuntu-latest
    steps:
      - name: Checkout
        uses: actions/checkout@v4

      - name: Setup Workspace
        uses: 0xTheProDev/setup-js@v1
        with:
          version-file: .nvmrc
```

- **Setup Yarn Workspace:**

```yaml
---
name: Test

on:
  push:
    branches:
      - main
  pull_request:
  workflow_dispatch:

concurrency: ${{ github.workflow }}-${{ github.ref }}

permissions:
  contents: read

jobs:
  test:
    runs-on: ubuntu-latest
    steps:
      - name: Checkout
        uses: actions/checkout@v4

      - name: Setup Workspace
        uses: 0xTheProDev/setup-js@v1
        with:
          cache: yarn
```

- **Setup Pnpm Workspace:**

```yaml
---
name: Test

on:
  push:
    branches:
      - main
  pull_request:
  workflow_dispatch:

concurrency: ${{ github.workflow }}-${{ github.ref }}

permissions:
  contents: read

jobs:
  test:
    runs-on: ubuntu-latest
    steps:
      - name: Checkout
        uses: actions/checkout@v4

      - name: Setup Workspace
        uses: 0xTheProDev/setup-js@v1
        with:
          cache: pnpm
```

- **Setup Bun Workspace (only Package Manager):**

```yaml
---
name: Test

on:
  push:
    branches:
      - main
  pull_request:
  workflow_dispatch:

concurrency: ${{ github.workflow }}-${{ github.ref }}

permissions:
  contents: read

jobs:
  test:
    runs-on: ubuntu-latest
    steps:
      - name: Checkout
        uses: actions/checkout@v4

      - name: Setup Workspace
        uses: 0xTheProDev/setup-js@v1
        with:
          cache: bun
```

- **Setup Specific Bun Version (v1.x, only Package Manager):**

```yaml
---
name: Test

on:
  push:
    branches:
      - main
  pull_request:
  workflow_dispatch:

concurrency: ${{ github.workflow }}-${{ github.ref }}

permissions:
  contents: read

jobs:
  test:
    runs-on: ubuntu-latest
    steps:
      - name: Checkout
        uses: actions/checkout@v4

      - name: Setup Workspace
        uses: 0xTheProDev/setup-js@v1
        with:
          cache: bun
          cache-version: 1.x
```

- **Setup Specific Bun Version (read from .bun-version, only Package Manager):**

```yaml
---
name: Test

on:
  push:
    branches:
      - main
  pull_request:
  workflow_dispatch:

concurrency: ${{ github.workflow }}-${{ github.ref }}

permissions:
  contents: read

jobs:
  test:
    runs-on: ubuntu-latest
    steps:
      - name: Checkout
        uses: actions/checkout@v4

      - name: Setup Workspace
        uses: 0xTheProDev/setup-js@v1
        with:
          cache: bun
          cache-version-file: .bun-version
```

- **Setup Bun Workspace:**

```yaml
---
name: Test

on:
  push:
    branches:
      - main
  pull_request:
  workflow_dispatch:

concurrency: ${{ github.workflow }}-${{ github.ref }}

permissions:
  contents: read

jobs:
  test:
    runs-on: ubuntu-latest
    steps:
      - name: Checkout
        uses: actions/checkout@v4

      - name: Setup Workspace
        uses: 0xTheProDev/setup-js@v1
        with:
          runtime: bun
```

- **Setup Specific Bun Version (v1.x):**

```yaml
---
name: Test

on:
  push:
    branches:
      - main
  pull_request:
  workflow_dispatch:

concurrency: ${{ github.workflow }}-${{ github.ref }}

permissions:
  contents: read

jobs:
  test:
    runs-on: ubuntu-latest
    steps:
      - name: Checkout
        uses: actions/checkout@v4

      - name: Setup Workspace
        uses: 0xTheProDev/setup-js@v1
        with:
          runtime: bun
          version: 1.x
```

- **Setup Specific Bun Version (read from .bun-version):**

```yaml
---
name: Test

on:
  push:
    branches:
      - main
  pull_request:
  workflow_dispatch:

concurrency: ${{ github.workflow }}-${{ github.ref }}

permissions:
  contents: read

jobs:
  test:
    runs-on: ubuntu-latest
    steps:
      - name: Checkout
        uses: actions/checkout@v4

      - name: Setup Workspace
        uses: 0xTheProDev/setup-js@v1
        with:
          runtime: bun
          version-file: .bun-version
```

## Reporting a Bug

Head on to [**Discussion**](https://github.com/0xTheProDev/setup-js/discussions) section to report a bug or to ask for any feature. Feel to add your queries about using this library as well under _Q & A_ section of it. Remember, do not create any Issues by yourself, maintainers of this repository will open one if deemed necessary.

## Changelog

See [CHANGELOG](https://github.com/0xTheProDev/setup-js/blob/main/.github/CHANGELOG.md) for more details on what has been changed in the latest release.

## Contributing

See [Contributing Guidelines](https://github.com/0xTheProDev/setup-js/blob/main/.github/CONTRIBUTING.md).

## License

This project is licensed under the terms of the MIT license, see [LICENSE](https://github.com/0xTheProDev/setup-js/blob/main/LICENSE) for more details.

<a href="https://github.com/0xTheProDev">
  <img src=".github/assets/the-pro-dev-original.png" alt="The Pro Dev" height="120" width="120"/>
</a>
