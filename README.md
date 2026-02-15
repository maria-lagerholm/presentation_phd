# PhD Defence Presentation

**Chemical characterisation of essential oils and machine learning analysis of molecular substructures associated with antimicrobial activity against *Salmonella* Typhimurium for food industry applications**

Built with [Reveal.js](https://revealjs.com/) v5.2.1.

## Prerequisites

- **Node.js** ≥ 18 (this project uses Node via the Python venv at `../venv/bin/node`)

## Setup

```bash
npm install
```

## Running the presentation

```bash
npm start
```

This launches a local server at **http://localhost:8000** with live-reload.

> **Tip:** If `npm`/`node` is not on your PATH, activate the venv first or export the path:
> ```bash
> export PATH="../venv/bin:$PATH"
> npm start
> ```

## Project structure

```
index.html          # Main entry point — loads slides dynamically
slides/             # Individual slide sections (HTML partials)
img/                # Images used in the presentation
dist/               # Reveal.js compiled assets (CSS, JS)
plugin/             # Reveal.js plugins (math, highlight, notes, zoom)
css/                # Reveal.js SCSS sources & custom theme
```

## Building

```bash
npm run build
```
