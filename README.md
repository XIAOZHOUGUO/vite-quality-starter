# vite-quality-starter

This is a starter template for a Vite project with Vue.js and TypeScript, pre-configured with quality tools to ensure code consistency and maintainability.

## Included Tools

- **Vite**: A next-generation frontend tooling that is fast and lean.
- **Vue.js + TypeScript**: A progressive framework for building user interfaces, with the safety of types.
- **ESLint with @antfu/eslint-config**: A powerful and flexible linter with a comprehensive and opinionated configuration.
- **Husky**: A tool that makes it easy to work with Git hooks.
- **lint-staged**: A tool to run linters on staged files before committing.
- **Commitizen**: A tool to create conventional commit messages.

## IDE Support

It is recommended to use the [VS Code ESLint extension](https://marketplace.visualstudio.com/items?itemName=dbaeumer.vscode-eslint) for the best development experience.

This project includes a recommended VS Code settings file at `.vscode/settings.json` that will:

- Enable ESLint for all supported file types.
- Disable the default formatter in favor of ESLint.
- Enable auto-fixing of ESLint errors on save.

## Getting Started

1. **Install dependencies**:
   ```bash
   pnpm install
   ```

2. **Run the development server**:
   ```bash
   pnpm dev
   ```

## Quality Tools

### ESLint

This project uses `@antfu/eslint-config` for ESLint configuration. You can run the linter with the following commands:

- `pnpm lint`: Check for linting errors.
- `pnpm lint:fix`: Automatically fix linting errors.

The configuration can be found in `eslint.config.js`.

### Husky and lint-staged

Husky is used to manage Git hooks. A `pre-commit` hook is configured to run `lint-staged`, which in turn runs ESLint on staged files. This ensures that no code with linting errors can be committed.

### Commitizen

Commitizen is used to enforce conventional commit messages. To use it, run the following command instead of `git commit`:

```bash
git cz
```

This will prompt you with a series of questions to generate a conventional commit message. For more details on the commit message format, please refer to the [Conventional Commits](https://www.conventionalcommits.org/) specification.

In short, the format is:

```
<type>[optional scope]: <description>

[optional body]

[optional footer(s)]
```

- **type**: Represents the type of commit, e.g., `feat` (new feature), `fix` (bug fix), `docs` (documentation), `style` (code style), `refactor` (code refactoring), `test` (tests), `chore` (changes to the build process or auxiliary tools).
- **scope**: (Optional) Represents the scope of this change, e.g., `button`, `login`, `core`.
- **description**: A short description of the change.

A `commit-msg` hook is also configured to validate the commit message format.

Here is an example of a valid commit message:

```text
feat(button): add new ripple effect

- Add a new ripple effect to the button component.
- The effect is triggered on click.
```
