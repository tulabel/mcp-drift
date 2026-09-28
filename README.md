# Tulabel mcp-drift

How fast do MCP servers change after you install them? Aggregate measurements of change ("drift") in the official MCP Registry.

> **v0.1.0 (2026-09-28):** first snapshot of the whole registry (36,830 servers, 123,157 versions) and an npm sample of 3,000 packages. Results: [`drift-public.md`](drift-public.md), data: [`data/summary.json`](data/summary.json).

- **What it measures**, from the official MCP Registry (`registry.modelcontextprotocol.io`, read-only public API) and npm (`registry.npmjs.org`):
  - **D1 — 90-day change rate**: the share of active servers (first published more than 90 days before the snapshot) that shipped at least one new version in the last 90 days. Remote-only and package servers are counted separately; days with bulk publishing are reported with and without.
  - **D2 — description and package change rate**: the share of servers whose description, package identifier, required or secret environment variable names, or remote URL changed between two adjacent versions.
  - **D3 — metadata fill rate**: how often the latest entries fill in repository URL, secret flags, transport type and remote endpoint.
  - **D4 — registry vs npm version mismatch (npm only)**: for a seeded random sample of npm packages listed in the registry, how often the registry's version differs from npm's `latest`. PyPI is not queried because its `robots.txt` disallows the JSON API.
- **Aggregates only.** No server names, package names or per-server results are published. Every number comes with its denominator and a 95% Wilson interval.

## Method and etiquette
- Sequential requests, at least 1.1 s apart, with a `User-Agent` that identifies Tulabel and a contact address. `Retry-After` is respected. Requests per host are recorded.
- Sources are checked against their `robots.txt` and terms before any automated request. A source that forbids it, or is unclear, gets zero requests.

## Files
| File | Content |
|---|---|
| `data/summary.json` | D1–D4 aggregates with denominators and 95% Wilson intervals |
| `data/summary.json.sha256` | Checksum |
| `drift-public.md` | Report (Korean, with an English summary) |

## Licenses
- Data and documentation: CC BY 4.0. Code (the release workflow): MIT. See [`LICENSE`](LICENSE).
- Registry and npm metadata are used only to compute aggregates. No third-party records are republished.

## Requests and contact
- Open an issue with the [question](../../issues/new?template=question.yml), [data correction](../../issues/new?template=data-correction.yml) or [metric request](../../issues/new?template=metric-request.yml) form. Issues are public: do not include confidential information, personal data or contact details, and do not name servers or packages. There is no promise of a reply or schedule.
- To cite this work, see [`CITATION.cff`](CITATION.cff).
- hello@tulabel.com · Updates: <https://tulabel.com/?utm_source=gh-release&utm_medium=tool&utm_campaign=mcp-drift-v0.1.0>

---

## 한국어

MCP 서버는 설치한 뒤 얼마나 빨리 바뀔까? 공식 MCP Registry의 변화("드리프트")를 집계로 잰다.

> **v0.1.0 (2026-09-28):** 레지스트리 전체 첫 스냅숏(서버 36,830개, 버전 123,157개)과 npm 패키지 표본 3,000개. 결과: [`drift-public.md`](drift-public.md), 데이터: [`data/summary.json`](data/summary.json).

- **잴 것**: 공식 MCP Registry(`registry.modelcontextprotocol.io`, 읽기 전용 공개 API)와 npm(`registry.npmjs.org`)에서 잰다.
  - **D1 — 90일 변화율**: 스냅숏 90일 전보다 먼저 처음 게시된 활성 서버 중, 최근 90일 안에 새 버전을 1개 이상 낸 서버의 비율. 원격 전용 서버와 패키지 서버를 따로 세고, 일괄 게시가 몰린 날은 포함·제외 두 값을 적는다.
  - **D2 — 설명·패키지 변화율**: 이웃한 두 버전 사이에 설명, 패키지 식별자, 필수·비밀 환경변수 이름, 원격 URL 중 하나라도 바뀐 서버의 비율.
  - **D3 — 메타데이터 채움률**: 최신 항목이 저장소 URL, 비밀 표시, 전송 방식, 원격 엔드포인트를 얼마나 채우는지.
  - **D4 — 레지스트리·npm 최신판 불일치율(npm만)**: 레지스트리에 있는 npm 패키지 중 시드 고정 무작위 표본에서, 레지스트리 버전이 npm `latest`와 다른 비율. PyPI는 `robots.txt`가 JSON API를 막아 조회하지 않는다.
- **집계만** 공개한다. 서버 이름·패키지 이름·서버별 결과는 싣지 않는다. 모든 값에 분모와 95% Wilson 구간을 붙인다.

## 방법과 요청 예절
- 순차 요청, 간격 1.1초 이상, Tulabel과 연락처를 밝힌 `User-Agent`를 쓴다. `Retry-After`를 따르고 호스트별 요청 수를 기록한다.
- 자동 요청 전에 `robots.txt`와 약관을 확인한다. 금지하거나 불명확하면 요청하지 않는다.

## 파일
- `data/summary.json`(D1~D4 집계, 분모·95% 구간), `data/summary.json.sha256`, `drift-public.md`(한국어, 영어 요약 포함).

## 라이선스
- 데이터·문서: CC BY 4.0. 코드(릴리스 워크플로): MIT. `LICENSE` 참고.
- 레지스트리·npm 메타데이터는 집계 계산에만 쓰고, 제3자 기록을 다시 게시하지 않는다.

## 요청과 연락
- 질문·데이터 정정·지표 요청 양식으로 이슈를 남겨 주세요. 이슈는 공개되므로 기밀·개인정보·연락처를 적지 말고, 서버·패키지 이름도 적지 마세요. 응답·일정은 약속하지 않습니다.
- 인용할 때는 `CITATION.cff`를 참고하세요.
- hello@tulabel.com · 소식 받기: <https://tulabel.com/?utm_source=gh-release&utm_medium=tool&utm_campaign=mcp-drift-v0.1.0>
