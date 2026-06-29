# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## 프로젝트 개요

게임 업계 신입 개발PM 취업 준비 포트폴리오. 자기소개서 페이지와 취업 준비 로드맵으로 구성.

## 파일 구조

- `index.html` — 메인 자기소개서 페이지 (HTML + CSS + JS 단일 파일)
- `ROADMAP.md` — 개발PM 취업 준비 로드맵 (6개월~1년)
- `CLAUDE.md` — 이 파일

## 개발 방법

빌드 도구 없음. 브라우저에서 직접 파일을 열어 확인.

```
# 브라우저로 열기 (Windows)
start index.html

# 또는 VS Code Live Server 확장 사용 권장
```

## 아키텍처

### index.html

**단일 파일 구조** — 외부 의존성 없이 HTML 파일 하나로 완결. 배포는 GitHub Pages.

**레이아웃:** 고정 좌측 사이드바(240px) + 메인 콘텐츠(max-width 780px), Flexbox 기반

**디자인 시스템 (CSS 변수 — `:root`)**
```css
--bg: #ffffff
--surface: #f8f9fa      /* 사이드바·블록 배경 */
--border: #e9ecef
--text-primary: #1a1a2e
--text-secondary: #6c757d
--accent: #2563eb       /* 블루 액센트 */
--accent-light: #eff6ff
--sidebar-w: 240px
```

**JS 동작:** Intersection Observer API로 스크롤 위치 감지 → 사이드바 현재 섹션 `.active` 강조

**섹션 구성 (01~06):** 개발PM 강점 및 역량 → 게임 업계 지원 이유 → 성격 장단점 → 노력과 경험 → 게임 분석 역량 → AI 회의 관리 자동화

## 코드 컨벤션

- **CSS 수정 시 반드시 CSS 변수 사용** — 직접 색상값(`#2563eb`) 하드코딩 금지
- **태그(`.tag`) 추가 시** 카테고리 색상 체계 유지 (PM기술/게임지식/AI자동화/경험)
- **JS:** 인라인 `onmouseover/onmouseout` 핸들러 신규 추가 금지 → CSS 클래스 기반으로 작성
- **애니메이션 금지:** 페이드인·슬라이드 등 화려한 효과 추가하지 않음

## 기술 스택 결정 사항

- **Vanilla CSS 유지** (Tailwind 사용 안 함) — 단일 HTML 파일 배포 구조에 최적
- 추후 Next.js 리빌드 시 Tailwind 도입 고려

## 예정된 개선 작업

- [ ] 섹션 순서 변경: 개발PM강점(01) → 게임업계지원이유(02) → 성격장단점(03) → 나머지 유지
- [ ] 히어로 카드 추가 (이름/학력/경험/스킬뱃지/PDF링크)
- [ ] 메타태그 / OG 태그 / 파비콘
- [ ] 태그 카테고리별 색상 구분 (PM/게임/AI/경험)
- [ ] 모바일 햄버거 메뉴 (768px 이하에서 사이드바 미노출)
