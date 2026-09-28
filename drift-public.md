<!-- SPDX-License-Identifier: CC-BY-4.0 · Copyright (c) 2026 Tulabel -->
# MCP 서버 변화율 실측 v0 (집계)

- 스냅숏: `20260928T070125717Z` (공식 MCP Registry 공개 API 2026-09-28T07:59:38.071Z, npm 공개 레지스트리)
- 항목(버전) 123157개, 서버 36830개. 이 문서는 **집계만** 싣는다. 개별 서버는 싣지 않는다.
- 레지스트리 메타데이터(서버 수준 필드)만 본다. 원격 서버가 같은 URL에서 도구를 바꾸는 것은 볼 수 없다.
- PyPI 패키지는 PyPI robots.txt가 JSON API를 막아 조회하지 않았다(D4는 npm만).

| 지표 | 값 |
|---|---|
| D1 90일 안에 새 버전을 낸 서버(전체) | 28.4% (3952/13910, 95% 27.7–29.2%) |
| D1 원격 전용 서버 | 29.6% (1707/5768, 95% 28.4–30.8%) |
| D1 패키지 서버 | 28.2% (2226/7887, 95% 27.2–29.2%) |
| D1 일괄 게시 의심일 제외 | 28.4% (3952/13910, 95% 27.7–29.2%) |
| D2 버전 사이 설명·패키지·환경변수·원격 URL 변화 | 50.7% (7804/15398, 95% 49.9–51.5%) |
| D2 설명만 바뀐 것 제외 | 23.2% (3575/15398, 95% 22.6–23.9%) |
| D3 저장소 URL | 76.1% (28014/36830, 95% 75.6–76.5%) |
| D3 비밀값 여부를 기계가 읽을 수 있음(패키지 서버 전체, 환경변수 없는 서버 포함) | 14.5% (2262/15566, 95% 14.0–15.1%) |
| D3 같은 값, 환경변수가 있는 패키지 서버 중 | 29.8% (2262/7592, 95% 28.8–30.8%) |
| D4 레지스트리 버전 ≠ npm 최신판(npm 표본) | 34.1% (1017/2982, 95% 32.4–35.8%) |

- 버전 간격 중앙값: 0.679일 (간격 86327개, 서버 15398개)
- 일괄 게시 의심일(하루에 전체의 5% 이상): 0일

## Summary (English)
- Snapshot `20260928T070125717Z` of the official MCP Registry (public API) and the npm registry; aggregates only, no per-server listing.
- Server-level registry fields only; tool changes behind an unchanged remote URL are not visible. PyPI is excluded because its robots.txt disallows the JSON API.

| Metric | Value |
|---|---|
| D1 servers with a new version in 90 days (all) | 28.4% (3952/13910, 95% 27.7–29.2%) |
| D1 remote-only servers | 29.6% (1707/5768, 95% 28.4–30.8%) |
| D1 package servers | 28.2% (2226/7887, 95% 27.2–29.2%) |
| D1 excluding bulk-publish days | 28.4% (3952/13910, 95% 27.7–29.2%) |
| D2 description/package/env/remote-URL change between versions | 50.7% (7804/15398, 95% 49.9–51.5%) |
| D2 excluding description-only changes | 23.2% (3575/15398, 95% 22.6–23.9%) |
| D3 repository URL | 76.1% (28014/36830, 95% 75.6–76.5%) |
| D3 machine-readable secret flags (all package servers, incl. those without env vars) | 14.5% (2262/15566, 95% 14.0–15.1%) |
| D3 same, among package servers that declare env vars | 29.8% (2262/7592, 95% 28.8–30.8%) |
| D4 registry version ≠ npm latest (npm sample) | 34.1% (1017/2982, 95% 32.4–35.8%) |

- Median gap between versions: 0.679 days. Bulk-publish days (≥5% of entries on one day): 0.
