# perfumery.kr — ILLVII Perfumery House

현재 패키지는 `https://perfumery.kr/` 루트 배포 기준입니다.

## GitHub 저장소 권장 구조

/
├─ index.html
├─ CNAME
├─ robots.txt
├─ sitemap.xml
├─ llms.txt
├─ site.webmanifest
├─ UTM_GUIDE.md
├─ README.md
├─ assets/
│  ├─ illvii-logo.svg          ← 기존 브랜드 로고 유지
│  ├─ og-perfumery-oem.jpg
│  ├─ favicon.svg
│  ├─ favicon-32.png
│  ├─ apple-touch-icon.png
│  └─ icon-512.png
└─ apps-script/
   └─ Code.gs                  ← 백업/관리용. 실제 실행은 Google Apps Script에서 함

## 현재 적용 기능

### 웹페이지
- 루트 랜딩페이지
- 소량 향수 OEM / ODM SEO
- canonical / Open Graph / Twitter Card
- OG 이미지 1200×630
- favicon / Apple Touch Icon / manifest
- robots.txt / sitemap.xml / llms.txt
- 개인정보처리방침 모달
- 문의폼 유효성 검증
- 휴대전화 `010` 11자리 검증
- UTM source / medium / campaign / content / term 저장
- referrer / page URL 저장
- KST 제출시간 저장
- 제출 성공 후 5초 카운트다운
- 5초 후 상단 이동 + 새로고침
- 즉시 첫 화면 복귀 버튼

### Google Apps Script
- Google Sheet `OEM_Inquiries` 저장
- 서버 측 필수값 재검증
- 서버 측 010 휴대전화 11자리 재검증
- formula injection 방지
- Lead ID 생성
- KST 시간 보정
- 문의 접수 후 `business@perfumery.kr` 이메일 알림
- 이메일 실패 시에도 Sheet 저장은 유지

## 배포할 때

### GitHub
웹페이지 변경 시 주로 `index.html`을 교체합니다.
SEO/아이콘 파일을 바꾼 경우 `assets/`, `robots.txt`, `sitemap.xml`, `site.webmanifest`도 함께 반영합니다.

### Google Apps Script
`apps-script/Code.gs` 내용을 Apps Script의 Code.gs에 붙여넣고 새 버전으로 웹 앱을 재배포합니다.

현재 Web App URL:
https://script.google.com/macros/s/AKfycbzyssSZkhcLPpUeRZIhtylKzeGGuUNlX79KXnk2pif14k1sViNY4hJJ1_PKKt02QHDD/exec

## UTM
실전 링크는 `UTM_GUIDE.md` 참고.

## 운영 체크
1. 테스트 문의 1건 제출
2. Google Sheet 저장 확인
3. business@perfumery.kr 이메일 알림 확인
4. Client 제출시각 KST 확인
5. 010 형식이 아닌 전화번호 차단 확인
6. 5초 후 첫 화면 복귀 확인


## v0.24 변경사항
- `이름 / 브랜드명` 필드 예시 순서를 실제 라벨 순서에 맞게 수정했습니다.
- 예시: `김하린 / 오브제랩`


## v0.25 메타/SEO 정리
- title: `소량 향수 OEM · 50개부터 | ILLVII Perfumery House`
- description: 소량 제작, 향 개발, 혼합, 충진, 라벨링 핵심 내용 반영
- canonical: `https://perfumery.kr/`
- Open Graph / Twitter Card 제목·설명·이미지 정리
- og:image 1200×630 고정
- Organization / WebSite / WebPage / Service / FAQ 구조화 데이터 정리
- ko-KR hreflang 적용


## v0.26 메타/SEO 변경
- 타이틀 한글 브랜드명 적용:
  `소량 향수 OEM · MOQ 50개부터 | 일비 퍼퓨머리 하우스`
- 메타 description에 `향수 제조`, `MOQ 50개`, `소량 향수 OEM·ODM` 반영
- keywords에 향수 제조/향수 제조업체/MOQ/향수 최소수량 등 보강
- Open Graph/Twitter 제목과 설명도 동일 방향으로 정리
- 구조화 데이터 Service / FAQ에 향수 제조 MOQ 50개 관련 내용 추가
- 한글 브랜드명과 영문 브랜드명을 함께 구조화 데이터에 등록


