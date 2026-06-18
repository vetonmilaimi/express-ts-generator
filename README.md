# Express TypeScript Generator

A command-line tool to quickly scaffold an Express application skeleton pre-configured with TypeScript, modern tooling, and optional stylesheet or view engine support.

Inspired by [express-generator](https://github.com/expressjs/generator).

## Features

- **TypeScript Native**: Pre-configured `tsconfig.json`, source files in `src/`, and ES Modules imports.
- **Modern Dev Tooling**: Live reloading using [nodemon](https://github.com/remy/nodemon) and [ts-node](https://github.com/TypeStrong/ts-node) for seamless TypeScript execution.
- **Environment Configuration**: Ready-to-go dotenv configuration.
- **Cross-Platform Static Building**: Multi-platform node script for copying public assets & templates to `dist` for compilation.
- **Multiple Options**: Supports CSS preprocessors (Sass, Less) and popular view engines (EJS, Pug, Handlebars).
- **Git Ready**: Built-in option to initialize git repository and generate `.gitignore`.

---

## Installation

The package is published on npm as `@veton.milaimi/express-ts-generator` and exposes the `express-ts` command.

Install it globally:

```bash
npm install -g @veton.milaimi/express-ts-generator
```

Then generate a project:

```bash
express-ts [options] [dir]
```

You can also run it without installing globally:

```bash
npx @veton.milaimi/express-ts-generator [options] [dir]
```

---

## Usage

After global installation, use the CLI command:

```bash
express-ts [options] [dir]
```

For one-off usage, prefix the same arguments with the package name:

```bash
npx @veton.milaimi/express-ts-generator [options] [dir]
```

Examples:

```bash
# Generate an API project in ./my-app
express-ts --git --pm npm my-app

# Or run directly from npm without a global install
npx @veton.milaimi/express-ts-generator --ejs --css sass my-web-app
```

### Options

| Flag | Option | Description |
| :--- | :--- | :--- |
| `-h` | `--help` | Output usage information |
| | `--version` | Output the version number |
| `-e` | `--ejs` | Add EJS engine support |
| | `--pug` | Add Pug engine support |
| | `--hbs` | Add Handlebars engine support |
| | `--no-view` | Use static HTML instead of a view engine (default) |
| `-c` | `--css <engine>` | Add stylesheet engine support (`css`, `sass`, `less`) (default: `css`) |
| `-g` | `--git` | Add `.gitignore` and initialize a git repository |
| `-f` | `--force` | Force generation in a non-empty directory |
| `-p` | `--pm <manager>` | Specify package manager: `npm`, `yarn`, `pnpm`, `bun` (default: `npm`) |

---

## Quick Start

### 1. Create a New Project

```bash
npx @veton.milaimi/express-ts-generator --git --pm npm my-app
```

### 2. Start Development

```bash
cd my-app
npm install
npm run dev
```

### 3. Scaffold a Project with EJS and Sass

```bash
npx @veton.milaimi/express-ts-generator --ejs --css sass my-web-app
```

---

## Generated Project Scripts

Inside the generated project directory, you will have access to the following npm scripts:

- **Start development server** (with hot-reloading):
  ```bash
  npm run dev
  ```
- **Build the project** (compiles TypeScript to `dist/` and copies static assets):
  ```bash
  npm run build
  ```
- **Start the compiled application** in production mode:
  ```bash
  npm start
  ```

---

## License

MIT
