# Changelog

## v0.1.0 — 2026-09-28
- First data release. Snapshot `20260928T070125717Z` of the official MCP Registry (whole list, 1,232 pages, 36,830 servers, 123,157 versions) and an npm sample of 3,000 packages (2,982 answered).
- D1 90-day change rate 28.4% (3,952/13,910), D2 field change between versions 50.7% (23.2% excluding description-only changes), D3 repository URL 76.1%, D4 registry vs npm `latest` mismatch 34.1% (1,017/2,982). No bulk-publish days.
- Aggregates only: `data/summary.json` (+ `.sha256`) and `drift-public.md`. No server or package names. PyPI not queried (robots.txt).

## Unreleased
- Repository skeleton: README (English, then Korean), license (data CC BY 4.0, code MIT), issue forms (question, data correction, metric request), release workflow with issue-label setup, citation file.
- No data yet. v0.1.0 will add `data/summary.json`, its `.sha256` and `drift-public.md`.