## v0.27 AI citation / GEO 개선
- 중복 meta description / Open Graph / Twitter meta 정리
- Organization sameAs: 제로톤 네이버 블로그
- Person(YDO/이태하) sameAs: Threads @perfumer.lee
- WebPage datePublished / dateModified 추가
- 화면에 `향수 제조 핵심 정보` 정답형 블록 추가
- 구조화 데이터 FAQ와 동일한 실제 화면 FAQ 8개 추가
- `/moq-50/` 독립 가이드 페이지 추가
- `/perfume-oem-cost/` 독립 가이드 페이지 추가
- 루트 페이지에서 두 가이드로 내부 링크 추가
- sitemap.xml에 신규 가이드 2개 추가
- llms.txt에 공식 프로필/핵심 사실/가이드 URL 정리
- footer에 공식 네이버 블로그 / 조향사 Threads 링크 추가


## v0.28 Knowledge Hub 확장
신규 가이드:
- `/fragrance-development/` 향 개발 비용/진행 방식
- `/small-batch-perfume/` 소량 향수 제작
- `/perfume-oem-process/` OEM 진행 과정
- `/supplied-materials/` 사급 부자재

기존:
- `/moq-50/`
- `/perfume-oem-cost/`

메인 페이지의 Guide 카드도 2개 → 6개로 확장했고,
sitemap.xml / llms.txt / 각 가이드의 내부 링크를 모두 갱신했습니다.

실제 제조 사진은 추후 교체 가능하도록 현재 기존 이미지 구조를 유지했습니다.


## v0.29 /guide + GEO 정리

### URL 구조
- `/guide/`
- `/guide/moq-50/`
- `/guide/perfume-oem-cost/`
- `/guide/fragrance-development/`
- `/guide/small-batch-perfume/`
- `/guide/perfume-oem-process/`
- `/guide/supplied-materials/`

### GEO / AI 인용 개선
- `/guide/` 허브(CollectionPage + ItemList) 추가
- 모든 내부 링크 / canonical / breadcrumb / sitemap / llms.txt를 `/guide/` 구조로 통일
- Organization / Service에 `areaServed` 추가
- WebPage 및 가이드 페이지에 서울 지역 문맥 추가
- `geo.region=KR-11`, `geo.placename=서울특별시 도봉구`
- 화면에도 `Seoul, Korea`와 제조 핵심 사실을 명시
- 공식 네이버 블로그 / Threads 연결 유지
- 실제 좌표(latitude/longitude)는 검증하지 않은 값을 넣지 않았습니다.

주의:
기존 `/moq-50/` 등의 URL을 이미 외부에 공개했다면, 나중에 해당 경로를 `/guide/.../`로 301 redirect 하는 것을 권장합니다.


## v0.30 Naver Search Advisor verification
루트 `index.html`의 `<head>`에 다음 태그를 추가했습니다.

`<meta name="naver-site-verification" content="4c6ba261f43dbfc13202a8765830362b8e2ad880" />`


## v0.31 Daum Webmaster Tool
`robots.txt` 파일 하단에 Daum 웹마스터 도구 PIN을 추가했습니다.

`#DaumWebMasterTool:a1d432a51869bf6453cf7eed1bc12ba7b38fb518eb4d94fc35c67469d127e93f:Wz/rfTo9osfCpgVJS36Djg==`


## v0.32 이미지 없는 제조 정보형 디자인
- 메인 페이지의 Unsplash 제조 이미지를 모두 제거했습니다.
- 실제 제조 사진처럼 오해될 수 있는 스톡 이미지 대신 CSS/타이포그래피 기반 제조 인포그래픽으로 교체했습니다.
- Hero: MOQ 50 + Production Map
- 공정 시각화: 컨셉 → 샘플/사양 → 생산 → 검수/출고
- MOQ 조건 시각화: 용량 / 용기 / 향 / 패키지 / 공정
- Service 이미지 영역: Production Scope 4 Layers
- Experience 이미지 영역: 운영 맥락/연도/제작 기준 정보 패널
- Unsplash preconnect / dns-prefetch 제거
- 메인 페이지 최종 업데이트 날짜를 2026-10-15로 갱신
- 실제 공장 사진이 확보되면 정보형 섹션 일부에 보조 이미지로 추가하는 방식을 권장합니다.


## v0.33 실제 제조 아카이브 하이브리드
- v0.32의 정보형 구조는 유지하고 실제 제조사진을 결합했습니다.
- Hero를 제로톤 주식회사 실제 생산 아카이브로 교체했습니다.
- `Actual manufacturing` 섹션을 신설해 세척 → 내용물 준비 → 충진/조립 → 부자재 검수 → 라벨 → 포장/출고 흐름을 실제 사진 6장으로 보여줍니다.
- Experience 영역은 과거 완제품·패키지 제조 아카이브 3장으로 구성했습니다.
- 모든 이미지는 `/assets/manufacturing/` 아래 WebP로 최적화했습니다.
- 메인 이미지와 제조 사진 일부를 Organization/WebPage 구조화 데이터에도 연결했습니다.
- 기존 SEO/GEO 정보, Naver 인증 태그, Daum robots PIN은 유지합니다.


