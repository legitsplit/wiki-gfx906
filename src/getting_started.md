# Getting Started

Welcome to the **GFX906 Wiki**! This guide will help you set up the project locally and start exploring the documentation.

## Prerequisites

- **Git** – to clone the repository.
- **Rust** (stable) – required for building `mdbook`.
- **mdBook** – can be installed via `cargo install mdbook` (the GitHub Actions workflow does this automatically).

## Clone the Repository

```sh
git clone https://github.com/yourusername/wiki-gfx906.git
cd wiki-gfx906
```

## Build the Book Locally

1. Install `mdbook` if you haven't already:

   ```sh
   cargo install mdbook
   ```

2. Build the book:

   ```sh
   mdbook build
   ```

   The generated static site will appear in `book/`.

3. Preview it locally:

   ```sh
   mdbook serve
   ```

   Open `http://localhost:3000` in your browser to view the wiki.

## Adding New Content

1. Create a new markdown file in `src/`, e.g.:

   ```sh
   touch src/new_section.md
   ```

2. Edit `src/SUMMARY.md` to include the new file:

   ```markdown
   - [New Section](./new_section.md)
   ```

3. Re‑run `mdbook build` or `mdbook serve` to see your changes.

## Contributing

- Fork the repository.
- Create a feature branch.
- Commit your changes with clear messages.
- Open a Pull Request targeting `main`.

All contributions are welcome! See the **Contributing** page for detailed guidelines.

## Deploy to GitHub Pages

The repository includes a GitHub Actions workflow (`.github/workflows/mdbook.yml`) that automatically builds the book and publishes it to GitHub Pages on every push to `main`. No manual steps are required.

---

Happy documenting! 🎉