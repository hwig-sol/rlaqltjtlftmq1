# 바이브코딩 워크숍 사이트

## 프로젝트 개요
- **이름**: 바이브코딩 워크숍 (VIBE CODING Workshop)
- **목적**: 비개발자 대상 Claude Code 워크숍 랜딩 & 수강신청 사이트
- **기술**: 순수 HTML/CSS 정적 사이트 (프레임워크 없음)
- **배포**: GitHub → Vercel 자동 배포
- **레포**: https://github.com/hwig-sol/rlaqltjtlftmq1
- **배포 URL**: https://rlaqltjtlftmq1.vercel.app/솔%20개발/

## 파일 구조
```
솔 개발/
├── common.css          # 공통 스타일시트 (라이트 테마, CSS 변수, nav/footer/버튼 등)
├── index.html          # 메인 랜딩 (히어로 + 커리큘럼 그리드)
├── intro.html          # 소개 페이지 (강사소개 + 현장사진 + Before/After + 실습결과물 슬라이더 + 추천대상 체크리스트 + 로드맵)
├── schedule.html       # 일정 (강의일정 카드 + 캘린더 + 정보카드 + 챗봇)
├── apply.html          # 수강신청 (폼 + 캘린더)
├── qna.html            # Q&A (강의별 준비물 + FAQ 아코디언 + 연락처)
├── access.html         # 강의자료 (비밀번호 입력 → lecture-N.html 이동)
├── 이미지/
│   ├── 강의 모습.png        # 강사 사진 (intro.html에 사용)
│   ├── 결과물1~7_*.png      # 실습 결과물 스크린샷 (intro.html 슬라이더)
└── .claude/
    └── launch.json         # 프리뷰 서버 설정 (port 3847)
```

## 디자인 시스템 (common.css)
- **테마**: 라이트 (`--bg: #F6F5FB`, `--bg-card: #FFFFFF`, `--text: #1E1B3A`)
- **히어로만 다크**: `--bg-hero: linear-gradient(135deg, #2D2B55, #3D3A6E)`
- **강의별 색상**:
  - 1강: `--color-1: #6C5CE7` (보라)
  - 2강: `--color-2: #00B4B5` (틸)
  - 3강: `--color-3: #E8A317` (노랑/주황)
  - 4강: `--color-4: #E85D5C` (빨강) — schedule.html에서는 `#2563EB` 파랑 사용
- **폰트**: Noto Sans KR (Google Fonts)
- **모든 페이지**: `<link rel="stylesheet" href="common.css">` 공유

## 네비게이션 (모든 페이지 공통)
```
소개(intro.html) | 커리큘럼(index.html#curriculum) | 일정(schedule.html) | Q&A(qna.html) | 강의자료(access.html) | [수강 신청](apply.html)
```

## 커리큘럼 내용
| 강 | 제목 | 핵심 내용 |
|---|------|----------|
| 1강 | 내 컴퓨터에 AI 개발자 앉히기 | Claude 앱 실전 체험, Claude Code 설치·실습, 업무 자동화 |
| 2강 | 만든 걸 세상에 내보내기 | GitHub/Vercel 배포, CLAUDE.md 작성법, 커스텀 슬래시 명령어 |
| 3강 | 외부 세계와 연결하기 | API 연동, MCP 서버 설정 |
| 4강 | 혼자서도, 함께도 계속 만들기 | 멀티 디바이스, 협업, 멀티 에이전트, Hooks, 터미널 멀티태스킹 |

## 일정 정보
- **1강**: 2026-04-01 (화) 19:00~21:00
- **2강**: 2026-04-08 (화) 19:00~21:00
- **3~4강**: 일정 확정 시 안내
- **장소**: 누리꿈스퀘어 7층
- **가격**: 강의당 5만원 (Claude Pro 구독 별도)

## 강의별 준비물 (qna.html)
- **1강**: 노트북, Claude 가입, Claude Pro 유료 구독
- **2강**: 노트북, GitHub/Vercel 가입, 아이디어 구상
- **3강**: 노트북, 해외 결제 카드, 2강 프로젝트
- **4강**: 노트북, 스마트폰, 데스크탑 원격(선택)

## 주요 컴포넌트
- **캘린더**: schedule.html, apply.html에 JS 캘린더 (월 이동, 강의일 색상 마커)
- **챗봇**: schedule.html 우하단 플로팅 (비용/준비물/장소/시간/코딩/환불/일정/주차 FAQ)
- **실습 결과물 슬라이더**: intro.html — 7개 이미지 자동 좌측 스크롤, hover 시 정지, 색상 테두리+제목
- **Before/After 카드**: intro.html — 1~2강/3강/4강 수료 후 변화
- **FAQ 아코디언**: qna.html — 비용/수업/장소&시간/준비물 카테고리
- **비밀번호 접근**: access.html — vibe1~vibe4 입력 시 각 강의자료 페이지 이동

## intro.html 이미지 사용 현황
- **강사 사진**: `이미지/강의 모습.png` → instructor-photo에 적용 (display:block)
- **현장 사진 3칸**: 빈 placeholder (이미지 추가 예정)
- **결과물 슬라이더 7개**: 이미지 적용 완료, 각 카드에 색상 테두리 + 컬러 제목
  1. 서비스 프로토타입 구현
  2. 서비스 프로토타입 구현 2
  3. 회사 홈페이지 제작
  4. 시장조사 및 보고서 생성
  5. 서비스페이지 및 챗봇 생성
  6. 개인업무비서 만들기
  7. 서비스 제작

## 작업 시 유의사항
- 모든 페이지는 common.css를 공유하므로, 공통 스타일 변경 시 전체 영향 확인 필요
- 캘린더 이벤트 색상은 강의 카드 색상과 매칭 (1강=보라, 2강=틸)
- 히어로 섹션만 다크, 나머지는 라이트 테마 유지
- 변경 후 `git push`하면 Vercel 자동 배포됨
- 프리뷰 서버: `솔 개발/` 기준 port 3847 (.claude/launch.json)