## v0.34 Manufacturing + Capabilities
- `/manufacturing/` 실제 제조 공정·생산 아카이브
- `/capabilities/` 향 개발·생산·사급·소량·재생산 가능 범위
- 메인에 두 페이지 진입 카드 추가
- sitemap.xml / llms.txt 갱신


## v0.37 original subpage restore
- `/manufacturing/`와 `/capabilities/`를 최초 v0.34 서브페이지 디자인/내용으로 되돌렸습니다.
- 메인 `index.html`의 비주얼 시스템을 서브페이지에 복제하지 않았습니다.
- `/capabilities/`는 v0.34 원본 그대로 유지합니다.
- `/manufacturing/`는 v0.34 원본에서 별도 `Manufacturing Archive` 섹션만 제거했습니다.
- 폰트/레이아웃/카드/헤더/푸터도 v0.34 고유 스타일을 유지합니다.


## v0.38 manufacturing refresh
- manufacturing 페이지 제목 가독성을 강화했습니다.
- manufacturing 페이지에서 메인과 중복되던 기존 이미지 사용을 줄이고, 공정별 Unsplash 제조 이미지를 적용했습니다.
- 공정별 출처 표기를 figcaption에 추가했습니다.
- capabilities 및 메인 index 구조는 유지했습니다.


## v0.39 korean labels + capabilities images
- index의 Manufacturing / Capabilities 카드 표기를 한글 중심으로 수정했습니다.
- manufacturing 페이지의 이미지 구성을 퍼퓨머리 중심으로 재조정했습니다.
- capabilities 페이지에 실제 제품/작업 이미지를 포함해 이해도를 높였습니다.
- 하단 관련 링크를 모두 한글화했습니다.


## v0.40 focused visuals
- Manufacturing 페이지 이미지를 3개 핵심 장면으로 축소하고, 6단계 공정은 텍스트 카드 중심으로 변경했습니다.
- Capabilities 페이지의 설명용 이미지를 제거하고 제작 범위/준비 상태별 진행 방식 중심으로 재구성했습니다.
- 메인 페이지 한글 카드 표기는 v0.39 그대로 유지합니다.


## v0.41 Product finish image
- Manufacturing 페이지의 `Product finish` 이미지 교체
- 기존 STILL LIFE 드로퍼 이미지 대신, 완제품 향수와 단상자가 함께 보이는 HOLIMUS 실제 제조 이미지를 사용
- "완성된 제품"이라는 섹션 메시지와 이미지 의미를 더 직접적으로 맞춤


## v0.42 inspection image change
- manufacturing 페이지의 `INSPECTION` 섹션 이미지를 교체했습니다.
- 작업자 클로즈업 사진 대신, 완제품과 패키지를 함께 보여주는 실제 제조 이미지로 변경했습니다.
- 공정 사이 확인/검수의 의미가 더 직관적으로 전달되도록 조정했습니다.


## v0.47 SEO / AI Search hardening

이번 버전은 화면 구조와 본문 카피를 변경하지 않고 검색·AI 해석 계층만 보강했습니다.

### 변경
- robots.txt에 Googlebot, Bingbot, Yeti, OAI-SearchBot, ChatGPT-User, OAI-AdsBot 명시 허용
- sitemap.xml에 제조 공정, 제작 가능 범위, 가이드 허브와 6개 상세 가이드를 모두 복구/등록
- llms.txt를 회사/브랜드/조향사/서비스/대표 문서 기준으로 확장
- 메인 JSON-LD의 Organization / Person / WebSite / WebPage / Service 연결 강화
- 6개 가이드에 Article 구조화 데이터와 YDO author / 제로톤 publisher 관계 추가
- 제조 공정·제작 가능 범위 페이지의 about / author / keywords 관계 강화
- hreflang, author, googlebot, bingbot 메타 보강
- 화면의 BODY 영역 해시 검증: 본문/레이아웃 변경 없음

### 중요
- 이 ZIP에는 Apps Script를 포함하지 않았습니다.
- 현재 사용 중인 이메일 알림 v0.46 Code.gs는 그대로 유지하세요.
