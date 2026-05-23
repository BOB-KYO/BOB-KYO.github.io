# AGENTS.md — BOB-KYO.github.io Jekyll Portfolio Site

## 1. 프로젝트 개요

- **사이트**: `https://bob-kyo.github.io` — Kyoseok Hwang 개인 포트폴리오 (Jekyll 기반)
- **GitHub repo**: `https://github.com/BOB-KYO/BOB-KYO.github.io`
- **로컬 경로**: `D:\AIothch\worktrees\my-app-claude\github\BOB-KYO.github.io\`
- **테마**: Minimal Academic (Academic Pages fork)

## 2. 디렉터리 구조

```
BOB-KYO.github.io/
├── _config.yml        # Jekyll 전체 설정 (핵심 파일)
├── _pages/            # 주요 페이지 (about, cv, portfolio, publications, ...)
├── _portfolio/        # 포트폴리오 항목 (*.md)
├── _posts/            # 블로그 포스트 (YYYY-MM-DD-*.md)
├── _publications/     # 논문/연구 항목
├── _includes/         # 재사용 HTML 컴포넌트
├── _layouts/          # 페이지 레이아웃 템플릿
├── _sass/             # SCSS 스타일 (테마 기반)
├── assets/            # 이미지, JS, CSS 등 정적 파일
└── _data/             # 데이터 파일 (navigation.yml 등)
```

## 3. 작업 규칙 (Codex / Claude 공통)

1. **`_config.yml` 직접 수정 금지** — 사이트 전체 설정. 변경 시 사용자 명시 승인 필요.
2. **`_sass/` 직접 수정 금지** — 테마 SCSS 충돌 위험. 커스텀은 `assets/css/` 에서.
3. **이미지/바이너리 파일 추가 금지** — `assets/images/` 안 기존 파일만 참조.
4. **`main`/`master` 브랜치 직접 push 금지** — PR 은 사용자 결정.
5. **Jekyll Front Matter** — 새 페이지/포스트는 반드시 YAML front matter (`---`) 포함.

## 4. 자주 쓰는 파일 패턴

| 작업 | 파일 위치 | 비고 |
|---|---|---|
| 새 포트폴리오 항목 | `_portfolio/portfolio-N.md` | layout: single |
| 새 블로그 포스트 | `_posts/YYYY-MM-DD-title.md` | layout: single |
| About 페이지 수정 | `_pages/about.md` | 메인 소개 |
| CV 수정 | `_pages/cv.md` | 학력/경력 |
| 내비게이션 수정 | `_data/navigation.yml` | 상단 메뉴 |

## 5. AI 대시보드 개발 (Task B 전용)

본 사이트에 AI 에이전트 현황 대시보드를 추가할 예정:
- **목표**: AI 뉴스, 모델 토큰/로그, 에이전트 현황을 한눈에 볼 수 있는 페이지
- **구현 방식**: 신규 Jekyll 페이지 (`_pages/ai-dashboard.md`) + static JSON/HTML
- **branch**: `feature/ai-dashboard` 에서 작업 → PR → 사용자가 main merge 결정

## 6. 병렬 에이전트 분업

| 에이전트 | 담당 영역 |
|---|---|
| Claude (Claude Code) | 페이지 구조 설계, HTML/Liquid 템플릿, 대시보드 레이아웃 |
| Codex (Ouroboros backend) | 콘텐츠 채우기, 마크다운 작성, 데이터 파일 갱신 |

두 에이전트는 **각기 다른 파일**에 작업 → 충돌 없음.
Claude: `_pages/`, `_includes/`, `_layouts/`
Codex: `_portfolio/`, `_posts/`, `_data/`, `_pages/cv.md`

## 7. 로컬 빌드 (선택)

```bash
# WSL 또는 macOS
cd /path/to/BOB-KYO.github.io
bundle install
bundle exec jekyll serve --livereload
# 브라우저: http://localhost:4000
```

단, Windows 환경에서는 Jekyll gem dependency 관리가 복잡할 수 있음 — GitHub Pages 직접 확인 권장.

## 8. Ouroboros 사용 시

Ouroboros seed의 `constraints` 에 반드시 명시:
```yaml
constraints:
  - "작업 디렉토리: /mnt/d/AIothch/worktrees/my-app-claude/github/BOB-KYO.github.io/"
  - "feature/ai-dashboard 브랜치에서만 작업"
  - "_config.yml, _sass/ 수정 금지"
  - "바이너리·이미지 파일 추가 금지"
```
