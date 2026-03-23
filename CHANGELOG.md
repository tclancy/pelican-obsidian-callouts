
## 2026-03-23
- Fix CI ruff failures from cookiecutter restructure: add docstring to `register()`, suppress D103 on test files, fix RUF059 unused variable

## 2026-03-21
- Restructured to match cookiecutter-pelican-plugin flat layout (no `src/`)
- Split `__init__.py` into `obsidian_callouts.py` (implementation) + `__init__.py` (re-export)
- Moved tests inside package as `test_obsidian_callouts.py`
- Added `.cruft.json` to track template commit (enables `cruft update`)
- Added `.editorconfig`, `CONTRIBUTING.md`, `tasks.py` from cookie cutter
- Expanded `pyproject.toml`: ruff config, autopub, optional markdown dep
