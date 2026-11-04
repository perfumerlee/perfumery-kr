# perfumery.kr v0.50 배포 안내

**기준 파일:** v0.49 전체 패키지 (2026-11-04). **운영 서버 미배포:** 이 ZIP은 교체용 파일입니다.

## 목적

네이버 서치어드바이저 최근 30일 TOP 30 데이터의 주요 검색어를 기준으로 검색 의도별 기존 페이지를 보강했습니다. 검색 순위·클릭 상승은 보장하지 않습니다.

- `향수 oem` + `향수oem`: 노출 84, 클릭 5 → **홈페이지** 핵심 검색어 유지.
- `향수 제조`: 노출 12, 클릭 0 → **manufacturing/** 실제 제조 공정과 업체 비교 기준 강화.
- `향수 oem 문의 방법`: 노출 11, 클릭 0 → **guide/perfume-oem-process/** 문의 정보 5가지·작성 예시 추가.
- `퍼퓨머리하우스` + `퍼퓨머리 하우스`: 노출 25, 클릭 0 → **guide/what-is-perfumery/** 일반 명칭과 일비 브랜드 명확히 구분.
- `향수 소량 제작`: 노출 7, 클릭 0 → **guide/small-batch-perfume/** 50개/100개 판단 기준 보강.

**검색 보고서 전체 기준선:** 2026-11-03 업데이트, 최근 30일, PC+모바일, 노출 약 480, 클릭 46, CTR 9.7%. CTR을 순위로 오인하지 마세요.

## 실제 변경된 7개 HTML

1. `index.html` — 홈페이지 검색 제목과 폼/스크립트를 보존하고 내부 링크 문구/설명만 강화
2. `manufacturing/index.html` — 향수 제조 업체 비교 기준 및 페이지 설명
3. `guide/perfume-oem-process/index.html` — 향수 OEM 문의 방법/체크리스트와 제목·설명
4. `guide/what-is-perfumery/index.html` — 브랜드명과 일반 명칭 구분
5. `guide/perfume-oem-cost/index.html` — 공임과 재료비의 구분
6. `guide/small-batch-perfume/index.html` — 소량 향수 50개/100개 선택 기준
7. `guide/index.html` — 기존 가이드 탐색 문구

수정한 기존 가이드에는 해당 수정일 `2026-11-04`를 표시하고 JSON-LD의 `dateModified`를 일치시켰습니다. `datePublished`는 원래 날짜 그대로 유지했습니다.

## 안전 배포 순서

1. **현재 GitHub 운영 브랜치와 비교:** v0.49 이후 별도 수정이 있다면 파일을 통째로 덮어쓰지 말고 변경 부분만 병합하세요.
2. **권장:** `perfumery-kr-v0.50-changed-files.zip`에 들어 있는 7개 HTML을 **동일 경로**로 교체. `index.html`만 교체하면 나머지 콘텐츠 개선이 반영되지 않습니다.
3. Commit/push 후 HTTPS 도메인의 각 변경 페이지를 열어 본문과 버튼을 확인하세요. 사이트가 GitHub Pages 자동 배포라면 별도 Apps Script 배포 불필요.
4. `/guide/perfume-oem-process/` 하단의 ‘향수 OEM 제작 문의하기’ 버튼이 기존 메인 문의 폼 `/#contact`로 이동하는지 확인하세요.
5. 검색엔진에서 신규 URL 추가는 없습니다. 기존 사이트맵 그대로 사용하고, 네이버 서치어드바이저에서 변경한 핵심 URL을 수집 요청할 수 있습니다. 반복 과다 요청은 피하세요.
6. 약 2~4주 뒤 동일한 최근 30일 보고서로 ‘향수 OEM 문의 방법’, ‘향수 제조’, ‘퍼퓨머리’ 관련 검색어의 클릭·노출 변화를 비교하세요. 기간이 일부 겹칠 수 있으므로 주간 추이도 함께 보세요.

## 변경하지 않은 파일/기능

- `sitemap.xml`, `robots.txt`, `llms.txt`, CNAME 및 이미지 등 자산 그대로
- 홈페이지 CSS, 폼 입력 필드, 문의 전송 endpoint, UTM 추적 JavaScript 그대로
- Google Apps Script, Google Sheets 상담관리·매출관리 전혀 변경하지 않음
- 신규 페이지 생성 없음, 기존 11개 URL 유지

## 점검 결과

- 11/11 HTML의 title, description, canonical, H1, JSON-LD 검사 통과
- 모든 내부 링크·로컬 이미지 경로 유효
- 홈페이지 비-JSONLD JavaScript 원본과 동일
- 기존 robots/site map/llms/이미지 바이트 동일
- 보강한 6개 하위 페이지 `dateModified` 일치

## 주의

이것은 **v0.49 파일 기반**이므로, 실제 운영 서버가 같은 버전인지 확인하지 않고 일괄 덮어쓰면 운영 중 수정사항을 잃을 수 있습니다.
