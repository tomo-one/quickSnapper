# quickSnapper

A small personal information lookup tool for the command line.
The snippets you need every day — employee ID, credentials, proxy
strings, color codes, phone numbers — all live in one data file.
Pick YAML, TOML or INI and have them at hand with a two-second command.
The result lands in the clipboard, secrets stay masked on screen, and
passwords or other sensitive information can also be stored encrypted.

This repository distributes **ready-to-run binaries** of quickSnapper.
It does not contain the Python source code.

## Download

Grab the latest ZIP from the [Releases](../../releases) page. Currently
built for **Windows** (x64); other platforms may follow.

## Installation

1. Unpack the ZIP, e.g. into `%USERPROFILE%\bin\quickSnapper`.
2. Add that directory to your `PATH`.
3. Run `qs` from a new command prompt:

   ```
   qs --version
   qs --list
   qs email
   ```

4. Swap the bundled demo data (`data\qs_demo.yaml`) for your own, e.g.:

   ```
   qs --db config\quickSnapper.ini --set settings.data_file qs_data.yaml
   ```

## Package contents

```
quickSnapper/
  ├── qs.exe                    the tool (standalone, no Python install needed)
  ├── config/
  │   └── quickSnapper.ini      program settings
  ├── data/
  │   └── qs_demo.yaml          demo data (shipped default)
  └── extensions/
      └── doskeys.cmd           DOSKEY aliases (Windows)
```

## License

[MIT](LICENSE) — for the binary distribution in this repository.

---

Version 0.8.9 — Tom Gries
