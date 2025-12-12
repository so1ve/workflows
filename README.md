# so1ve/workflows

A collection of reusable GitHub Actions workflows and actions for TypeScript projects.

> Adapted from [sxzz/workflows](https://github.com/sxzz/workflows)

## Features

- Standardized CI/CD workflows for testing, building, and releasing
- Easy integration into any TypeScript repository
- Includes custom actions for setup and automation

## Included Workflows

- **Conventional CI**: Runs typecheck, lint, and tests with configurable Node.js versions
- **autofix.ci**: Automatically fixes code style issues via a commit
- **Release**: Publishes releases to npm/JSR
- **Release to JSR**: Publishes releases specifically to JSR
- **Release Commit to pkg.pr.new**: Releases any commit as a package to pkg.pr.new
- **Lock Threads**: Automatically locks closed issues after a period of inactivity
- **Upload code coverage to Codecov**: Uploads code coverage reports to Codecov

## Usage

To use a workflow, reference it in your project’s `.github/workflows/*.yml`:

```yaml
# Example: Conventional CI
uses: so1ve/workflows/.github/workflows/conventional-ci.yml@v1
```

See the workflows in the [`.github/workflows/`](./.github/workflows) folder for configuration details.

## Actions

- [`setup-js/action.yml`](./setup-js/action.yml): Sets up Node.js and installs dependencies

## License

[MIT](./LICENSE) License © 2025-PRESENT [Ray](https://github.com/so1ve)
