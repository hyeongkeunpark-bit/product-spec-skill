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

Claude Code에게 이 레포 URL을 주고 설치를 요청하면 됩니다:

> 이 스킬 설치해줘 https://github.com/hyeongkeunpark-bit/product-spec-skill

## 사용법

```
/product-spec
```

또는 자연어로:

```
스펙 작성해줘
PRD 만들어줘
문서 정리해줘
```

- `docs/PRODUCT_SPEC.md`가 없으면 → 신규 생성
- `docs/PRODUCT_SPEC.md`가 있으면 → 변경 섹션만 수정

## 업데이트

스킬 실행 시 자동으로 최신 버전을 체크합니다. 업데이트가 있으면 안내가 표시됩니다.
