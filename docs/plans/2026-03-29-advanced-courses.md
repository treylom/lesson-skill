# Advanced Course Materials Implementation Plan

> **For Claude:** REQUIRED SUB-SKILL: Use superpowers:executing-plans to implement this plan task-by-task.

**Goal:** Add intermediate and advanced courses plus shared guides so `lesson-skill` supports a clear CC101 → skill-builder → context-engineering learning path.

**Architecture:** Keep each course self-contained with a course-level `CLAUDE.md`, a minimal `course-structure.json`, and lesson markdown files under `lessons/`. Add reusable instructor/student guidance under `guides/`, then rewrite the root `README.md` so the three-course roadmap is discoverable from the repo entry point.

**Tech Stack:** Markdown, JSON, Claude Code skill/plugin conventions

---

### Task 1: Course directory scaffolding

**Files:**
- Create: `courses/skill-builder/CLAUDE.md`
- Create: `courses/skill-builder/course-structure.json`
- Create: `courses/skill-builder/lessons/`
- Create: `courses/context-engineering/CLAUDE.md`
- Create: `courses/context-engineering/course-structure.json`
- Create: `courses/context-engineering/lessons/`
- Create: `guides/`

**Step 1: Create the directories**

Run: `mkdir -p courses/skill-builder/lessons courses/context-engineering/lessons guides docs/plans`
Expected: directories exist with no errors

**Step 2: Add minimal course metadata**

Write `CLAUDE.md` and `course-structure.json` for each course using the approved schema:

```json
{
  "id": "skill-builder",
  "name": "스킬 빌더 — 나만의 Claude Code 스킬 만들기",
  "level": "intermediate",
  "prerequisite": "cc101",
  "modules": [
    {"id": "1", "name": "스킬 설계와 구조", "lessons": ["1-1", "1-2", "1-3"]},
    {"id": "2", "name": "배포와 공유", "lessons": ["2-1"]}
  ]
}
```

**Step 3: Verify metadata**

Run: `Read courses/skill-builder/course-structure.json` and `Read courses/context-engineering/course-structure.json`
Expected: ids, levels, prerequisites, and lesson arrays match the approved design

### Task 2: Intermediate course content

**Files:**
- Modify/Create: `courses/skill-builder/CLAUDE.md`
- Create: `courses/skill-builder/lessons/1-1-skill-anatomy.md`
- Create: `courses/skill-builder/lessons/1-2-first-skill.md`
- Create: `courses/skill-builder/lessons/1-3-references.md`
- Create: `courses/skill-builder/lessons/2-1-publishing.md`

**Step 1: Write the course scenario**

Document that CC101을 마친 김신입이 업무 자동화 스킬을 설계하고 배포하는 단계임을 명시한다.

**Step 2: Write four lesson documents**

Each lesson must include:
- lesson title and continuation from CC101
- 학습 목표
- 핵심 개념 or 실습 흐름
- 체크리스트 or 산출물
- 다음 단계 연결

**Step 3: Verify continuity**

Run: `Read courses/skill-builder/CLAUDE.md` and one sample lesson
Expected: CC101 완료자 관점, 한국어 설명, 영문 코드/명령어만 사용

### Task 3: Advanced course content

**Files:**
- Modify/Create: `courses/context-engineering/CLAUDE.md`
- Create: `courses/context-engineering/lessons/1-1-three-layers.md`
- Create: `courses/context-engineering/lessons/1-2-agent-teams.md`
- Create: `courses/context-engineering/lessons/1-3-mcp.md`

**Step 1: Write the advanced scenario**

Document that skill-builder를 마친 김신입이 팀 단위 AI 워크플로우를 설계하는 단계임을 명시한다.

**Step 2: Write three lesson documents**

Cover:
- prompt → `CLAUDE.md` → Plan mode layer experiment
- `/tofu-at`, Split Pane, parallel agent teamwork
- MCP concept and Obsidian/Notion/Slack integration

**Step 3: Verify scope**

Run: `Read courses/context-engineering/course-structure.json` and one sample lesson
Expected: advanced framing, no confusion with lesson-sungwoo, continuity from skill-builder

### Task 4: Shared guides

**Files:**
- Create: `guides/create-your-course.md`
- Create: `guides/difficulty-roadmap.md`
- Create: `guides/for-instructors.md`

**Step 1: Write authoring guide**

Explain `courses/` layout, `CLAUDE.md` writing principles, and provide a lesson template.

**Step 2: Write roadmap guide**

Explain beginner → intermediate → advanced progression and self-diagnosis questions.

**Step 3: Write instructor guide**

Explain `/lesson` usage, student profile handling, and 감자재배법 teaching principles.

### Task 5: README rewrite and verification

**Files:**
- Modify: `README.md`

**Step 1: Rewrite the README in Korean**

Include:
- project introduction
- three-course list with difficulty
- recommended roadmap
- Quick Start
- guide links

**Step 2: Verify file set**

Run: `Glob courses/**/* guides/* docs/plans/*`
Expected: all requested course files, guide files, and plan file exist

**Step 3: Final review**

Run: `Read README.md`
Expected: Korean rewrite reflects the new three-course structure and links to the guides
