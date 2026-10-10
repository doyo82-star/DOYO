# 스마트 도서관 예약 시스템 (Smart Library Reservation)

Google Apps Script 및 Google Sheets와 실시간 연동되는 모던한 도서관 도서 검색 및 대출 예약 웹 애플리케이션입니다.

---

## 🚀 GitHub 및 Vercel 배포 가이드

이 프로젝트는 **Vercel**에 최적화되어 있어 별도 설정 없이 원클릭으로 바로 배포할 수 있습니다.

### 1. GitHub 저장소에 코드 올리기

터미널에서 아래 명령어를 차례대로 실행하여 GitHub 리포지토리에 코드를 푸시합니다:

```bash
# Git 초기화 (필요한 경우)
git init

# 모든 변경 사항 추가
git add .

# 커밋 생성
git commit -m "feat: 스마트 도서관 예약 시스템 Vercel 배포 준비 완료"

# GitHub 리포지토리 연결 및 푸시
git branch -M main
git remote add origin https://github.com/사용자아이디/리포지토리이름.git
git push -u origin main
```

---

### 2. Vercel에서 배포하기

1. [Vercel](https://vercel.com)에 로그인합니다.
2. 대시보드 우측 상단 **[Add New...] > [Project]**를 클릭합니다.
3. 위에서 푸시한 **GitHub 저장소를 선택(Import)**합니다.
4. **Configure Project** 설정 확인:
   - **Framework Preset**: `Vite` (자동 감지됨)
   - **Build Command**: `npm run build` (자동 지정됨)
   - **Output Directory**: `dist` (자동 지정됨)
5. *(선택 사항)* **Environment Variables** (환경 변수):
   - Key: `VITE_GAS_URL`
   - Value: `https://script.google.com/macros/s/AKfycbyklKrB7YUSSzRJxbCtdjLUrTLgcPDZCzP-lf2cxlNDREhgjumA_FaXxvzly8omWLRVuw/exec`
   *(지정하지 않아도 코드 내 기본값으로 자동 연동됩니다)*
6. 하단 **[Deploy]** 버튼을 클릭하면 약 20~30초 만에 전 세계 CDN으로 라이브 배포가 완료됩니다!

---

## 🛠️ 주요 기능

- **도서 실시간 검색 및 필터**: 제목, 저자, 카테고리별 실시간 필터링
- **원클릭 예약 신청**: 선택한 도서 정보 확인 후 예약자 성함 및 이메일로 신청
- **구글 스프레드시트 실시간 동기화**: 예약 즉시 시트에 기록 및 도서 상태 '예약중' 전환
- **내 예약 내역 확인 및 취소**: 이메일 기반 예약 조회 및 취소 시 도서 자동 복구
- **반응형 디자인**: 모바일 및 데스크톱 모든 디바이스 최적화 (Tailwind CSS)
- **Vercel SPA 라우팅 지원**: `vercel.json`을 통한 깔끔한 새로고침 및 경로 유지
