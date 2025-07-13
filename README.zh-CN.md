
# vite-quality-starter

这是一个 Vite 入门模板，集成了 Vue.js 和 TypeScript，并预先配置了多种代码质量工具，以确保代码的一致性和可维护性。

## 集成工具

- **Vite**: 新一代前端构建工具，快速、轻量。
- **Vue.js + TypeScript**: 用于构建用户界面的渐进式框架，并具备类型安全。
- **ESLint (使用 @antfu/eslint-config)**: 功能强大且灵活的 Linter，提供全面且主观的配置。
- **Husky**: 让使用 Git 钩子变得简单的工具。
- **lint-staged**: 在提交前对暂存文件运行 Linter 的工具。
- **Commitizen**: 用于创建规范化提交信息的工具。

## IDE 支持

为了获得最佳的开发体验，推荐使用 [VS Code ESLint 扩展](https://marketplace.visualstudio.com/items?itemName=dbaeumer.vscode-eslint)。

本项目在 `.vscode/settings.json` 中包含了推荐的 VS Code 设置，它将：

- 为所有支持的文件类型启用 ESLint。
- 禁用默认格式化程序，以 ESLint 为准。
- 启用保存时自动修复 ESLint 错误。

## 快速上手

1. **安装依赖**:
   ```bash
   pnpm install
   ```

2. **运行开发服务器**:
   ```bash
   pnpm dev
   ```

## 代码质量工具

### ESLint

本项目使用 `@antfu/eslint-config` 作为 ESLint 配置。你可以使用以下命令运行 Linter：

- `pnpm lint`: 检查代码规范问题。
- `pnpm lint:fix`: 自动修复代码规范问题。

配置文件位于 `eslint.config.js`。

### Husky 和 lint-staged

Husky 用于管理 Git 钩子。项目中配置了一个 `pre-commit` 钩子，它会在你提交代码前运行 `lint-staged`。`lint-staged` 会对暂存区的文件运行 ESLint，确保不符合规范的代码不会被提交。

### Commitizen

Commitizen 用于强制使用规范化的提交信息。请使用以下命令替代 `git commit`：

```bash
git cz
```

该命令会通过一系列交互式问题，引导你生成符合规范的提交信息。关于提交信息格式的更多细节，请参考 [Conventional Commits](https://www.conventionalcommits.org/) 规范。

简单来说，格式如下：

```
<type>[optional scope]: <description>

[optional body]

[optional footer(s)]
```

- **type**: 代表提交的类型，如 `feat` (新功能), `fix` (修复bug), `docs` (文档), `style` (代码格式), `refactor` (重构), `test` (测试), `chore` (构建过程或辅助工具的变动) 等。
- **scope**: (可选) 代表本次改动影响的范围，比如 `button`, `login`, `core` 等。
- **description**: 对本次改动的简短描述。

此外，项目还配置了 `commit-msg` 钩子，用于校验提交信息的格式。

以下是一个有效的提交信息示例：

```
feat(button): 添加新的波纹效果

- 为按钮组件添加新的波纹效果。
- 该效果在点击时触发。
```
