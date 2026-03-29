# lesson-skill

Claude Code로 1:1 인터랙티브 강의를 운영하기 위한 범용 강의 스킬 저장소다.
초급 실무자 교육부터 스킬 제작, 팀 단위 컨텍스트 엔지니어링까지 한 흐름으로 확장할 수 있다.

## 프로젝트 소개

`/lesson {COURSE_ID} {WEEK_NUM}` 형식으로 강의를 시작하면,
강의 스킬이 수강생 프로필과 코스 문맥을 바탕으로 맞춤형 진행을 돕는다.

이 저장소는 세 가지 축으로 구성된다.
- `skills/lesson/`: 실제 강의를 구동하는 Claude Code 스킬
- `courses/`: 강좌별 세계관, 난이도, 레슨 문서
- `guides/`: 강좌 제작자와 강사를 위한 운영 가이드

핵심 운영 원칙은 다음과 같다.
- 수강생이 직접 해보게 만든다.
- 한 번에 하나씩 진행한다.
- 난이도에 맞게 설명 깊이를 조정한다.
- 실무 문제 해결에서 출발해 점진적으로 구조 설계까지 확장한다.

## 코스 목록

### 1. CC101 — beginner
- **대상**: Claude Code를 처음 쓰는 비개발자·실무자
- **목표**: 파일 읽기, 계획 수립, 문서 작성, Git/GitHub 첫 사용까지 한 사이클 완주
- **다음 단계**: 반복 업무를 스킬로 묶고 싶다면 `skill-builder`

### 2. skill-builder — intermediate
- **대상**: CC101을 마치고 반복 업무 자동화를 스킬로 만들고 싶은 학습자
- **목표**: `SKILL.md`, frontmatter, `references/`, Progressive Disclosure, 배포 흐름 이해
- **다음 단계**: 개인 자동화를 팀 운영 구조로 확장하고 싶다면 `context-engineering`

### 3. context-engineering — advanced
- **대상**: 스킬을 직접 만들어봤고 팀 단위 AI 워크플로우를 설계하려는 학습자
- **목표**: 프롬프트·`CLAUDE.md`·Plan 모드의 차이, 에이전트 팀 설계, MCP 연동 이해
- **다음 단계**: 조직 맞춤형 운영 원칙과 도구 연결 전략 문서화

## 로드맵

```text
CC101 → skill-builder → context-engineering
```

추천 흐름은 간단하다.
1. **CC101**에서 Claude Code로 실제 업무 한 사이클을 끝낸다.
2. **skill-builder**에서 반복 업무를 스킬로 고정한다.
3. **context-engineering**에서 팀 전체가 재사용할 수 있는 AI 워크플로우를 설계한다.

## Quick Start

```bash
# 스킬 설치
cp -r skills/lesson ~/.claude/skills/lesson
cp commands/lesson.md ~/.claude/commands/lesson.md

# 강의 시작
/lesson cc101 1-1
/lesson skill-builder 1-1
/lesson context-engineering 1-1
```

## 디렉토리 구조

```text
lesson-skill/
├── .claude-plugin/
│   └── plugin.json
├── commands/
│   └── lesson.md
├── skills/
│   └── lesson/
│       ├── SKILL.md
│       └── references/
├── courses/
│   ├── cc101/
│   ├── skill-builder/
│   └── context-engineering/
├── guides/
└── README.md
```

## 강좌 제작과 운영 가이드

- [새 강좌 만들기](guides/create-your-course.md)
- [난이도 로드맵](guides/difficulty-roadmap.md)
- [강사용 운영 가이드](guides/for-instructors.md)

## 코스 구조 규칙

각 강좌는 아래 구조를 따른다.

```text
courses/{course-id}/
├── CLAUDE.md
├── course-structure.json
└── lessons/
```

`course-structure.json`은 아래 스키마를 사용한다.

```json
{
  "id": "skill-builder",
  "name": "스킬 빌더 — 나만의 Claude Code 스킬 만들기",
  "level": "intermediate",
  "prerequisite": "cc101",
  "modules": [
    {"id": "1", "name": "모듈명", "lessons": ["1-1", "1-2"]}
  ]
}
```

## 감자재배법 원칙

1. **가이드하되 대신하지 않기**
2. **숙련도에 맞춰 설명 깊이 조정하기**
3. **직접 해본 경험을 남기게 만들기**
4. **다음에도 혼자 할 수 있는 자립도를 키우기**

## 권장 모델

Sonnet 4.6, medium effort
