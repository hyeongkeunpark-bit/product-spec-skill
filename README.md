# product-spec-skill

Claude Code에서 `/product-spec`으로 호출하는 **Product Spec 작성 에이전트**.

프로젝트 코드와 git 히스토리를 자동 분석해 Wantedlab Product Spec 양식에 맞는 문서를 생성/수정합니다.

## 주요 기능

- 프로젝트 컨텍스트 자동 수집 (코드, git, 메모, 배포 설정)
- 영역(A/B/C) 자동 판별 — 기존 화면 변경 / 새 요소 추가 / 새 화면 생성
- 페이지 기반 변경 명세 (라우트별 입력 필드, 시나리오, 구현 참고)
- Mermaid 사용자 플로우 차트
- Confluence MCP 연동 시 자동 게시/갱신
- 스킬 업데이트 자동 알림

## 설치

프로젝트 루트에서 아래 명령어를 실행합니다:

```bash
mkdir -p .claude/skills/product-spec
curl -sf "https://raw.githubusercontent.com/hyeongkeunpark-bit/product-spec-skill/main/.claude/skills/product-spec/SKILL.md" \
  -o .claude/skills/product-spec/SKILL.md
```

## 사용법

Claude Code에서 아래 중 아무 표현으로 호출하면 됩니다:

```
/product-spec
```

또는 자연어로:

```
스펙 작성해줘
PRD 만들어줘
문서 정리해줘
```

### 신규 생성

`docs/PRODUCT_SPEC.md`가 없으면 자동으로 신규 생성 모드로 진입합니다.
프로젝트 코드/git/메모를 분석해 초안을 생성하고 `docs/PRODUCT_SPEC.md`에 저장합니다.

### 수정

`docs/PRODUCT_SPEC.md`가 이미 있으면 수정 모드로 자동 분기됩니다.
변경된 섹션만 업데이트하고 나머지는 그대로 유지합니다.

## 업데이트

스킬 실행 시 자동으로 최신 버전을 체크합니다.
업데이트가 있으면 아래와 같은 안내가 표시됩니다:

```
⚡ product-spec 스킬 업데이트가 있습니다 (로컬 1.0.0 → 최신 1.1.0)
업데이트: curl -sf "https://raw.githubusercontent.com/hyeongkeunpark-bit/product-spec-skill/main/.claude/skills/product-spec/SKILL.md" -o .claude/skills/product-spec/SKILL.md
```

안내에 나온 `curl` 명령어를 실행하면 최신 버전으로 업데이트됩니다.

## 요구사항

- [Claude Code](https://claude.ai/claude-code) CLI, Desktop, 또는 IDE 확장
- (선택) Confluence 자동 게시를 사용하려면 Atlassian MCP 연결 필요
