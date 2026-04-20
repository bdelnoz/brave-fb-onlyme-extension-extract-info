<!--
Document : README.md
Auteur : Bruno DELNOZ
Email : bruno.delnoz@protonmail.com
Version : v1.1.0
Date : 2026-04-20 11:31
-->
# brave-fb-onlyme-extension-extract-info

## Overview

This repository stores extraction artifacts related to Facebook post collection and browser network capture.

Current repository content is **data-oriented** (JSON/HAR artifacts) and does **not** include executable scripts in the repository root at this time.

## Repository content

- `facebook-posts-50-2026-03-28T09-03-26-661Z.json`
  - JSON array with extracted post-like objects (1 item currently present).
  - Object schema includes:
    - `postKey`
    - `permalink`
    - `authorName`
    - `authorProfileUrl`
    - `timestampIso`
    - `timestampLabel`
    - `audience`
    - `message`
    - `reactionsCount`
    - `commentsCount`
    - `sharesCount`
    - `extractedAt`

- `facebook-posts-50-2026-03-28T09-17-19-201Z.json`
  - JSON array currently empty (`[]`).

- `www.facebook.com.har`
  - HTTP Archive capture containing 38 requests.
  - Main observed hosts:
    - `static.xx.fbcdn.net`
    - `www.facebook.com`
    - `scontent-bru2-1.xx.fbcdn.net`

## Expected usage

Typical usage in this repository is:

1. Keep raw extraction artifacts for traceability.
2. Analyze JSON post payloads.
3. Analyze HAR network behavior for debugging or extraction validation.

## Quick inspection examples

### Check JSON file sizes and item count

```bash
python - <<'PY'
import json,glob
for p in sorted(glob.glob('facebook-posts-50-*.json')):
    with open(p, encoding='utf-8') as f:
        data = json.load(f)
    print(f"{p}: {len(data)} item(s)")
PY
```

### Display first JSON record (if available)

```bash
python - <<'PY'
import json
p='facebook-posts-50-2026-03-28T09-03-26-661Z.json'
with open(p, encoding='utf-8') as f:
    data=json.load(f)
print(data[0] if data else 'No records')
PY
```

### Count HAR entries

```bash
python - <<'PY'
import json
with open('www.facebook.com.har', encoding='utf-8') as f:
    har=json.load(f)
print(len(har.get('log',{}).get('entries',[])))
PY
```

## Documentation set

- `README.md`: repository overview and artifact usage.
- `INSTALL.md`: local requirements and setup notes for data inspection.
- `WHY.md`: project rationale and intended value.
- `CHANGELOG.md`: documentation history for this repository.

## Notes

- No script or feature behavior was modified in this documentation update.
- If scripts are added later, documentation should be extended to include their CLI, options, versioning, and operational workflow.
