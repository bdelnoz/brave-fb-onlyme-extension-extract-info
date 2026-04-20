<!--
Document : WHY.md
Auteur : Bruno DELNOZ
Email : bruno.delnoz@protonmail.com
Version : v1.0.0
Date : 2026-04-20 11:31
-->
# WHY

## Why this repository exists

This repository centralizes extraction artifacts generated from Facebook browsing context, with a focus on:

1. Keeping a reproducible snapshot of extracted post data.
2. Preserving associated network traces (`.har`) for technical validation.
3. Supporting audit/debug workflows for extraction quality.

## Practical value

- **Traceability**: raw artifacts remain available for review.
- **Debugging**: HAR requests can explain missing or partial extraction fields.
- **Data quality checks**: JSON payloads can be validated over time.

## Current scope

- Data artifacts only.
- No executable pipeline script included in the current repository state.

## Future scope (if needed)

If extraction scripts are added in the future, this repository can evolve into:

- script + artifact workflow,
- versioned extraction process,
- repeatable diagnostics and reporting.
