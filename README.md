# mylib

Search and download books from your terminal.

## Install

Download the archive for your computer from [Releases](https://github.com/what1f/mylib-releases/releases/latest).

| Platform | Archive |
| --- | --- |
| macOS — Apple Silicon | `mylib_darwin_arm64.tar.gz` |
| macOS — Intel | `mylib_darwin_amd64.tar.gz` |
| Linux — Intel / AMD 64-bit | `mylib_linux_amd64.tar.gz` |
| Linux — ARM64 | `mylib_linux_arm64.tar.gz` |
| Windows — Intel / AMD 64-bit | `mylib_windows_amd64.zip` |
| Windows — ARM64 | `mylib_windows_arm64.zip` |

On macOS or Linux, extract the archive and put `mylib` in a directory on your `PATH`:

```sh
tar -xzf mylib_darwin_arm64.tar.gz
mkdir -p ~/.local/bin
install -m 755 mylib ~/.local/bin/mylib
```

Replace the archive name with the one you downloaded.

On Windows, extract the ZIP and put `mylib.exe` in a directory on your `PATH`. You can also run `./mylib.exe` from that directory in PowerShell.

## Search

```sh
mylib search "Alice in Wonderland"
mylib search --full-text "Alice in Wonderland"
mylib search --page 2 --limit 20 "Alice in Wonderland"
```

Results are JSON with `id`, `book_key`, `title`, `publisher`, `author`, `year`, and `language`. Missing text is empty; an unknown year is `0`.

`--full-text` searches within book contents. `--page` defaults to `1`; `--limit` defaults to `20` and accepts `1`–`100`.

## Download

Copy a `book_key` from the search results:

```sh
mylib download 34O8Ye6wVQ
mylib download 34O8Ye6wVQ --output ~/Downloads
```

The file is saved in the current directory unless you set `--output`. The command prints the saved file path. Existing files are preserved.

## Help

```sh
mylib --help
```
