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
