---
name: opencode-conventions
description: Development conventions and patterns for opencode. TypeScript Hono project with conventional commits.
---

# Opencode Conventions

> Generated from [bufanliu/opencode](https://github.com/bufanliu/opencode) on 2026-03-20

## Overview

This skill teaches Claude the development patterns and conventions used in opencode.

## Tech Stack

- **Primary Language**: TypeScript
- **Framework**: Hono
- **Architecture**: type-based module organization
- **Test Location**: mixed
- **Test Framework**: playwright

## When to Use This Skill

Activate this skill when:
- Making changes to this repository
- Adding new features following established patterns
- Writing tests that match project conventions
- Creating commits with proper message format

## Commit Conventions

Follow these commit message conventions based on 200 analyzed commits.

### Commit Style: Conventional Commits

### Prefixes Used

- `fix`
- `chore`
- `refactor`
- `feat`
- `zen`
- `tweak`
- `docs`
- `app`

### Message Guidelines

- Average message length: ~47 characters
- Keep first line concise and descriptive
- Use imperative mood ("Add feature" not "Added feature")


*Commit message example*

```text
tweak: adjust codex plugin logic so that codex instruction isn't always added (oauth plan no longer enforces instruction whitelisting) (#18337)
```

*Commit message example*

```text
docs: add Cloudflare Workers AI provider (#18322)
```

*Commit message example*

```text
app: file type filter on desktop + multiple files (#18403)
```

*Commit message example*

```text
fix(app): align review file comments with diff comments (#18406)
```

*Commit message example*

```text
chore: update nix node_modules hashes
```

*Commit message example*

```text
deslopity deslopity (#18343)
```

*Commit message example*

```text
patch solid to try fix memo undefined under transition bug (#18338)
```

*Commit message example*

```text
fix: lots of desktop stability, better e2e error logging (#18300)
```

## Architecture

### Project Structure: Turborepo

This project uses **type-based** module organization.

### Configuration Files

- `.github/workflows/beta.yml`
- `.github/workflows/close-stale-prs.yml`
- `.github/workflows/compliance-close.yml`
- `.github/workflows/containers.yml`
- `.github/workflows/daily-issues-recap.yml`
- `.github/workflows/daily-pr-recap.yml`
- `.github/workflows/deploy.yml`
- `.github/workflows/docs-locale-sync.yml`
- `.github/workflows/docs-update.yml`
- `.github/workflows/duplicate-issues.yml`
- `.github/workflows/generate.yml`
- `.github/workflows/nix-eval.yml`
- `.github/workflows/nix-hashes.yml`
- `.github/workflows/notify-discord.yml`
- `.github/workflows/opencode.yml`
- `.github/workflows/pr-management.yml`
- `.github/workflows/pr-standards.yml`
- `.github/workflows/publish-github-action.yml`
- `.github/workflows/publish-vscode.yml`
- `.github/workflows/publish.yml`
- `.github/workflows/release-github-action.yml`
- `.github/workflows/review.yml`
- `.github/workflows/sign-cli.yml`
- `.github/workflows/stale-issues.yml`
- `.github/workflows/stats.yml`
- `.github/workflows/storybook.yml`
- `.github/workflows/sync-zed-extension.yml`
- `.github/workflows/test.yml`
- `.github/workflows/triage.yml`
- `.github/workflows/typecheck.yml`
- `.github/workflows/vouch-check-issue.yml`
- `.github/workflows/vouch-check-pr.yml`
- `.github/workflows/vouch-manage-by-issue.yml`
- `github/package.json`
- `github/tsconfig.json`
- `package.json`
- `packages/app/e2e/tsconfig.json`
- `packages/app/package.json`
- `packages/app/playwright.config.ts`
- `packages/app/tsconfig.json`
- `packages/app/vite.config.ts`
- `packages/console/app/package.json`
- `packages/console/app/tsconfig.json`
- `packages/console/app/vite.config.ts`
- `packages/console/core/drizzle.config.ts`
- `packages/console/core/package.json`
- `packages/console/core/tsconfig.json`
- `packages/console/function/package.json`
- `packages/console/function/tsconfig.json`
- `packages/console/mail/package.json`
- `packages/console/resource/package.json`
- `packages/console/resource/tsconfig.json`
- `packages/containers/base/Dockerfile`
- `packages/containers/bun-node/Dockerfile`
- `packages/containers/publish/Dockerfile`
- `packages/containers/rust/Dockerfile`
- `packages/containers/tauri-linux/Dockerfile`
- `packages/containers/tsconfig.json`
- `packages/desktop-electron/package.json`
- `packages/desktop-electron/tsconfig.json`
- `packages/desktop/package.json`
- `packages/desktop/tsconfig.json`
- `packages/desktop/vite.config.ts`
- `packages/enterprise/package.json`
- `packages/enterprise/tsconfig.json`
- `packages/enterprise/vite.config.ts`
- `packages/function/package.json`
- `packages/function/tsconfig.json`
- `packages/opencode/Dockerfile`
- `packages/opencode/drizzle.config.ts`
- `packages/opencode/package.json`
- `packages/opencode/src/cli/cmd/tui/context/theme/vercel.json`
- `packages/opencode/tsconfig.json`
- `packages/plugin/package.json`
- `packages/plugin/tsconfig.json`
- `packages/script/package.json`
- `packages/script/tsconfig.json`
- `packages/sdk/js/package.json`
- `packages/sdk/js/tsconfig.json`
- `packages/slack/package.json`
- `packages/slack/tsconfig.json`
- `packages/storybook/package.json`
- `packages/storybook/tsconfig.json`
- `packages/ui/package.json`
- `packages/ui/src/theme/themes/vercel.json`
- `packages/ui/tsconfig.json`
- `packages/ui/vite.config.ts`
- `packages/util/package.json`
- `packages/util/tsconfig.json`
- `packages/web/package.json`
- `packages/web/tsconfig.json`
- `sdks/vscode/package.json`
- `sdks/vscode/tsconfig.json`
- `tsconfig.json`

### Guidelines

- Group code by type (components, services, utils)
- Keep related functionality in the same type folder
- Avoid circular dependencies between type folders

## Code Style

### Language: TypeScript

### Naming Conventions

| Element | Convention |
|---------|------------|
| Files | camelCase |
| Functions | camelCase |
| Classes | PascalCase |
| Constants | SCREAMING_SNAKE_CASE |

### Import Style: Relative Imports

### Export Style: Named Exports


*Preferred import style*

```typescript
// Use relative imports
import { Button } from '../components/Button'
import { useAuth } from './hooks/useAuth'
```

*Preferred export style*

```typescript
// Use named exports
export function calculateTotal() { ... }
export const TAX_RATE = 0.1
export interface Order { ... }
```

## Testing

### Test Framework: playwright

### File Pattern: `*.test.ts`

### Test Types

- **Unit tests**: Test individual functions and components in isolation
- **Integration tests**: Test interactions between multiple components/services
- **E2e tests**: Test complete user flows through the application

### Coverage

This project has coverage reporting configured. Aim for 80%+ coverage.


## Error Handling

### Error Handling Style: Try-Catch Blocks


*Standard error handling pattern*

```typescript
try {
  const result = await riskyOperation()
  return result
} catch (error) {
  console.error('Operation failed:', error)
  throw new Error('User-friendly message')
}
```

## Common Workflows

These workflows were detected from analyzing commit patterns.

### Feature Development

Standard feature implementation workflow

**Frequency**: ~4 times per month

**Steps**:
1. Add feature implementation
2. Add tests for feature
3. Update documentation

**Files typically involved**:
- `packages/opencode/src/filesystem/*`
- `packages/opencode/src/skill/*`
- `packages/opencode/src/snapshot/*`
- `**/*.test.*`

**Example commit sequence**:
```
feat(filesystem): add AppFileSystem service, migrate Snapshot (#18138)
fix: restore recent test regressions and upgrade effect beta (#18158)
chore: update nix node_modules hashes
```

### Refactoring

Code refactoring and cleanup workflow

**Frequency**: ~2 times per month

**Steps**:
1. Ensure tests pass before refactor
2. Refactor code structure
3. Verify tests still pass

**Files typically involved**:
- `src/**/*`

**Example commit sequence**:
```
refactor: abstract SQLite behind runtime-conditional #db import (#18316)
refactor: replace Bun shell execution with portable Process utilities (#18318)
fix: include cache bin directory in which() lookups (#18320)
```

### Update Nix Node Modules Hashes

Keeps the Nix node_modules hashes up to date for reproducible builds.

**Frequency**: ~6 times per month

**Steps**:
1. Update or regenerate nix/hashes.json
2. Commit the updated hashes file

**Files typically involved**:
- `nix/hashes.json`

**Example commit sequence**:
```
Update or regenerate nix/hashes.json
Commit the updated hashes file
```

### Generate Sdk Or Test Artifacts

Regenerates SDK files, test artifacts, or other generated code after changes to source or API definitions.

**Frequency**: ~5 times per month

**Steps**:
1. Run code generation scripts
2. Commit generated files (e.g., sdk.gen.ts, types.gen.ts, openapi.json, or test files)

**Files typically involved**:
- `packages/sdk/js/src/v2/gen/sdk.gen.ts`
- `packages/sdk/js/src/v2/gen/types.gen.ts`
- `packages/sdk/openapi.json`
- `packages/opencode/test/account/service.test.ts`
- `packages/opencode/test/project/project.test.ts`
- `packages/opencode/src/tool/task.ts`
- `packages/app/e2e/projects/projects-switch.spec.ts`
- `packages/app/src/pages/layout.tsx`
- `packages/app/src/pages/layout/helpers.ts`
- `packages/app/src/pages/session.tsx`
- `packages/app/src/pages/session/session-side-panel.tsx`

**Example commit sequence**:
```
Run code generation scripts
Commit generated files (e.g., sdk.gen.ts, types.gen.ts, openapi.json, or test files)
```

### Add Or Update I18n Translations

Adds or updates translation files for multiple languages in the app or console.

**Frequency**: ~2 times per month

**Steps**:
1. Edit or add translation files for each supported language
2. Commit all updated translation files together

**Files typically involved**:
- `packages/app/src/i18n/ar.ts`
- `packages/app/src/i18n/br.ts`
- `packages/app/src/i18n/bs.ts`
- `packages/app/src/i18n/da.ts`
- `packages/app/src/i18n/de.ts`
- `packages/app/src/i18n/en.ts`
- `packages/app/src/i18n/es.ts`
- `packages/app/src/i18n/fr.ts`
- `packages/app/src/i18n/ja.ts`
- `packages/app/src/i18n/ko.ts`
- `packages/app/src/i18n/no.ts`
- `packages/app/src/i18n/pl.ts`
- `packages/app/src/i18n/ru.ts`
- `packages/app/src/i18n/th.ts`
- `packages/app/src/i18n/tr.ts`
- `packages/app/src/i18n/zh.ts`
- `packages/app/src/i18n/zht.ts`
- `packages/console/app/src/i18n/ar.ts`
- `packages/console/app/src/i18n/br.ts`
- `packages/console/app/src/i18n/da.ts`
- `packages/console/app/src/i18n/de.ts`
- `packages/console/app/src/i18n/en.ts`
- `packages/console/app/src/i18n/es.ts`
- `packages/console/app/src/i18n/fr.ts`
- `packages/console/app/src/i18n/it.ts`
- `packages/console/app/src/i18n/ja.ts`
- `packages/console/app/src/i18n/ko.ts`
- `packages/console/app/src/i18n/no.ts`
- `packages/console/app/src/i18n/pl.ts`
- `packages/console/app/src/i18n/ru.ts`
- `packages/console/app/src/i18n/th.ts`
- `packages/console/app/src/i18n/tr.ts`
- `packages/console/app/src/i18n/zh.ts`
- `packages/console/app/src/i18n/zht.ts`

**Example commit sequence**:
```
Edit or add translation files for each supported language
Commit all updated translation files together
```

### Feature Or Bugfix With Tests

Implements a new feature or bugfix and adds/updates corresponding tests.

**Frequency**: ~3 times per month

**Steps**:
1. Edit or add implementation files
2. Edit or add test files in the corresponding test directory
3. Commit both implementation and test changes together

**Files typically involved**:
- `packages/opencode/src/agent/agent.ts`
- `packages/opencode/src/skill/skill.ts`
- `packages/opencode/src/tool/task.ts`
- `packages/opencode/test/agent/agent.test.ts`
- `packages/opencode/test/session/system.test.ts`
- `packages/opencode/test/tool/skill.test.ts`
- `packages/opencode/test/tool/task.test.ts`
- `packages/opencode/test/account/service.test.ts`
- `packages/opencode/test/filesystem/filesystem.test.ts`
- `packages/opencode/test/file/watcher.test.ts`
- `packages/opencode/test/util/process.test.ts`
- `packages/opencode/test/cli/cmd/tui/prompt-part.test.ts`

**Example commit sequence**:
```
Edit or add implementation files
Edit or add test files in the corresponding test directory
Commit both implementation and test changes together
```

### Dependency Or Package Update

Updates dependencies or patches, often across multiple package.json files and lockfiles.

**Frequency**: ~3 times per month

**Steps**:
1. Edit bun.lock and/or package.json files
2. Edit or add patch files if needed
3. Commit all related files together

**Files typically involved**:
- `bun.lock`
- `package.json`
- `packages/opencode/package.json`
- `packages/app/package.json`
- `packages/desktop-electron/package.json`
- `patches/solid-js@1.9.10.patch`
- `patches/@ai-sdk%2Fxai@2.0.51.patch`

**Example commit sequence**:
```
Edit bun.lock and/or package.json files
Edit or add patch files if needed
Commit all related files together
```


## Best Practices

Based on analysis of the codebase, follow these practices:

### Do

- Use conventional commit format (feat:, fix:, etc.)
- Write tests using playwright
- Follow *.test.ts naming pattern
- Use camelCase for file names
- Prefer named exports

### Don't

- Don't write vague commit messages
- Don't skip tests for new features
- Don't deviate from established patterns without discussion

---

*This skill was auto-generated by [ECC Tools](https://ecc.tools). Review and customize as needed for your team.*
