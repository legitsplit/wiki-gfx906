# Reference

This reference provides a quick overview of the most important concepts, commands, and configuration options for the GFX906 wiki built with **mdBook**.

## Project Structure

```
wiki-gfx906/
├── book/               # Generated static site (output of `mdbook build`)
├── src/                # Source markdown files
│   ├── SUMMARY.md      # Table of contents for the book
│   ├── intro.md
│   ├── getting_started.md
│   ├── usage.md
│   ├── reference.md    # ← This file
│   └── contributing.md
├── book.toml           # mdBook configuration
└── .github/
    └── workflows/
        └── mdbook.yml  # GitHub Actions CI/CD pipeline
```

## mdBook Commands

| Command | Description |
|---------|-------------|
| `mdbook build` | Compile the book into static HTML files under `book/`. |
| `mdbook serve` | Run a local development server (default: <http://localhost:3000>) that watches for changes. |
| `cargo install mdbook` | Install the `mdbook` binary (required for the above commands). |

## Configuration (`book.toml`)

```toml
[book]
title = "Wiki GFX906"
author = ["Your Name"]
description = "Documentation and wiki for gfx906 project"
language = "en"
multilingual = false
src = "src"

[output.html]
default-theme = "light"
preferred-dark-theme = "navy"
git-repository-url = "https://github.com/yourusername/wiki-gfx906"
edit-url-template = "https://github.com/yourusername/wiki-gfx906/edit/main/{path}"
```

- **`src`** – Directory that holds the markdown source files.  
- **`default-theme` / `preferred-dark-theme`** – Control the visual theme of the generated site.  
- **`edit-url-template`** – Enables the “Edit on GitHub” link for each page.

## GitHub Actions Workflow (`.github/workflows/mdbook.yml`)

| Step | Purpose |
|------|---------|
| `actions/checkout@v4` | Checks out the repository. |
| `actions/setup-rust@v1` | Installs the stable Rust toolchain. |
| `cargo install mdbook` | Installs `mdbook` on the runner. |
| `mdbook build wiki-gfx906` | Generates the static site. |
| `actions/upload-pages-artifact@v3` | Packages the `book/` directory for deployment. |
| `actions/deploy-pages@v3` | Publishes the artifact to GitHub Pages. |

The workflow triggers on pushes to `main` and can also be started manually via `workflow_dispatch`.

## Adding New Content

1. **Create a Markdown file** in `src/` (e.g., `src/new_topic.md`).  
2. **Add an entry** in `src/SUMMARY.md`:
   ```markdown
   - [New Topic](./new_topic.md)
   ```
3. **Rebuild** (`mdbook build`) or **serve** (`mdbook serve`) to see the changes.

## Frequently Asked Questions

- **Do I need to run `mdbook build` on every push?**  
  No. The GitHub Actions workflow automatically builds and deploys on every push to `main`.

- **How can I change the theme?**  
  Edit `default-theme` and `preferred-dark-theme` in `book.toml` and rebuild.

- **Where are the generated files stored?**  
  In the `book/` directory, which is ignored by Git by default.

## Contributing Guidelines

Refer to `src/contributing.md` for the full contribution process, commit style, and code‑of‑conduct.

---  

*Happy documenting!* 🎉