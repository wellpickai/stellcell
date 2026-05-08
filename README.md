# 셀이즈LAB 줄기세포 피부주사 랜딩페이지 (v3 - SPA)

## 📦 파일 구성
- `index.html` — 랜딩페이지 (SPA 방식 — 메인 / EVENT 01 / EVENT 02 3개 뷰)
- `admin.html` — 관리자 페이지
- `logo_color.png` / `logo_white.png` — 로고
- `hero_model.png` — 히어로 인물 이미지
- `event1_prp.jpg` — EVENT 01 PRP 체험가 이미지
- `event2_prf.jpg` — EVENT 02 PRF 가정의 달 이미지

## 🎬 사용자 흐름

```
[메인 뷰]
 ├─ 헤더 (셀이즈LAB 로고)
 ├─ 히어로 (배경형 인물 + 줄기세포 피부주사 + 55만원 골드)
 ├─ 비교 섹션
 │   ├─ PRP/PRF 비교표
 │   └─ EVENT 카드 2개 (가격 표시)
 └─ 푸터

   ↓ EVENT 01 카드 클릭         ↓ EVENT 02 카드 클릭
   
[EVENT 01 뷰]                  [EVENT 02 뷰]
 ├─ ← 뒤로가기 버튼              ├─ ← 뒤로가기 버튼
 ├─ 체험가 이벤트 이미지         ├─ 가정의 달 이미지
 └─ 상담 신청 폼 (모카 톤)       └─ 상담 신청 폼 (그린 톤)
```

브라우저 뒤로가기 버튼도 정상 작동 (URL hash: `#event1`, `#event2`)

## ✨ v3 주요 변경사항
- **히어로**: 액자형 placeholder → 인물 이미지 **배경형** (체험가 이벤트 스타일)
- **"55"** 숫자: 골드 그라디언트 + 다크 외곽선 + 88px 초대형
- **비교 섹션**: PRP/PRF 비교표 추가, 카드 우측에 가격(55만원~/150만원~) 추가
- **SPA 페이지 전환**: 카드 클릭 시 해당 이벤트 화면으로 전환
- **"마감되기 전에 신청하세요"** 배지: 사이즈 업, 골드 메탈릭 + 펄스 + shimmer

## 🚀 사용 방법

### 1. 배포
8개 파일을 같은 폴더에 두고 웹 서버에 업로드.

### 2. 어드민 접속
`https://yourdomain.com/admin.html`
- 초기 비밀번호: `cellize2026` (로그인 후 [계정 설정]에서 변경)

### 3. 텔레그램 봇 연동
어드민 → [텔레그램 설정] 탭의 가이드 5단계
1. @BotFather → `/newbot` → BOT TOKEN 발급
2. 봇과 대화 시작
3. @userinfobot → CHAT ID 확인
4. 어드민에 입력 → [저장] → [테스트 전송]

## ⚠️ 운영 시 참고사항
1. DB는 브라우저 localStorage 저장 → 같은 브라우저로만 어드민 접근
2. 정식 운영 시 Firebase/Supabase 등 클라우드 DB 권장
3. 텔레그램 토큰은 클라이언트에 노출됨 → 대규모 운영 시 백엔드 프록시 권장

## 🔧 수정 가이드
- 가격: `index.html`에서 `compare-card-price` 검색
- 헤드라인: `.hero-title`, `.headline`, `.form-title` 검색
- 컬러: `:root` 안의 CSS 변수 (`--primary`, `--accent`, `--gold`)
- EVENT 카드 색상: `--event1-color`, `--event2-color`
- 히어로 인물 이미지: `hero_model.jpg` 교체
- 이벤트 이미지: `event1_prp.jpg`, `event2_prf.jpg` 교체
