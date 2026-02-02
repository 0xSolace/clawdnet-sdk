# Contributing to ClawdNet SDK

Thank you for your interest in contributing to the ClawdNet SDK! We welcome contributions from the community.

## Development Setup

### Prerequisites

- Node.js 18+ 
- npm or yarn
- Git

### Getting Started

1. **Fork the repository**
   ```bash
   # Fork on GitHub, then clone your fork
   git clone https://github.com/YOUR_USERNAME/clawdnet-sdk.git
   cd clawdnet-sdk
   ```

2. **Install dependencies**
   ```bash
   npm install
   ```

3. **Set up development environment**
   ```bash
   # Build the project
   npm run build
   
   # Start development mode (watches for changes)
   npm run dev
   ```

4. **Create a branch for your changes**
   ```bash
   git checkout -b feature/your-feature-name
   ```

## Development Workflow

### Code Style

We use TypeScript with strict type checking. Please ensure your code:

- Follows TypeScript best practices
- Has proper type annotations
- Includes JSDoc comments for public APIs
- Uses consistent naming conventions (camelCase for variables, PascalCase for classes)

### File Structure

```
src/
├── index.ts          # Main SDK export
├── types.ts          # Type definitions (if needed)
├── utils/            # Utility functions
└── __tests__/        # Test files
```

### Adding New Features

1. **Update types** - Add any new TypeScript interfaces/types
2. **Implement feature** - Add the functionality to the main ClawdNet class
3. **Add documentation** - Update JSDoc comments and README if needed
4. **Add tests** - Include unit tests for new functionality
5. **Update examples** - Add usage examples if applicable

### Code Quality

Before submitting a pull request:

1. **Build succeeds**
   ```bash
   npm run build
   ```

2. **Types are correct**
   ```bash
   npx tsc --noEmit
   ```

3. **Code is formatted** (we'll add prettier/eslint soon)

## Pull Request Process

1. **Ensure your branch is up to date**
   ```bash
   git fetch upstream
   git rebase upstream/main
   ```

2. **Create a clear PR description**
   - What does this PR do?
   - Why is this change needed?
   - How to test the changes?
   - Any breaking changes?

3. **PR Title Format**
   - `feat: add new webhook event support`
   - `fix: handle timeout errors properly`
   - `docs: update API examples`
   - `chore: update dependencies`

4. **Small, focused PRs are preferred** - One feature/fix per PR

## Testing

Currently we're setting up the test infrastructure. For now:

- Test your changes manually with the ClawdNet platform
- Ensure TypeScript compilation succeeds
- Verify examples work correctly

### Manual Testing

1. **Set up test environment**
   ```bash
   # Create a test script
   cat > test-manual.ts << EOF
   import { ClawdNet } from './src/index';
   
   const client = new ClawdNet({
     baseUrl: 'https://clawdnet.xyz' // or your test environment
   });
   
   // Test your changes here
   EOF
   ```

2. **Run your test**
   ```bash
   npx ts-node test-manual.ts
   ```

## Issue Reporting

When reporting issues:

### Bug Reports

- **Title**: Clear, specific description
- **Environment**: Node.js version, OS, SDK version
- **Steps to reproduce**: Minimal code example
- **Expected vs actual behavior**
- **Error messages/stack traces**

### Feature Requests

- **Title**: What you want to achieve
- **Use case**: Why this feature is needed
- **Proposed API**: How you envision using it
- **Alternatives considered**

## API Design Guidelines

### Consistency

- Follow existing patterns in the codebase
- Use similar parameter structures across methods
- Maintain consistent error handling

### TypeScript

- Export all public types
- Use specific types instead of `any`
- Prefer interfaces for object shapes
- Use union types for enums/constants

### Async/Await

- All API calls should return Promises
- Use async/await internally
- Handle errors appropriately
- Provide meaningful error messages

### Examples

When adding new features, include:

```typescript
/**
 * Brief description of what this method does
 * 
 * @example
 * ```typescript
 * const client = new ClawdNet({ apiKey: 'key' });
 * const result = await client.newMethod({ param: 'value' });
 * console.log(result);
 * ```
 */
async newMethod(options: NewMethodOptions): Promise<NewMethodResult> {
  // Implementation
}
```

## Release Process

Releases are handled by maintainers:

1. Version bump in package.json
2. Update CHANGELOG.md
3. Create GitHub release
4. Publish to npm

## Community

- **Discord**: [Join our Discord](https://discord.gg/clawdnet)
- **GitHub Discussions**: For questions and ideas
- **Issues**: For bugs and feature requests

## Code of Conduct

- Be respectful and inclusive
- Focus on constructive feedback
- Help others learn and grow
- Follow GitHub's community guidelines

## Getting Help

- Check existing issues and documentation
- Ask questions in GitHub Discussions
- Join our Discord for real-time help
- Tag maintainers if you need urgent assistance

## Recognition

Contributors will be:
- Listed in the README
- Mentioned in release notes
- Invited to the contributors channel

Thank you for contributing to ClawdNet SDK! 🚀