> # 📖 La référence du langage Rust
>
> **🌐 This is the french translation of the book "The Rust Language Reference"**
>
> [👓 Click here to read this translated book online](https://jimskapt.github.io/rust-reference-fr/)
>
> *[🔗 Click here to go to the English Book repository](https://github.com/rust-lang/reference)*
>
> Translations are inside [`/FRENCH/`](https://github.com/Jimskapt/rust-reference-fr/tree/french-release/FRENCH)
> folder. Everything else should be remaining as the English Book *(except some
> necessary files, like this README.md)*.
>
> Want to help to translate ?
> Please read the file
> [/FRENCH/CONTRIBUTING.md](https://github.com/Jimskapt/rust-reference-fr/blob/french-release/FRENCH/CONTRIBUTING.md) !

# The Rust Language Reference

This document is the primary reference for the Rust programming language.

This document is not normative. It may include details that are specific
to `rustc` itself, and should not be taken as a specification for the
Rust language. We intend to produce such a document someday, but this is
what we have for now.

## Dependencies

- rustc (the Rust compiler).
- mdbook (use `cargo install mdbook` to install it).

## Build steps

First, go to the repository folder and test the code snippets to catch
compilation errors:

```sh
cd reference
mdbook test
```

And then generate the book:

```sh
mdbook build
```

The generated HTML will be in the `book` folder.
