# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

Ruminate Studio 회사 홈페이지. 정적 웹사이트로 빌드 도구나 프레임워크 없이 순수 HTML/CSS/JS로 구성되어 있다. GitHub Pages로 호스팅되며 커스텀 도메인은 `ruminate.studio`.

## Architecture

- `index.html` — 단일 페이지 사이트. 섹션: Hero, About, Manifesto, Products (readog), Contact, Footer. 인라인 `<script>`에 i18n 번역, IntersectionObserver 기반 fade-in 애니메이션 포함.
- `style.css` — 전체 스타일. 모바일 퍼스트 레이아웃, 640px/480px 브레이크포인트.
- `CNAME` — GitHub Pages 커스텀 도메인 설정 파일 (`ruminate.studio`).

## Brand Assets

| 파일 | 용도 |
|------|------|
| `readog-icon.png` | 제품 아이콘 (512x512, 투명 배경, 브랜드 컬러 강아지) |
| `readog-icon.svg` | 제품 아이콘 SVG 원본 |
| `favicon.svg` | SVG favicon |
| `favicon-32x32.png` | PNG favicon (32x32) |
| `apple-touch-icon.png` | iOS 홈 화면 아이콘 (180x180) |

readog 아이콘은 모바일앱(`readog/frontend/assets/images/app_icon_foreground_source.svg`)의 foreground SVG에서 파생된다. 앱 아이콘 변경 시 웹사이트도 함께 업데이트해야 한다.

## Development

빌드/번들링 과정 없음. `index.html`을 브라우저에서 직접 열어 확인.

```
open index.html
```

## Design Conventions

- 브랜드 컬러: `#C44525` (CTA, 링크, 배지, 섹션 디바이더)
- 배경: `#fafaf8` (off-white)
- 타이포그래피:
  - 본문: Pretendard Variable (CDN), 폴백 `system-ui, -apple-system, sans-serif`
  - readog 제품명: Crimson Pro (Google Fonts), weight 500, letter-spacing 0.25em — 모바일앱 노트 이미지 브랜딩과 동일
- 레이아웃: `.container` max-width 760px 중앙 정렬
- 섹션 패딩: 120px (데스크톱), 80px (모바일)
- 애니메이션: `.fade-in` / `.visible` 클래스 기반 스크롤 트리거 (IntersectionObserver)
- 시각 효과: SVG grain 오버레이, gradient orb 애니메이션, ripple ring 펄스

## i18n

클라이언트 사이드 번역. `translations` 객체에 `en`/`ko` 키로 텍스트 정의. `data-i18n` 속성으로 번역 대상 요소 지정. `localStorage`에 언어 설정 저장, 기본값은 브라우저 언어 감지.

## Git Conventions

커밋 메시지는 한국어 본문과 함께 conventional commit prefix 사용 (feat, chore 등).

## Deployment

`main` 브랜치에 push하면 GitHub Pages가 자동 배포한다.
