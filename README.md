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

Grab the ZIP for your platform from the [Releases](../../releases) page:

- **Windows** x64 (`qs.exe`)
- **macOS** Apple Silicon (`qs`)
- **Linux** x64 (`qs`)
- **Linux** ARM64 (`qs`)

## Installation

1. Unzip the archive anywhere (e.g. Downloads).
2. Run the bundled interactive installer from the unpacked folder:

   ```
   install.cmd        (Windows, in a command prompt)
   ./install.sh       (macOS/Linux)
   ```

   It asks for the install location (platform default, home-bin variant
   or a custom path), optionally adds a PATH entry, and can create the
   optional aliases `qsl`, `qse`, `qsd` — individually selectable. On an
   update it merges `config/quickSnapper.ini` instead of overwriting it,
   so your settings survive. Alternatively, set everything up by hand:
   see `docs/README.md` in the package.

3. Open a new terminal and try:

   ```
   qs --version
   qs --list
   qs email
   ```

4. Keep your own data in `qs_data.yaml` — it is created automatically
   from a built-in template on first access and never touched by
   updates. The bundled `data/qs_demo.yaml` is a playground; activate it
   temporarily with:

   ```
   qs --db ../config/quickSnapper.ini --set settings.data_file qs_demo.yaml
   ```

## Package contents

```
quickSnapper-<platform>-vX.Y.Z/
  ├── qs.exe  or  qs            the tool (standalone, no Python install needed)
  ├── _internal/                the tool's runtime files (belong to the binary)
  ├── install.cmd / install.sh  interactive installer (per platform)
  ├── LICENSE                   MIT license
  ├── config/
  │   └── quickSnapper.ini      program settings
  ├── data/
  │   ├── qs_demo.yaml          demo data (playground; overwritten by updates)
  │   ├── cc.yaml               extra DB: country codes, incl. reverse lookup
  │   └── cc.xlsx               Excel source of cc.yaml
  ├── docs/
  │   ├── README.md             full documentation (English)
  │   └── README.de.md          full documentation (German)
  └── src/
      ├── qs_excel_to_yaml.py   script: Excel -> YAML data files
      └── qs_yaml_to_excel.py   script: YAML data files -> Excel (round trip)
```

The scripts under `src/` require a Python installation (3.10+,
`pip install openpyxl pyyaml`) — the `qs` binary itself does not.

## Community data

More lookup DBs (e.g. `kfz.yaml`, German license plate codes) live in
[community-data/](community-data) on this repo's `main` branch instead of
being bundled in the release ZIP — new or updated ones show up here
without needing a new quickSnapper release. Fetch one straight into your
`data/` folder:

```
qs --fetch-db          # list what's available
qs --fetch-db kfz      # download kfz.yaml into data/
```

Excel sources for these files (so they can be edited and reconverted) live
under [community-data/xlsx/](community-data/xlsx).

## License

[MIT](LICENSE) — for the binary distribution in this repository.

---

Version 0.10.0 — TOMO
