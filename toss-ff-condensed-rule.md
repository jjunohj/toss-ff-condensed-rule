# CLAUDE.md - Toss Frontend Code Quality Guide (Condensed)

## Core Principles

**Good Code = Easy-to-Change Code**. Evaluated by 4 criteria:

### 1. Readability

- Give explicit names to complex conditions
- Replace magic numbers with constants
- Convert nested ternary operators → if statements
- Abstract implementation details into functions/components

### 2. Predictability

- Functions with same names should behave identically
- Same type of functions should have consistent return types
- Separate side effects not revealed in function names

### 3. Cohesion

- Keep code that changes together in same location
- Manage related constants together
- Structure folders according to change patterns

### 4. Coupling

- Props Drilling → Composition pattern/Context API
- Allow reasonable duplication over excessive abstraction
- Single Responsibility Principle (one role per Hook/function)

## Additional Principles

### 5. Consistency

- Standardize file and folder naming conventions
- Define accurate types (TypeScript/PropTypes), avoid `any`

### 6. Documentation

- Add JSDoc/TS Doc comments (parameters, returns, side effects)

### 7. Error Handling

- Use `try/catch` and custom error classes
- Provide user-friendly messages

### 8. Performance & Security

- Optimize with `useMemo`/`useCallback`, code-splitting, and lazy loading
- Validate inputs, defend against XSS/CSRF, and run regular vulnerability audits

### 9. Testability

- Structure code as pure functions to enable unit testing
- Minimize DOM dependencies for E2E/UI testability

## Trade-offs

Hard to satisfy all 4 criteria. Priority by situation:

- **High Risk** → Prioritize Cohesion (abstraction/commonization)
- **Low Risk** → Prioritize Readability (allow duplication)

## Application Checklist

1. Do conditions/magic numbers have meaningful names?
2. Can you predict behavior from function name alone?
3. Is code that changes together located nearby?
4. Is the impact scope predictable when modifying one place?
5. Are file/folder naming conventions standardized and followed?
6. Are TypeScript types accurately defined (avoid `any`)?
7. Are functions documented with JSDoc/TS Doc (parameters, returns, side effects)?
8. Is error handling implemented with try/catch and user-friendly messages?
9. Are performance optimizations applied (useMemo/useCallback, code-splitting)?
10. Are security measures in place (input validation, XSS/CSRF protection)?
