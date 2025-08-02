# TypeScript Package Template

A modern TypeScript npm package template with dual CJS/ESM support, automated testing, linting, and semantic releases.

## 🚀 Features

- **Dual Format Support** - CommonJS and ES Modules
- **TypeScript Declarations** - Full type safety
- **Automated Testing** - Jest with ts-jest
- **Code Quality** - ESLint configuration
- **Automated Releases** - Semantic versioning with semantic-release
- **Git Hooks** - Husky with commitlint
- **CI/CD** - GitHub Actions workflow

## 🛠️ Tech Stack

- **TypeScript** 5.8+
- **Node.js** 18+
- **Jest** - Testing framework
- **ESLint** - Code linting
- **semantic-release** - Automated versioning
- **Husky** - Git hooks
- **GitHub Actions** - CI/CD

## 📦 Quick Start

### 1. Use Template

```bash
# Click "Use this template" on GitHub
# Or clone and customize
git clone https://github.com/yourusername/typescript-package-template.git my-package
cd my-package
```

### 2. Update Package Configuration

```json
{
  "name": "your-package-name",
  "version": "0.1.0",
  "description": "Your package description",
  "author": "Your Name",
  "repository": {
    "type": "git",
    "url": "git+https://github.com/yourusername/your-package-name.git"
  }
}
```

### 3. Install Dependencies

```bash
npm install
```

### 4. Add Your Code

```typescript
// src/your-function.ts
export const yourFunction = (input: string): string => {
  return input.toUpperCase();
};

// src/index.ts
export * from "./your-function";
```

### 5. Build & Test

```bash
npm run build
npm test
```

## 📜 Available Scripts

| Script                  | Description                           |
| ----------------------- | ------------------------------------- |
| `npm run build`         | Build CJS, ESM, and type declarations |
| `npm run build:cjs`     | Build CommonJS format only            |
| `npm run build:esm`     | Build ES Modules format only          |
| `npm run build:types`   | Generate TypeScript declarations only |
| `npm run test`          | Run tests                             |
| `npm run test:watch`    | Run tests in watch mode               |
| `npm run test:coverage` | Run tests with coverage               |
| `npm run lint`          | Lint TypeScript files                 |
| `npm run lint:fix`      | Fix linting issues                    |
| `npm run clean`         | Remove dist folder                    |
| `npm run dev`           | Watch mode for development            |
| `npm run validate`      | Lint, test, and build                 |
| `npm run size`          | Check bundle size                     |

## 🔄 Automated Workflow

### Release Process

1. **Commit with conventional message** (see below)
2. **Push to main branch**
3. **GitHub Actions triggers** semantic-release
4. **Automatic version bump** based on commit type
5. **Publish to npm** with changelog
6. **Create GitHub release**

### Commit Message Convention

```
type(scope): description

[optional body]

[optional footer]
```

**Types:**

- `feat` - New feature (minor version)
- `fix` - Bug fix (patch version)
- `BREAKING CHANGE` - Breaking change (major version)
- `docs` - Documentation changes
- `style` - Code style changes
- `refactor` - Code refactoring
- `test` - Test changes
- `chore` - Build/tooling changes

**Examples:**

```bash
feat: add multiply function
fix: handle edge case in add function
feat(api): BREAKING CHANGE: rename add to sum
```

## 📁 Project Structure

```
├── src/
│   ├── index.ts          # Main exports
│   └── your-function.ts  # Your functions
├── tests/
│   └── your-function.test.ts
├── dist/                 # Built files (auto-generated)
│   ├── cjs/             # CommonJS
│   ├── esm/             # ES Modules
│   └── types/           # TypeScript declarations
├── .github/
│   ├── workflows/       # CI/CD
│   └── ISSUE_TEMPLATE/  # Issue templates
└── package.json
```

## 🔧 Configuration

### TypeScript Configs

- `tsconfig.base.json` - Base configuration
- `tsconfig.cjs.json` - CommonJS build
- `tsconfig.esm.json` - ES Modules build

### Build Outputs

- **CommonJS**: `dist/cjs/index.js`
- **ES Modules**: `dist/esm/index.js`
- **Types**: `dist/types/index.d.ts`

## 🚀 Publishing

### First Time Setup

1. **Login to npm**: `npm login`
2. **Create npm access token**:
   ```bash
   npm token create --read-only
   # Copy the generated token
   ```
3. **Configure GitHub secrets**:
   - Go to your repository → Settings → Secrets and variables → Actions
   - Click "New repository secret"
   - Name: `NPM_TOKEN`
   - Value: Paste your npm access token
4. **Push to main** - Triggers automatic release

### Manual Publishing

```bash
npm run publish:patch  # 0.1.0 → 0.1.1
npm run publish:minor  # 0.1.0 → 0.2.0
npm run publish:major  # 0.1.0 → 1.0.0
```

## 📋 Requirements

- Node.js 18+
- npm 9+ (or yarn/pnpm)
- GitHub account (for CI/CD)
- npm account (for publishing)

## 🤝 Contributing

1. Fork the template
2. Create feature branch
3. Follow commit conventions
4. Submit pull request

## 📄 License

MIT License - see [LICENSE](LICENSE) file.
