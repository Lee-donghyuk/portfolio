# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

단일 HTML 파일로 구성된 이동혁의 개발PM 직군 자기소개서 + 포트폴리오 페이지입니다. 빌드 도구나 의존성 없이 브라우저에서 직접 열어 사용합니다.

## Running

```
# 브라우저에서 직접 파일 열기 (빌드 불필요)
start 자소서_페이지.html
```

## Architecture

`자소서_페이지.html` 한 파일에 HTML/CSS/JS가 모두 포함된 단일 파일 구조입니다.

- **레이아웃**: 고정 사이드바(`<aside>`) + 스크롤 가능한 메인 콘텐츠(`<main>`) 구조
- **CSS**: `<style>` 블록에 인라인 작성, CSS 변수(`--bg`, `--accent` 등)로 색상 테마 관리
- **JS**: 파일 끝 `<script>` 블록에 `IntersectionObserver` 기반 스크롤 스파이만 포함 (사이드바 활성 항목 변경)
- **섹션 구성**: `<section id="s1">` ~ `<section id="s6">` + `<section id="portfolio">`
- **이미지**: base64 인코딩으로 HTML 내부에 직접 임베드 (파일 크기가 큰 이유)

## Content Sections

| ID | 제목 |
|----|------|
| s1 | 성격 장단점 |
| s2 | 게임 업계에 지원한 이유 |
| s3 | 개발PM 강점 및 역량 |
| s4 | 개발PM을 위한 노력과 경험 |
| s5g | 게임 분석 역량 |
| s6 | AI를 활용한 회의 관리 자동화 경험 |
| portfolio | 포트폴리오 (Google Drive PDF 링크 2개) |

## Editing Notes

- 섹션 내용은 `.block` div 단위로 구성되며, `.block-title`과 `<p>` 태그로 이루어짐
- `.tag` 스팬으로 키워드 태그 표시
- 사이드바 링크는 `<nav id="sidebar-nav">` 안에 수동으로 관리 — 섹션 추가/제거 시 사이드바도 함께 수정 필요
- 포트폴리오 링크(Google Drive URL)는 `<section id="portfolio">` 안에 하드코딩되어 있음
