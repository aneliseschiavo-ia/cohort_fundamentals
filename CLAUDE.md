# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Repository Overview

This is the **CoHort Fundamentals** learning repository—a space for course materials, exercises, and projects as you progress through the curriculum. The repository uses a flexible structure that grows with your learning.

**Course Resources:**
- [Class Page](https://fundamentals-theta.vercel.app/#/aula/1/fundacao)
- [NotebookLM](https://notebooklm.google.com/notebook/02e00a39-2dbe-4232-971d-e42cb3f5246f?authuser=0&addSource=true)

## Project Structure

As the course progresses, organize work by module:

```
cohort_fundamentals/
├── links/                    # Course resources and reference links
├── module-1-name/           # Each module gets its own directory
│   ├── exercises/           # Coding exercises
│   ├── projects/            # Module projects
│   ├── notes/               # Learning notes
│   └── tests/               # Test files
├── module-2-name/
│   └── ... (same structure)
└── shared/                  # Shared utilities, helpers, type definitions
    └── utils/
```

## Development Commands

### Setup
```bash
npm install    # Install dependencies (when package.json is added)
```

### Development
```bash
npm run dev    # Start development environment
npm start      # Run the application
```

### Testing
```bash
npm test       # Run all tests
npm run test:watch  # Run tests in watch mode
npm run test:single -- path/to/test.js  # Run a specific test
```

### Code Quality
```bash
npm run lint   # Check code style
npm run format # Format code automatically
npm run typecheck  # Run TypeScript/type checking (if applicable)
```

### Building
```bash
npm run build  # Create production build
```

## Code Standards

### General Principles
- **Self-documenting code**: Write clear function and variable names; avoid comments for obvious code
- **Consistency**: Follow existing patterns in the codebase
- **Testing**: Write tests for exercises and projects; at minimum, test edge cases
- **Error handling**: Use try-catch blocks appropriately and provide meaningful error messages

### JavaScript/TypeScript
- Use ES6+ syntax (arrow functions, const/let, destructuring, template literals)
- Prefer functional programming patterns when appropriate
- Keep functions focused and testable (ideally under 25 lines)
- Use descriptive variable names (avoid single letters except in loops/callbacks)

### File Organization
- One main concept per file
- Group related utilities in a directory with an `index.js` re-export
- Place tests alongside code (`component.js` + `component.test.js`)

### Git & Commits
- Commit frequently with clear messages explaining *why* not just *what*
- Use conventional prefixes: `feat:`, `fix:`, `docs:`, `test:`, `refactor:`
- Example: `feat: add input validation to form component`
- Keep commits atomic—one logical change per commit

## Module-Specific Guidelines

When working on a module:

1. **Read the module requirements** first (usually in the course materials)
2. **Create the module directory** with the structure above
3. **Start with exercises** before tackling projects
4. **Document your approach** in a README within the module directory
5. **Test thoroughly** before marking work complete
6. **Review and refactor** after functionality works

## Testing Strategy

- Write tests *as you code*, not after
- Test edge cases and error conditions
- For exercises: unit tests for functions/components
- For projects: mix unit tests + integration tests
- Use descriptive test names that explain what's being tested

Example:
```javascript
// ✓ Good
test('should return sum of two numbers', () => { ... })

// ✗ Avoid
test('add function', () => { ... })
```

## When to Ask for Help

- You get stuck after trying multiple approaches
- You're unsure about the right design pattern to use
- Code works but feels overly complex
- You need to understand how multiple files interact
- Tests are failing and the error message isn't clear

When asking, provide:
- What you're trying to accomplish
- What you've already tried
- The specific error or unexpected behavior
- Relevant code snippets

## Learning Tips

- **Start small**: Complete exercises before starting projects
- **Understand before coding**: Read requirements thoroughly
- **Refactor regularly**: Once tests pass, improve code clarity
- **Compare solutions**: After completing work, review the reference solution
- **Build incrementally**: Add features one at a time, testing each step

---

*This CLAUDE.md will evolve as the course progresses. Update it with new patterns, tools, or conventions your cohort adopts.*
