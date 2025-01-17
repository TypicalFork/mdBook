# The watch command

The `watch` command is useful when you want your book to be rendered on every
file change. You could repeatedly issue `mdbook build` every time a file is
changed, but using `mdbook watch` greatly simplifies this behaviour. It will watch your files and
trigger a build automatically whenever you modify a file.

#### Specify a directory

The `watch` command can take a directory as an argument to use as the book's
root instead of the current working directory.

```bash
mdbook watch path/to/book
```

#### --open

When you use the `--open` (`-o`) option, mdBook will open the rendered book in
your default web browser.

#### --dest-dir

The `--dest-dir` (`-d`) option allows you to change the output directory for the
book. Relative paths are interpreted relative to the book's root directory. If
not specified it will default to the value of the `build.build-dir` key in
`book.toml`, or to `./book`.


#### Specify exclude patterns

The `watch` command will not automatically trigger a build for files listed in
the `.gitignore` file in the book's root directory. The `.gitignore` file may
contain file patterns described in the [gitignore
documentation](https://git-scm.com/docs/gitignore). This can be useful for
ignoring temporary files created by some editors.

***Note***: *Only `.gitignore` from the book's root directory is used. Global
`$HOME/.gitignore` or `.gitignore` files in parent directories are not used.*
