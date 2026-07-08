```markdown
# autobe Development Patterns

> Auto-generated skill from repository analysis

## Overview
This skill teaches the core development conventions and workflows used in the `autobe` TypeScript repository. You'll learn about file naming, import/export styles, commit patterns, and how to write and run tests. The repository does not use a detected framework, so it follows a lightweight, modular TypeScript structure.

## Coding Conventions

### File Naming
- Use **camelCase** for file names.
  - Example: `myModule.ts`, `userService.ts`

### Import Style
- Use **relative imports** for referencing other modules.
  - Example:
    ```typescript
    import { myFunction } from './myModule';
    ```

### Export Style
- Use **named exports** (not default).
  - Example:
    ```typescript
    // In myModule.ts
    export function myFunction() { ... }

    // Usage
    import { myFunction } from './myModule';
    ```

### Commit Messages
- Follow **conventional commit** style.
- Use the `chore` prefix for maintenance commits.
  - Example: `chore: update dependencies for security patch`

## Workflows

### Commit Changes
**Trigger:** When making any code or maintenance change  
**Command:** `/commit-changes`

1. Make your code changes following the coding conventions.
2. Stage your changes:  
   ```bash
   git add .
   ```
3. Write a commit message using the conventional commit format, typically with the `chore` prefix:
   ```bash
   git commit -m "chore: describe your change"
   ```
4. Push your changes:
   ```bash
   git push
   ```

### Add a New Module
**Trigger:** When creating a new feature or utility module  
**Command:** `/add-module`

1. Create a new TypeScript file using camelCase naming, e.g., `newFeature.ts`.
2. Use named exports for all functions or constants.
   ```typescript
   // newFeature.ts
   export function doSomething() { ... }
   ```
3. Import your module using a relative path where needed.
   ```typescript
   import { doSomething } from './newFeature';
   ```

### Write and Run Tests
**Trigger:** When adding or updating code that needs testing  
**Command:** `/run-tests`

1. Create a test file with the `.test.ts` suffix, e.g., `myModule.test.ts`.
2. Write your tests using your preferred testing framework (not specified in repo).
   ```typescript
   // myModule.test.ts
   import { myFunction } from './myModule';

   describe('myFunction', () => {
     it('should work correctly', () => {
       expect(myFunction()).toBe(/* expected value */);
     });
   });
   ```
3. Run your tests using the appropriate command for your test runner.

## Testing Patterns

- Test files use the `*.test.ts` naming pattern and are placed alongside the modules they test.
- The testing framework is not specified, but typical test structure includes `describe` and `it` blocks.
- Example:
  ```typescript
  // example.test.ts
  import { exampleFunction } from './example';

  describe('exampleFunction', () => {
    it('returns expected result', () => {
      expect(exampleFunction()).toBe('expected');
    });
  });
  ```

## Commands
| Command         | Purpose                                      |
|-----------------|----------------------------------------------|
| /commit-changes | Guide for committing code using conventions  |
| /add-module     | Steps for adding a new module                |
| /run-tests      | Instructions for writing and running tests   |
```