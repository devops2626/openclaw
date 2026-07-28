```markdown
# openclaw Development Patterns

> Auto-generated skill from repository analysis

## Overview

This skill teaches you how to contribute to the `openclaw` codebase, a TypeScript project using the Express framework. You'll learn the repository's coding conventions, commit patterns, testing strategies, and the main development workflows for features, schema evolution, extensions, UI updates, authentication, and scheduling logic. Each workflow is documented with step-by-step instructions and suggested `/commands` for common tasks.

---

## Coding Conventions

- **File Naming:**  
  Use `kebab-case` for files and folders.  
  _Example:_  
  ```
  src/gateway/server-cron-handler.ts
  extensions/slack/src/slack-client.ts
  ```

- **Import Style:**  
  Mixed usage of default and named imports.  
  _Examples:_  
  ```typescript
  import express from 'express';
  import { validateSchema } from './schema-validator';
  ```

- **Export Style:**  
  Prefer **named exports**.  
  _Example:_  
  ```typescript
  // Good
  export function startServer() { ... }
  export const SERVER_PORT = 8080;

  // Avoid default exports
  ```

- **Commit Messages:**  
  Follow [Conventional Commits](https://www.conventionalcommits.org/):  
  - Prefixes: `fix`, `refactor`, `feat`, `test`, `perf`
  - Example:  
    ```
    feat: add cron job scheduler for recurring tasks
    fix: correct OAuth token refresh logic
    ```

---

## Workflows

### Feature Development with Tests and Docs
**Trigger:** When adding or enhancing a feature, ensuring it is tested and documented  
**Command:** `/feature`

1. Implement or modify feature logic in main source files (`src/**/*.ts`, `extensions/**/*.ts`).
2. Add or update corresponding test files (`*.test.ts`).
3. Update or add relevant documentation (`docs/*.md`).

_Example:_
```typescript
// src/gateway/server-cron-handler.ts
export function scheduleJob(...) { ... }
```
```typescript
// src/gateway/server-cron-handler.test.ts
import { scheduleJob } from './server-cron-handler';
test('schedules job', () => { ... });
```

---

### API or Schema Evolution
**Trigger:** When adding, changing, or removing API endpoints or data structures  
**Command:** `/update-schema`

1. Modify or add schema/type files (`packages/gateway-protocol/src/schema*.ts`).
2. Update validator or registry files as needed.
3. Update or add related test files for schema validation.
4. Update documentation if the public contract changes.

_Example:_
```typescript
// packages/gateway-protocol/src/schema-user.ts
export interface UserSchema { ... }
```
```typescript
// packages/gateway-protocol/src/schema-user.test.ts
import { UserSchema } from './schema-user';
test('validates user schema', () => { ... });
```

---

### Extension or Plugin Enhancement with Tests
**Trigger:** When enhancing or fixing an extension/plugin  
**Command:** `/update-extension`

1. Modify or add implementation files under `extensions/<plugin>/src/`.
2. Update or add test files under the same extension.
3. Update the extension's `openclaw.plugin.json` if needed.
4. Optionally update related docs.

_Example:_
```typescript
// extensions/slack/src/slack-client.ts
export function sendMessage(...) { ... }
```
```typescript
// extensions/slack/src/slack-client.test.ts
import { sendMessage } from './slack-client';
test('sends message', () => { ... });
```

---

### UI Component or Style Update with Tests
**Trigger:** When adding or updating a UI component or style  
**Command:** `/ui-update`

1. Modify or add files under `ui/src/components/` or `ui/src/styles/`.
2. Add or update browser/e2e test files for the UI change.
3. Optionally update related helpers or state controllers.

_Example:_
```typescript
// ui/src/components/button.ts
export function Button(props) { ... }
```
```typescript
// ui/src/components/button.browser.test.ts
import { Button } from './button';
test('renders button', () => { ... });
```

---

### Fix or Enhance Auth Provider Flow
**Trigger:** When fixing, extending, or refactoring authentication flows  
**Command:** `/auth-fix`

1. Modify or add files under `src/agents/auth-profiles/`, `src/llm/utils/oauth/`, or `extensions/github-copilot/`.
2. Update or add corresponding test files.
3. Optionally update documentation.

_Example:_
```typescript
// src/llm/utils/oauth/token-manager.ts
export function refreshToken(...) { ... }
```
```typescript
// src/llm/utils/oauth/token-manager.test.ts
import { refreshToken } from './token-manager';
test('refreshes token', () => { ... });
```

---

### Cron or Scheduler Feature or Fix
**Trigger:** When adding, fixing, or refactoring cron/scheduler logic  
**Command:** `/cron-fix`

1. Modify or add files under `src/gateway/server-cron*`, `src/cron/`, or `src/gateway/server-methods/cron*`.
2. Update or add test files for cron logic.
3. Optionally update protocol/schema files if contract changes.

_Example:_
```typescript
// src/gateway/server-cron-handler.ts
export function handleCronJob(...) { ... }
```
```typescript
// src/gateway/server-cron-handler.test.ts
import { handleCronJob } from './server-cron-handler';
test('handles cron job', () => { ... });
```

---

## Testing Patterns

- **Framework:** [Vitest](https://vitest.dev/)
- **File Pattern:** Tests are colocated and named `*.test.ts`
- **Example:**
  ```typescript
  // src/utils/date-utils.test.ts
  import { formatDate } from './date-utils';

  test('formats date correctly', () => {
    expect(formatDate(new Date('2024-01-01'))).toBe('2024-01-01');
  });
  ```

---

## Commands

| Command         | Purpose                                                      |
|-----------------|-------------------------------------------------------------|
| /feature        | Start a new feature with tests and documentation            |
| /update-schema  | Update or extend API schemas and related validation         |
| /update-extension | Enhance or fix an extension/plugin with tests             |
| /ui-update      | Add or update UI components/styles with tests               |
| /auth-fix       | Fix or enhance authentication provider logic                |
| /cron-fix       | Add or fix cron/scheduler logic and related tests           |
```
