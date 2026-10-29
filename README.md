![Brian Document Skills — 문서를 작성하는 파란색 캐릭터](assets/cover.webp)

# Brian Document Skills

사람이 읽고 이해하기 쉽고, AI가 필요한 지식을 찾아 활용할 수 있는 문서를 작성하기 위한 스킬입니다. `brian-docs`는 기술·지식 문서부터 로드맵, 버전별 계획, 릴리스·결정 기록까지 작성하고 다듬는 기준을 제공합니다.

## 어떤 작업에 사용하나요?

- **문서 작성**: 독자가 얻으려는 결과에 맞춰 사용법, 참조 문서, 개념 설명을 작성합니다.
- **문장 교정**: 핵심을 먼저 전달하고, 불분명한 표현과 반복 설명을 줄입니다.
- **구조 정리**: 문서별 역할을 구분하고, 공통 기준을 한 곳에서 관리하도록 참조를 정리합니다.
- **계획과 이력 관리**: 현재 계획과 배포된 결과, 중요한 결정의 배경을 구분해 기록합니다.
- **문서 검토**: 독자의 이해와 실행을 방해하는 문제를 찾아 위치, 영향, 수정안을 제시합니다.

## 설치하기

Codex 대화창에서 아래와 같이 요청하면 모든 프로젝트에서 사용할 수 있습니다.

```text
$skill-installer를 사용해 아래 저장소의 skills/brian-docs 스킬을 설치해줘.
https://github.com/thebriancompany/brian-ai-document-plugin
```

설치 후 `$brian-docs`를 입력해 스킬이 표시되는지 확인하세요. 표시되지 않으면 Codex를 다시 시작하세요.

## 사용하기

설치한 스킬은 `$brian-docs`로 호출하세요. 작업할 문서와 독자, 원하는 결과를 함께 알려주면 수정 범위를 명확하게 정할 수 있습니다.

### 기존 문서 다듬기

```text
$brian-docs를 사용해 docs/getting-started.md를 다듬어줘.
처음 사용하는 개발자가 순서대로 따라 할 수 있게 정리하고,
필수 조건과 예외는 유지하면서 중복 설명을 줄여줘.
```

### 문서 전체 검토하기

```text
$brian-docs를 사용해 docs/ 문서 전체를 검토해줘.
여러 문서에 반복된 정책과 역할이 겹치는 문서를 찾아줘.
수정하기 전에 문제 위치, 독자에게 미치는 영향, 수정안을 정리해줘.
```

### 계획과 릴리스 기록 정리하기

```text
$brian-docs를 사용해 다음 버전 계획과 릴리스 기록을 정리해줘.
진행 중인 목표는 docs/plans/에, 실제 배포가 확인된 변경은 docs/releases/에 기록해줘.
배포 여부를 확인할 수 없는 항목은 초안으로 표시해줘.
```

예시의 문서 경로는 프로젝트 구조에 맞게 바꿔 사용하세요.

## 다른 설치 방법

<details>
<summary>Codex의 특정 프로젝트에만 설치하기</summary>

Git이 설치된 macOS·Linux 환경에서 아래 명령을 실행하세요. `/path/to/project`는 스킬을 사용할 프로젝트의 실제 경로로 바꾸세요.

```sh
git clone https://github.com/thebriancompany/brian-ai-document-plugin.git
cd brian-ai-document-plugin
mkdir -p /path/to/project/.agents/skills
cp -R skills/brian-docs /path/to/project/.agents/skills/
```

`SKILL.md`와 `references/`가 함께 복사되어야 합니다. 해당 프로젝트를 Codex에서 열고 `$brian-docs`로 요청하세요.

팀과 공유하려면 `.agents/skills/brian-docs/` 폴더를 프로젝트의 버전 관리에 포함하세요.

설치 경로는 [공식 Codex 스킬 문서](https://learn.chatgpt.com/docs/build-skills)를 참고하세요.

</details>

<details>
<summary>설치 없이 사용하기</summary>

이 저장소의 파일을 읽을 수 있는 AI 에이전트에 [brian-docs 스킬](skills/brian-docs/SKILL.md)을 읽고 적용하도록 요청하세요.

```text
skills/brian-docs/SKILL.md를 읽고 적용해줘.
이 저장소를 처음 접하는 개발자가 프로젝트의 목적과 사용 방법을 알 수 있도록
README.md를 작성해줘. 저장소에서 확인할 수 있는 내용을 근거로 작성해줘.
```

</details>

## 작성 기준

각 문서는 하나의 독자 목표에 집중합니다. 기존 문서의 목적과 구조를 존중하고, 요청한 범위와 직접 영향을 받는 문서를 중심으로 수정합니다. 확인된 사실과 제안·가정을 구분하며, 짧게 쓰기 위해 필수 단계나 예외를 생략하지 않습니다.

세부 기준은 아래 문서에서 관리합니다.

| 문서 | 다루는 내용 |
| --- | --- |
| [스킬 정의](skills/brian-docs/SKILL.md) | 작업 범위, 지침 선택, 검토와 완료 기준 |
| [글쓰기 지침](skills/brian-docs/references/writing.md) | 문서 유형, 문장·섹션 구성, 예시와 표현 |
| [구조 지침](skills/brian-docs/references/structure.md) | 문서 분리·통합, 기준 위치, 참조와 변경 순서 |
| [계획과 이력 지침](skills/brian-docs/references/planning-and-history.md) | 로드맵, 버전별 계획, 릴리스·결정 기록의 관리와 보존 |
