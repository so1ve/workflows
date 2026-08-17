# so1ve/workflows

A collection of reusable GitHub Actions workflows and actions for Ray's projects.

> Adapted from [sxzz/workflows](https://github.com/sxzz/workflows)

## Features

- Standardized CI/CD workflows for testing, building, and releasing
- Easy integration into any TypeScript or Rust repository
- Includes custom actions for setup and automation

## Included Workflows

### JavaScript/TypeScript

- **Conventional CI**: Runs typecheck, lint, and tests with configurable Node.js versions
- **autofix.ci**: Automatically fixes code style issues via a commit
- **Release**: Publishes releases to npm/JSR
- **Release to JSR**: Publishes releases specifically to JSR
- **Release Commit to pkg.pr.new**: Releases any commit as a package to pkg.pr.new
- **Lock Threads**: Automatically locks closed issues after a period of inactivity
- **Upload code coverage to Codecov**: Uploads code coverage reports to Codecov

### Rust

- **Rust CI**: Runs rustfmt, clippy, and tests with configurable toolchain
- **Rust Release**: Publishes releases using release-plz
- **Rust autofix.ci**: Automatically fixes code style issues via a commit

## Usage

To use a workflow, reference it in your project’s `.github/workflows/*.yml`:

```yaml
# Example: Conventional CI
jobs:
  ci:
    uses: so1ve/workflows/.github/workflows/conventional-ci.yml@v1
```

### Custom Rust CI setup

Rust CI can run arbitrary caller-defined setup steps before linting and testing. Create a [composite action](https://docs.github.com/en/actions/sharing-automations/creating-actions/creating-a-composite-action) in the caller repository, then pass its directory through the `setup` input:

```yaml
jobs:
  ci:
    uses: so1ve/workflows/.github/workflows/rust-ci.yml@v1
    with:
      setup: .github/actions/setup-rust-ci
```

See the example workflow configurations in the [`examples/`](./examples) folder:

### JavaScript/TypeScript

- [Conventional CI](./examples/conventional-ci.yml)
- [autofix.ci](./examples/autofix-ci.yml)
- [Release](./examples/release.yml)
- [Release Commit to pkg.pr.new](./examples/release-commit.yml)
- [Lock Threads](./examples/lock.yml)
- [Upload code coverage to Codecov](./examples/coverage.yml)

### Rust

- [Rust CI](./examples/rust-ci.yml)
- [Rust Release](./examples/rust-release.yml)
- [Rust autofix.ci](./examples/rust-autofix-ci.yml)

For more details, see the workflow definitions in the [`.github/workflows/`](./.github/workflows) folder.

## Actions

- [`setup-js/action.yml`](./setup-js/action.yml): Sets up Node.js and installs dependencies
- [`setup-rust/action.yml`](./setup-rust/action.yml): Sets up Rust toolchain with cargo cache

## License

[MIT](./LICENSE) License © 2025-PRESENT [Ray](https://github.com/so1ve)
