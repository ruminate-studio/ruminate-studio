# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

Ruminate Studio 회사 홈페이지. 정적 웹사이트로 빌드 도구나 프레임워크 없이 순수 HTML/CSS/JS로 구성되어 있다. GitHub Pages로 호스팅되며 커스텀 도메인은 `ruminate.studio`.

## Architecture

- `index.html` — 단일 페이지 사이트. 섹션: Hero, About, Products (Readog), Contact, Footer. 인라인 `<script>`에 smooth scroll과 IntersectionObserver 기반 fade-in 애니메이션 포함.
- `style.css` — 전체 스타일. Inter 폰트 사용. 모바일 퍼스트 레이아웃, 640px/480px 브레이크포인트.
- `CNAME` — GitHub Pages 커스텀 도메인 설정 파일.

## Development

빌드/번들링 과정 없음. `index.html`을 브라우저에서 직접 열어 확인.

```
open index.html
```

## Design Conventions

- 브랜드 컬러: `#C44525` (CTA 버튼, 링크 언더라인)
- 타이포그래피: Inter (Google Fonts), `clamp()` 사용한 반응형 폰트 크기
- 레이아웃: `.container` max-width 760px 중앙 정렬
- 섹션 간 구분: `border-top: 1px solid #eee`, 패딩 120px (모바일 80px)
- 애니메이션: `.fade-in` / `.visible` 클래스 기반 스크롤 트리거

## Git Conventions

커밋 메시지는 한국어 본문과 함께 conventional commit prefix 사용 (feat, chore 등).
