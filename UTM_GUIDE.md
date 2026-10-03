# perfumery.kr UTM 링크 사용 가이드

UTM은 “이 문의가 어디에서 들어왔는지” 확인하기 위한 추적 태그입니다.

기본 주소:
https://perfumery.kr/

권장 규칙:
- utm_source: 유입 플랫폼/출처
- utm_medium: 유입 방식
- utm_campaign: 캠페인 묶음 이름
- utm_content: 같은 캠페인 안에서 소재/문구 구분이 필요할 때
- utm_term: 검색 키워드 추적이 필요할 때

## 바로 사용할 링크

### Threads
https://perfumery.kr/?utm_source=threads&utm_medium=social&utm_campaign=oem_2026

### 네이버 블로그
https://perfumery.kr/?utm_source=naver_blog&utm_medium=content&utm_campaign=oem_2026

### ChatGPT Ads
https://perfumery.kr/?utm_source=chatgpt&utm_medium=ads&utm_campaign=oem_2026

### DM
https://perfumery.kr/?utm_source=dm&utm_medium=direct&utm_campaign=oem_sales

### Kakao
https://perfumery.kr/?utm_source=kakao&utm_medium=message&utm_campaign=oem_sales

## 소재별 구분 예시

Threads에서 글 2개를 따로 비교하고 싶다면:

https://perfumery.kr/?utm_source=threads&utm_medium=social&utm_campaign=oem_2026&utm_content=story_01

https://perfumery.kr/?utm_source=threads&utm_medium=social&utm_campaign=oem_2026&utm_content=price_50pcs

## 운영 권장

- source / medium은 가능한 한 고정된 이름을 반복 사용
- campaign은 월별 또는 목적별로 묶기
- 예: oem_2026, oem_oct, launch_50pcs
- 같은 광고 안에서 이미지/문구가 여러 개면 utm_content로 구분
- URL에 UTM이 없으면 해당 시트 컬럼이 비어 있는 것이 정상
- Referrer는 보조용이며 앱/메신저/브라우저 정책에 따라 비어 있을 수 있음
