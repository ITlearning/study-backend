# Backend Study Skills

[한국어](#한국어) | [English](#english)

---

## 한국어

Kotlin/Spring 백엔드를 공부할 때 쓸 수 있는 AI CLI 스킬 3개입니다. Claude Code, Codex CLI, Gemini CLI에서 사용할 수 있습니다. 답을 알려주는 대신 질문을 던져서 스스로 생각하게 만들고, 퀴즈로 복습하고, 공부한 내용을 노트로 정리해줍니다.

### 스킬 목록

#### `/backend-study` - 대화형 백엔드 학습

주제를 말하면 핵심 개념을 하나씩 짚어가며 가르칩니다. 답을 바로 알려주는 게 아니라 질문을 던져서 스스로 생각하게 만드는 방식입니다.

- 주제를 직접 입력하거나 학습 이력 기반 추천을 받을 수 있음
- 개념 설명 후 서술형 질문으로 이해도 확인
- 틀리면 힌트를 주고 다시 생각하게 유도
- 맞으면 바로 심화 내용으로 연결

#### `/backend-quiz` - 적응형 퀴즈

5문제짜리 퀴즈를 풀 수 있습니다. 맞추면 난이도가 올라가고, 틀리면 내려갑니다.

- 코드 결과 예측, 에러 찾기, 개념 질문, 코드 작성 등 4가지 유형
- 서술형 중심이라 직접 생각하고 답을 써야 함
- 끝나면 강점/약점 분석과 다음 학습 추천

#### `/backend-summary` - 학습 노트 생성

대화에서 공부한 내용을 마크다운 노트로 정리해줍니다.

- 핵심 개념, 코드 예제, 복습 질문을 포함한 구조화된 노트
- `notes/` 폴더에 날짜별로 자동 저장
- 학습 진도를 메모리에 기록해서 다음 세션에 이어서 공부 가능

### 설치 방법

#### 방법 1: Skills (전체)(권장)

```bash
npx skills add https://github.com/itlearning/study-backend
```

이후 원하는 스킬 스페이스바로 선택, 설치할 수 있습니다.

#### 방법 2: Plugin Marketplace (Claude Code)

```bash
# Claude Code에서 마켓플레이스 추가
/plugin marketplace add itlearning/study-backend

# 플러그인 설치
/plugin install backend-study-skills@study-backend
```

#### 방법 3: 직접 복사

```bash
# 저장소 클론
git clone https://github.com/itlearning/study-backend.git

# 스킬 파일을 프로젝트에 복사
# Claude Code
cp -r study-backend/.agents/skills/backend-study YOUR_PROJECT/.claude/skills/
cp -r study-backend/.agents/skills/backend-quiz YOUR_PROJECT/.claude/skills/
cp -r study-backend/.agents/skills/backend-summary YOUR_PROJECT/.claude/skills/

# Codex CLI
cp -r study-backend/.agents/skills/backend-study YOUR_PROJECT/.agents/skills/
cp -r study-backend/.agents/skills/backend-quiz YOUR_PROJECT/.agents/skills/
cp -r study-backend/.agents/skills/backend-summary YOUR_PROJECT/.agents/skills/

# Gemini CLI
cp -r study-backend/.agents/skills/backend-study YOUR_PROJECT/.gemini/skills/
cp -r study-backend/.agents/skills/backend-quiz YOUR_PROJECT/.gemini/skills/
cp -r study-backend/.agents/skills/backend-summary YOUR_PROJECT/.gemini/skills/
```

### 사용법

AI CLI에서 슬래시 커맨드로 실행하면 됩니다:

```
/backend-study        # 새로운 주제 학습 시작
/backend-quiz         # 퀴즈로 복습
/backend-summary      # 오늘 배운 내용 정리
```

### 학습 흐름

```
/backend-study로 새 주제 학습
        |
        v
/backend-quiz로 복습 퀴즈
        |
        v
/backend-summary로 노트 정리 및 진도 기록
        |
        v
다음 세션에서 이력 기반 추천으로 이어서 학습
```

### 지원 CLI

| CLI | 스킬 위치 | 프로젝트 지침 |
|-----|----------|-------------|
| [Claude Code](https://claude.ai/claude-code) | `.claude/skills/` | `CLAUDE.md` |
| [Codex CLI](https://github.com/openai/codex) | `.agents/skills/` | `AGENTS.md` |
| [Gemini CLI](https://github.com/google-gemini/gemini-cli) | `.gemini/skills/` | `.gemini/GEMINI.md` |

### 요구 사항

- 위 CLI 중 하나 이상

### 라이선스

MIT

---

## English

Three AI CLI skills for studying Kotlin/Spring backend. Works with Claude Code, Codex CLI, and Gemini CLI. They ask questions instead of giving answers, so you actually think through the material. Quiz included, plus a tool that turns your session into notes.

### Skills

#### `/backend-study` - Interactive backend learning

Pick a topic. It teaches one concept at a time, then asks you questions instead of moving on.

- Enter a topic or get recommendations from your study history
- You answer open-ended questions after each explanation
- Wrong? You get a hint and try again
- Right? Straight into deeper material

#### `/backend-quiz` - Adaptive quiz

5 questions. Get one right, difficulty goes up. Get one wrong, it goes down.

- Predict output, find bugs, answer concept questions, or write code
- Mostly open-ended -- you write your own answers
- Results show strengths, weak spots, and what to study next

#### `/backend-summary` - Learning notes

Turns your study conversation into a markdown note.

- Concepts, code examples, and review questions in one file
- Saved to `notes/` by date
- Remembers your progress so you can pick up next time

### Installation

#### Option 1: Skills (all CLIs)(recommended)

```bash
npx skills add https://github.com/itlearning/study-backend
```

Then select the skills you want with spacebar.

#### Option 2: Plugin marketplace (Claude Code)

```bash
# Add the marketplace in Claude Code
/plugin marketplace add itlearning/study-backend

# Install the plugin
/plugin install backend-study-skills@study-backend
```

#### Option 3: Manual copy

```bash
# Clone the repo
git clone https://github.com/itlearning/study-backend.git

# Copy skill files to your project
# Claude Code
cp -r study-backend/.agents/skills/backend-study YOUR_PROJECT/.claude/skills/
cp -r study-backend/.agents/skills/backend-quiz YOUR_PROJECT/.claude/skills/
cp -r study-backend/.agents/skills/backend-summary YOUR_PROJECT/.claude/skills/

# Codex CLI
cp -r study-backend/.agents/skills/backend-study YOUR_PROJECT/.agents/skills/
cp -r study-backend/.agents/skills/backend-quiz YOUR_PROJECT/.agents/skills/
cp -r study-backend/.agents/skills/backend-summary YOUR_PROJECT/.agents/skills/

# Gemini CLI
cp -r study-backend/.agents/skills/backend-study YOUR_PROJECT/.gemini/skills/
cp -r study-backend/.agents/skills/backend-quiz YOUR_PROJECT/.gemini/skills/
cp -r study-backend/.agents/skills/backend-summary YOUR_PROJECT/.gemini/skills/
```

### Usage

Slash commands in your AI CLI:

```
/backend-study        # Start learning a new topic
/backend-quiz         # Review with a quiz
/backend-summary      # Save today's learning notes
```

### Study flow

```
Learn a new topic with /backend-study
        |
        v
Review with /backend-quiz
        |
        v
Save notes with /backend-summary
        |
        v
Next session picks up with history-based recommendations
```

### Supported CLIs

| CLI | Skills location | Project instructions |
|-----|----------------|---------------------|
| [Claude Code](https://claude.ai/claude-code) | `.claude/skills/` | `CLAUDE.md` |
| [Codex CLI](https://github.com/openai/codex) | `.agents/skills/` | `AGENTS.md` |
| [Gemini CLI](https://github.com/google-gemini/gemini-cli) | `.gemini/skills/` | `.gemini/GEMINI.md` |

### Requirements

- One or more of the CLIs above

### License

MIT
