```markdown
# tt-rss Development Patterns

> Auto-generated skill from repository analysis

## Overview
This skill teaches the core development patterns and conventions used in the `tt-rss` TypeScript codebase. You'll learn about file naming, import/export styles, commit message patterns, and how to write and run tests in this repository. This guide is ideal for contributors looking to quickly align with the project's established practices.

## Coding Conventions

### File Naming
- **Convention:** PascalCase for all file names.
- **Example:**  
  ```
  ArticleList.ts
  FeedManager.ts
  ```

### Import Style
- **Convention:** Use relative imports for internal modules.
- **Example:**
  ```typescript
  import { FeedManager } from './FeedManager';
  import { Article } from '../models/Article';
  ```

### Export Style
- **Convention:** Use named exports.
- **Example:**
  ```typescript
  // In FeedManager.ts
  export function fetchFeeds() { ... }
  export const FEED_LIMIT = 100;
  ```

### Commit Message Patterns
- **Type:** Freeform, no strict prefix required.
- **Average Length:** ~50 characters.
- **Example:**
  ```
  Fix bug in feed parsing logic
  Add support for custom article filters
  ```

## Workflows

### Adding a New Feature
**Trigger:** When implementing a new feature or module  
**Command:** `/add-feature`

1. Create a new file using PascalCase (e.g., `NewFeature.ts`).
2. Use relative imports to include dependencies.
3. Export all functions or constants using named exports.
4. Write corresponding tests in a file named `NewFeature.test.ts`.
5. Commit changes with a clear, concise message.

### Fixing a Bug
**Trigger:** When resolving a bug or issue  
**Command:** `/fix-bug`

1. Locate the relevant file(s) using PascalCase naming.
2. Apply the fix, maintaining existing coding conventions.
3. Update or add tests in the corresponding `*.test.ts` file.
4. Commit with a descriptive message about the fix.

### Writing and Running Tests
**Trigger:** When adding or updating tests  
**Command:** `/run-tests`

1. Create or update a test file matching the pattern `*.test.ts`.
2. Write tests using the project's preferred (unspecified) testing framework.
3. Run the test suite using the project's test runner (framework not detected; refer to project docs or package.json scripts).

## Testing Patterns

- **Test File Pattern:** All test files are named with the pattern `*.test.ts`.
- **Framework:** Not explicitly detected; check project documentation or dependencies.
- **Example:**
  ```typescript
  // In FeedManager.test.ts
  import { fetchFeeds } from './FeedManager';

  test('fetchFeeds returns correct number of feeds', () => {
    expect(fetchFeeds()).toHaveLength(10);
  });
  ```

## Commands
| Command      | Purpose                                   |
|--------------|-------------------------------------------|
| /add-feature | Scaffold and implement a new feature      |
| /fix-bug     | Apply a bugfix and update related tests   |
| /run-tests   | Run the test suite for the codebase       |
```
