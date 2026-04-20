<!--
Document : INSTALL.md
Auteur : Bruno DELNOZ
Email : bruno.delnoz@protonmail.com
Version : v1.0.0
Date : 2026-04-20 11:31
-->
# INSTALL

## Purpose

This repository does not currently provide installable software or executable scripts.
It mainly contains extraction artifacts (`.json`, `.har`) for analysis.

## Local prerequisites (for analysis)

- Python 3.9+ (recommended)
- Optional tools:
  - `jq` for JSON CLI queries
  - Any HAR viewer or browser developer tools

## Minimal setup

```bash
# 1) Clone repository
git clone <repo-url>
cd brave-fb-onlyme-extension-extract-info

# 2) Verify available artifacts
ls -1 *.json *.har

# 3) Optional: inspect JSON quickly
python - <<'PY'
import json,glob
for p in glob.glob('*.json'):
    with open(p, encoding='utf-8') as f:
        data=json.load(f)
    print(p, type(data).__name__, len(data) if hasattr(data,'__len__') else 'n/a')
PY
```

## No build step

- No compilation step is required.
- No package installation is required for basic inspection.

## Data handling recommendation

- Keep raw files unchanged.
- If transformations are needed, generate derived files in a separate folder to preserve originals.
