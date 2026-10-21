# perfumery.kr v0.48 — 브랜드 SEO · AI 검색 정합성 개선

기준: **v0.47 SEO/GEO 패키지**. 정적 루트 전체를 포함한 배포용 ZIP입니다. 

## 이번에 변경한 사항

1. 메인 `WebSite.name`은 **일비 퍼퓨머리 하우스** 유지. `alternateName`에 실제 명칭에 기반한 **일비 퍼퓨머리 / ILLVII Perfumery House / perfumery.kr**을 순서대로 정리했습니다.
2. `Organization.brand`에 동일한 공식 브랜드의 짧은 표기를 추가했습니다. 운영 법인 **제로톤 주식회사**와 브랜드는 구분했습니다.
3. 전체 공개 10개 기존 HTML 페이지에서 `og:site_name`을 단일 공식 사이트 이름으로 통일했습니다. 기존 개별 SEO `<title>`과 description은 보존했습니다.
4. 설명형 콘텐츠 **`/guide/what-is-perfumery/`**를 새로 작성했습니다. 일반 용어 ‘퍼퓨머리’와 브랜드 이름의 차이, 조향사·제조·OEM 관계를 다룹니다. 회사로 오인하게 만드는 키워드 나열 대신 유용한 정보를 제공합니다.
5. 제작 가이드 허브에 해당 글 링크 추가, 메인 `WebSite.hasPart` 참조 추가.
6. `sitemap.xml`에 새 URL 포함 (총 11개). 실질 수정된 메인·가이드 허브·신규 글만 lastmod를 2026-10-21로 갱신했습니다.
7. `llms.txt`에서 새로운 글과 공식 회사·브랜드·일반명사 관계를 구분해 기재했습니다. `llms.txt`가 AI 검색 노출을 보장하지는 않습니다.

## 변경하지 않은 부분

- 메인 배너, 실사 제조 사진, 페이지 레이아웃, 제작 상담 버튼
- 메인 페이지의 모든 `<body>` 콘텐츠, FAQ UI, 개인정보처리방침, JavaScript, 폼
- Google Apps Script, Google Sheets, 이메일 알림, UTM 수집 (별도 관리 중)
- 네이버 검증 메타태그, 다음 웹마스터 검증, Bing, robots.txt, CNAME 및 OG 이미지
- 기존 가이드 6개·제조 공정·제작 범위 페이지의 **본문/제목/기능**

## 배포

정적 사이트 저장소 웹 루트에 ZIP 내용을 덮어쓰기 합니다. 이미 운영 중인 `Code.gs`나 앱스 스크립트는 교체·재배포하지 마세요.

주요 변경 파일: `index.html`, `guide/index.html`, `guide/what-is-perfumery/index.html` (신규), `sitemap.xml`, `llms.txt`, 그리고 OG 사이트명 정리를 위해 기존 8개 하위 페이지 HTML.

배포 후 확인:
- https://perfumery.kr/ 기존 UI 및 폼 보존
- https://perfumery.kr/guide/what-is-perfumery/ 200 OK, 링크 클릭 가능
- https://perfumery.kr/guide/ 가이드 7개 노출
- https://perfumery.kr/sitemap.xml 총 URL 11개
- Google Search Console에서 신규 URL 검사 → 색인 생성 요청, 1~4주 검색어별 노출 추이 확인
- 네이버 서치어드바이저 신규 URL 수집 요청 및 색인 상태 확인
- `퍼퓨머리`(일반어)와 `일비 퍼퓨머리`(브랜드) 검색어 성과를 구분해 평가

**유의:** 구조화 데이터는 검색엔진에 브랜드 이름을 *설명하는 신호*입니다. 단독 검색어의 상위 노출이나 AI 검색 인용은 보장되지 않습니다. 오프사이트 언급·공식 프로필의 명칭 일관성 등은 별도 운영 과제입니다.
