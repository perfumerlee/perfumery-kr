# DEPLOY CHECKLIST

[GitHub]
- [ ] index.html 교체
- [ ] assets/og-perfumery-oem.jpg 존재 확인
- [ ] assets/favicon.svg 존재 확인
- [ ] robots.txt 확인
- [ ] sitemap.xml 확인
- [ ] site.webmanifest 확인
- [ ] CNAME = perfumery.kr 확인

[Google Apps Script]
- [ ] apps-script/Code.gs 전체 붙여넣기
- [ ] 저장
- [ ] 배포 > 배포 관리
- [ ] 새 버전 배포
- [ ] 실행 사용자: 나
- [ ] 액세스 권한: 모든 사용자
- [ ] 기존 /exec URL 유지 여부 확인

[실전 테스트]
- [ ] 010-123-4567 차단
- [ ] 010-1234-5678 허용
- [ ] 문의가 OEM_Inquiries에 저장
- [ ] Client 제출시각이 KST
- [ ] 이메일 알림 도착
- [ ] UTM 링크 테스트 시 컬럼 저장
- [ ] 접수 완료 후 5초 뒤 상단 복귀/새로고침


[v0.29 guide 구조]
- [ ] 기존 루트의 guide 개별 폴더 삭제
- [ ] `guide/` 폴더 전체 업로드
- [ ] `guide/index.html` 접속 확인
- [ ] 메인 페이지 Guide 링크가 `/guide/.../`로 이동하는지 확인
- [ ] sitemap.xml 교체
- [ ] llms.txt 교체
- [ ] 기존 공개 URL이 있었다면 redirect 계획 확인
