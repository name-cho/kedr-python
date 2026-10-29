# Kedr Python

Free, fully open-source PyCharm Community fork for Windows: no subscription, no
trial, no license dialog and no upsell of any kind.

Kedr Python is built from the [Kedr](https://github.com/name-cho/kedr) source tree —
a rebranded fork of `JetBrains/intellij-community` — together with Kedr Studio.
This repository carries the product description, the release artifacts and the
documentation that is specific to the Python product; the source code itself
lives in the main repository.

## Product

| | |
| --- | --- |
| Based on | PyCharm Community 2026.2.3 (`pycharm/262.10968.92`) |
| Executable | `bin\pycharm64.exe` |
| Build number | `PC-262.10968.SNAPSHOT` (prefix `PC-` kept for plugin compatibility) |
| Settings dir | `KedrPython2026.2` |

## Packages

| Package | File | Notes |
| --- | --- | --- |
| Portable ZIP | `kedr-python-262.10968.SNAPSHOT.win.zip` | Unpack, run `bin\pycharm64.exe`, no elevation |
| NSIS installer | `kedr-python-262.10968.SNAPSHOT.exe` | Per-user install with uninstaller |

Both are attached to the releases of the main repository.

## What is inside

- The community Python plugin with `ruff`, `uv`, `pyright`, `pyrefly`, `ty`, the LSP core,
  the type engine, Jupyter modules, pytest/unittest and the classic pydevd debugger.
- The MIT Russian language pack (`su.rus.language-pack`). The UI starts in English and
  offers to switch on first start; the language can be changed later in
  Settings | Appearance & Behavior | System Settings | Language.
- No Marketplace "Staff Picks", no uninstall feedback, no update checks, no vendor links.

Python DAP Debugger is not bundled: it needs the closed-source `intellij.platform.dap`
module that does not exist in the open-source tree. See `docs/plugins.md`.

## Building

The build runs from the main repository:

```
cd /d <kedr-repo>
python\installers.cmd -Dintellij.build.target.os=current
```

Add `-Dintellij.build.skip.build.steps=windows_exe_installer` for a ZIP-only build.
Artifacts appear in `out\kedr-python\artifacts`.

## License

Kedr Python is distributed under the Apache License 2.0. Upstream attribution is kept
in `NOTICE.txt` of the main repository; third-party components keep their own licenses.
JetBrains, IntelliJ IDEA and PyCharm are trademarks of JetBrains s.r.o. Kedr is an
independent project, not affiliated with or endorsed by JetBrains.
