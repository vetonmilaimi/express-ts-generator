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

You can install the generator globally via npm:

```bash
npm install -g .
```

Or run it directly from the repository using the local path:

```bash
./bin/express-ts-generator [options] [dir]
```

---

## Usage

```bash
express-ts [options] [dir]
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

### 1. Scaffold a New API Project

```bash
# Generate in a folder called my-app
express-ts --git --pm npm my-app
```

### 2. Scaffold a Project with View Engine (e.g., EJS) & Sass

```bash
express-ts --ejs --css sass my-web-app
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
