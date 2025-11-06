# Usage

This page explains how to work with the **GFX906 Wiki** using `mdBook`. It covers building the book locally, previewing it, and adding new content.

## Prerequisites

- **Git** – to clone the repository.
- **Rust** (stable) – required for `cargo` and `mdbook`.
- **mdBook** – install with:

```sh
cargo install mdbook
```

## Building the Book

From the repository root:

```sh
mdbook build wiki-gfx906
```

The generated static site will be placed in `wiki-gfx906/book/`.

## Previewing Locally

Run a local development server that watches for changes:

```sh
mdbook serve wiki-gfx906
```

Open <http://localhost:3000> in your browser. The server automatically reloads when you edit markdown files.

## Adding New Content

1. **Create a markdown file** in `wiki-gfx906/src/`, e.g.:

   ```sh
   touch wiki-gfx906/src/advanced_topics.md
   ```

2. **Edit `SUMMARY.md`** to include the new file. For example, add:

   ```markdown
   - [Advanced Topics](./advanced_topics.md)
   ```

3. **Write your content** in the new file using standard Markdown syntax.

4. **Rebuild or serve** the book to see the changes.

## Common Patterns

### Code Blocks

```rust
fn main() {
    println!("Hello, mdBook!");
}
```

### Inline Code

Use backticks for `inline code`.

### Links

- Relative link to another chapter: `[Getting Started](./getting_started.md)`
- External link: <https://github.com/>

## Contributing

If you want to contribute improvements:

1. Fork the repository.
2. Create a feature branch.
3. Make your changes.
4. Open a Pull Request targeting `main`.

All contributions are welcome. See the [Contributing](./contributing.md) page for detailed guidelines.

## Deploying to GitHub Pages

The repository includes a GitHub Actions workflow (`.github/workflows/mdbook.yml`) that automatically:

1. Installs `mdbook`.
2. Builds the book.
3. Deploys the `book/` directory to GitHub Pages on every push to `main`.

No manual steps are required after the initial setup.

---

Enjoy writing and reading the GFX906 documentation! 🎉