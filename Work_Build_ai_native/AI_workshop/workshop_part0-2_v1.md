# 🎨 Vibe Coding 워크샵 - 디자이너를 위한 A to Z 완벽 가이드

**대상:** 코딩 경험이 전무한 디자인팀
**기간:** 8시간 (연속 또는 2일)
**목표:** "Claude와 대화하며 디자인 도구를 직접 만들 수 있는 디자이너가 되기"

---

## Part 0: 시작하기 전에 (20분)

### 0.1 "Vibe Coding"이란?

**전통적 프로그래밍**
```
디자이너: "애, 개발자님. 이런 기능이 필요해요"
개발자: "알겠습니다. 3주 후에 완성될 것 같습니다"
(3주 기다림)
→ 보통 원했던 것과 다름
```

**Vibe Coding**
```
당신: 내가 원하는 기능을 Claude에게 설명
Claude: "좋아요. 이렇게 할까요?" → 코드 제시
당신: "잠깐, 색상을 이렇게 바꿔줄래?" → 수정 요청
Claude: "오케이!" → 즉시 수정
(결과물 즉시 확인 가능)
→ 정확히 내가 원하는 것이 됨
```

**핵심: "AI와 대화하듯이 프로그래밍한다"**

---

### 0.2 오늘 8시간 동안 배울 것

| 시간 | 내용 | 결과물 |
|------|------|--------|
| **Part 0** (20분) | 개념 & 마인드셋 | 준비 완료 |
| **Part 1** (1시간) | 도구 설치 & 첫 코드 | 로컬에서 웹사이트 실행 |
| **Part 2** (1시간) | 핵심 개념 이해 | "왜 이렇게 하는가?"를 알게 됨 |
| **Part 3** (1.5시간) | AI 도구 활용법 | Claude 능력을 최대한 활용 |
| **Part 4** (4시간) | 실제 프로젝트 만들기 | 배포한 웹사이트 완성 |
| **Part 5** (30분) | 에러 해결 & 다음 스텝 | 앞으로 혼자 할 수 있는 자신감 |

---

### 0.3 필요한 준비물

#### 온라인 계정 (3개)

1. **GitHub** (https://github.com)
   - 코드를 온라인에 저장하는 곳
   - Google Drive처럼 생각하면 됨
   - 무료

2. **Anthropic Console** (https://console.anthropic.com)
   - Claude API 키를 받는 곳
   - 신용카드 필요 (월 $5 정도면 충분)

3. **Vercel** (https://vercel.com)
   - 웹사이트를 인터넷에 배포하는 서비스
   - GitHub 계정으로 가입 가능

#### 컴퓨터에 설치할 것

- Cursor (AI가 있는 코드 에디터)
- Claude Code CLI (터미널에서 Claude 사용)
- Git (코드 버전 관리)
- Node.js (JavaScript 실행 환경)

#### 장비
- Mac 또는 Windows 컴퓨터
- 웹 브라우저
- 인터넷 연결

---

### 0.4 꼭 알아두면 좋은 마인드셋 5가지

#### 1️⃣ "에러는 정상이다"
프로그래밍은 에러 해결의 연속입니다.
- 에러가 나도 당황하지 말기
- 에러 메시지를 Claude에게 보여주기
- Claude가 해결책을 제시해줌

#### 2️⃣ "한 번에 완벽할 필요는 없다"
오늘 만든 것이 못생겨도, 느려도 괜찮습니다.
대신 "이건 수정할 수 있다"는 것을 배우는 게 목표입니다.

#### 3️⃣ "Claude는 당신의 팀원이다"
- 모르는 걸 물어보기
- "왜 이렇게 하나?" 물어보기
- "더 나은 방법이 있을까?" 물어보기
- Claude는 항상 친절합니다

#### 4️⃣ "작은 것부터 시작하기"
Instagram 같은 거대한 앱을 만들지 않습니다.
대신:
- 색상 추천 도구
- 폰트 크기 조절기
- 이미지 분석 도구

작은 것들이 모여 큰 것이 됩니다.

#### 5️⃣ "이건 "디자인 스킬"이다"
프로그래밍을 배우는 게 아닙니다.
**AI를 이용한 프로토타이핑 도구를 배우는 것입니다.**
- Figma처럼 빠르게
- 원하는 대로 수정 가능
- 쉽게 배포 가능

**"나는 개발자가 아니다. 디자이너이고, AI 도구를 쓸 줄 아는 디자이너이다."**

---

### 0.5 오늘 끝나면 할 수 있는 것들

✅ **프로토타입 도구**
- 컬러 팔레트 생성기
- 타이포그래피 테스터
- 반응형 레이아웃 시뮬레이터

✅ **AI 통합 도구**
- 이미지 분석 도구
- 텍스트 기반 추천 시스템
- 채팅 인터페이스

✅ **팀 내부 도구**
- 디자인 메타데이터 추출기
- 컬러 코드 변환기
- 텍스트 스타일 생성기

✅ **개인 프로젝트**
- 포트폴리오 웹사이트
- 개인 도구 (분석, 계산 등)
- 작은 SaaS 프로토타입

---

### 0.6 자주 묻는 질문 (FAQ)

**Q. 개발자가 되어야 하나요?**
A. 아니요. "Claude에게 잘 요청하는 법"만 배우면 됩니다.

**Q. 영어를 잘 해야 하나요?**
A. 이 워크샵은 한글입니다. 필요한 영어는 복붙만 하면 됩니다.

**Q. Mac과 Windows는 다른가요?**
A. 약간의 차이가 있지만 가능합니다. Part 1에서 설명하겠습니다.

**Q. 어려우면 어떻게 하나요?**
A. Claude에게 물어보세요. 물어보면서 배우는 게 정상입니다.

**Q. 직무가 바뀌나요?**
A. 아니요. 디자이너 역할은 그대로입니다. 단, 개발팀 없이도 프로토타입을 만들 수 있게 됩니다.

**Q. 나중에도 쓸 수 있나요?**
A. 네. 평생 써먹을 수 있습니다. 가장 중요한 건 꾸준함입니다.

---

## Part 1: 환경 세팅 A to Z (1시간)

### 1.1 Cursor 설치하기

Cursor는 "Claude가 내장된 코드 에디터"입니다.

#### Step 1: 다운로드
1. https://www.cursor.sh 접속
2. "Download" 버튼 클릭
3. Mac 또는 Windows 선택
4. 다운로드 완료까지 기다리기

#### Step 2: 설치

**Mac 사용자:**
- 다운로드된 `Cursor.dmg` 파일 더블클릭
- Cursor 아이콘을 Applications 폴더로 드래그

**Windows 사용자:**
- 다운로드된 파일 더블클릭
- "다음" 계속 클릭
- 설치 완료

#### Step 3: 실행
- Applications/Cursor 더블클릭

#### Step 4: Claude 연결
```
메뉴 → Settings → Features → Claude API
```

1. "Enable Claude API" 토글 켜기
2. API 키 필요:
   - https://console.anthropic.com/api/keys 접속
   - "Create Key" 클릭
   - 생성된 키 복사해서 Cursor에 붙여넣기

---

### 1.2 Claude Code CLI 설치하기

Claude Code CLI는 "터미널에서 Claude와 대화하는 방법"입니다.

#### Step 1: 터미널 열기

**Mac:**
- Spotlight (Command + Space)
- "Terminal" 검색 & 열기

**Windows:**
- Windows 검색 (Windows + S)
- "PowerShell" 또는 "Command Prompt" 검색

#### Step 2: 설치 명령어 복사-붙여넣기

**Mac/Linux:**
```bash
curl -fsSL https://claude.sh/install.sh | bash
```

**Windows PowerShell:**
```powershell
irm https://claude.sh/install.ps1 | iex
```

#### Step 3: 설치 확인
```bash
claude --version
```

버전이 나타나면 완료!

---

### 1.3 Git 설치하기

Git은 "코드의 타임머신"입니다.

#### Step 1: 설치

**Mac:**
```bash
xcode-select --install
```

**Windows:**
- https://git-scm.com/download/win 접속
- 설치 파일 다운로드 & 실행
- "Next" 계속 클릭

#### Step 2: 확인
```bash
git --version
```

---

### 1.4 GitHub 계정 설정

#### Step 1: 계정 가입
- https://github.com/signup
- 이메일, 비밀번호, 사용자명 입력
- "Create account" 클릭

#### Step 2: Git 설정
터미널에 입력 (본인 정보로 수정):
```bash
git config --global user.name "Your Name"
git config --global user.email "your.email@example.com"
```

---

### 1.5 Node.js 설치하기

Node.js는 "JavaScript를 컴퓨터에서 실행하는 프로그램"입니다.

#### Step 1: 다운로드
- https://nodejs.org 접속
- "LTS" 버전 다운로드

#### Step 2: 설치
- 파일 더블클릭
- "다음" 계속 클릭
- 설치 완료

#### Step 3: 확인
새 터미널 창에서:
```bash
node --version
npm --version
```

둘 다 버전이 나타나면 완료!

---

### 1.6 첫 번째 프로젝트 만들기

#### Step 1: 작업 폴더 만들기
```bash
mkdir -p ~/Desktop/vibe-coding-workshop
cd ~/Desktop/vibe-coding-workshop
```

#### Step 2: React 프로젝트 생성
```bash
npm create vite@latest my-first-project -- --template react
```

TypeScript 물어볼 때: "No" 입력

#### Step 3: 프로젝트 폴더로 이동
```bash
cd my-first-project
```

#### Step 4: 패키지 설치
```bash
npm install
```

#### Step 5: 개발 서버 실행
```bash
npm run dev
```

터미널에 이렇게 보여야 함:
```
➜ Local: http://localhost:5173/
```

#### Step 6: 브라우저에서 확인
1. Chrome/Safari 열기
2. 주소창에 `http://localhost:5173` 입력
3. "Vite + React" 페이지가 보이면 성공!

---

### 1.7 첫 코드 수정해보기

#### Step 1: Cursor에서 프로젝트 열기
1. Cursor 열기
2. File → Open Folder
3. `~/Desktop/vibe-coding-workshop/my-first-project` 선택

#### Step 2: App.jsx 파일 열기
왼쪽 파일 목록 → src → App.jsx

#### Step 3: Claude에게 도움 요청하기
Cursor에서 `Cmd+K` (또는 `Ctrl+K` Windows) 눌러서 Claude 입력창 열기

입력:
```
"count" 대신에 "Hello, My Name is [당신의 이름]"으로 표시해줄래?
```

Claude가 수정안을 제시합니다. "Accept" 클릭.

#### Step 4: 브라우저에서 확인
브라우저 새로고침 (Cmd+R 또는 Ctrl+R)

텍스트가 바뀌었으면 성공! 🎉

---

### 1.8 Git에 저장하기

#### Step 1: 프로젝트 폴더로 이동
```bash
cd ~/Desktop/vibe-coding-workshop/my-first-project
```

#### Step 2: 현재 상태 확인
```bash
git status
```

#### Step 3: 모든 파일 추가
```bash
git add .
```

#### Step 4: 저장
```bash
git commit -m "Initial commit: My first project setup"
```

#### Step 5: GitHub에 업로드
1. https://github.com/new 접속
2. Repository name 입력 (예: `my-first-vibe-coding-project`)
3. "Create repository" 클릭
4. "또는 명령줄에서 기존 저장소를 푸시합니다" 섹션의 명령어 복사
5. 터미널에 붙여넣고 실행

완료! 코드가 GitHub에 저장되었습니다.

---

## Part 2: 핵심 개념 이해 (1시간)

### 2.1 Vibe Coding의 작동 원리

Claude가 코드를 이해하는 방식을 알면, 더 잘 요청할 수 있습니다.

#### Prompt와 Response

```
당신: "색상을 빨강으로 바꿔줄래?" ← Prompt (요청)
     ↓
Claude: [색상 코드 수정] ← Response (응답)
```

#### Context Window

Claude는 한 번에 제한된 양의 코드만 볼 수 있습니다.

**좋은 예:**
```
당신: "App.jsx에서 버튼의 배경색을 파란색으로 바꿔줄래?"
Claude: 🎯 정확하게 수정 (파일명 + 부분 명시)
```

**나쁜 예:**
```
당신: "색상을 바꿔줄래?"
Claude: ❓ 어느 파일? 어느 요소? (정보 부족)
```

---

### 2.2 Iteration (반복 수정)

Vibe Coding의 가장 큰 장점입니다.

```
당신: "버튼을 만들어줄래?"
Claude: "이렇게 할까요?" → 코드 제시

당신: "색상을 이렇게 바꿔줄래?"
Claude: "오케이!" → 수정

당신: "이제 더 크게 해줄래?"
Claude: "된다!" → 또 수정

(계속...)
```

**핵심:** 한 번에 완벽할 필요가 없습니다!

---

### 2.3 프론트엔드 기본 3요소

웹사이트는 3가지로 이루어집니다.

#### 1️⃣ HTML (뼈대)
웹사이트의 **구조**를 만듭니다.

```html
<button>클릭하세요</button>
<input type="text" placeholder="이름 입력" />
<div>내용이 여기 들어갑니다</div>
```

#### 2️⃣ CSS (인테리어)
웹사이트를 **예쁘게** 만듭니다.

```css
button {
  background-color: blue;      /* 배경색 */
  color: white;                /* 글씨색 */
  padding: 10px 20px;         /* 안쪽 여백 */
  border-radius: 5px;         /* 모서리 둥글게 */
}
```

#### 3️⃣ JavaScript (전기)
웹사이트가 **실제로 작동**하게 합니다.

```javascript
button.addEventListener('click', () => {
  alert('버튼이 눌렸습니다!');
});
```

---

### 2.4 React란? (컴포넌트 철학)

React는 "웹사이트를 작은 블록들로 만들게 해주는 라이브러리"입니다.

#### 컴포넌트 = 재사용 가능한 블록

레고처럼:
```
큰 건축물 = 작은 레고 블록들의 조합

┌─────────────────────┐
│  App (전체 페이지)   │
│  ┌────────┐┌─────┐  │
│  │ Button││ Card│  │
│  └────────┘└─────┘  │
└─────────────────────┘
```

#### 예시: Button 컴포넌트

```jsx
function MyButton() {
  return <button>클릭하세요</button>;
}

// 다른 곳에서 재사용
<MyButton />
<MyButton />
<MyButton />
// 3개의 버튼이 자동으로 만들어짐
```

---

### 2.5 State (상태 변화)

State는 "시간에 따라 변하는 데이터"입니다.

**예: 좋아요 버튼**

```jsx
function LikeButton() {
  const [liked, setLiked] = useState(false);

  return (
    <button onClick={() => setLiked(!liked)}>
      {liked ? '❤️ 좋아요' : '🤍 좋아요'}
    </button>
  );
}
```

- 처음: `liked = false` → "🤍 좋아요" 표시
- 클릭: `setLiked(true)` → "❤️ 좋아요"로 변경
- 다시 클릭: `setLiked(false)` → "🤍 좋아요"로 돌아옴

---

### 2.6 Tailwind CSS (스타일링 쉽게 하기)

Tailwind CSS는 "CSS를 쓰는 대신 클래스명을 쓰는 방식"입니다.

#### 전통적인 CSS (복잡함)

```css
.button {
  background-color: #3b82f6;
  color: white;
  padding: 10px 20px;
  border-radius: 5px;
}
```

#### Tailwind CSS (간단함)

```jsx
<button className="bg-blue-500 text-white px-5 py-2 rounded">
  클릭하세요
</button>
```

- `bg-blue-500` = 배경색 파란색
- `text-white` = 글씨색 하얀색
- `px-5 py-2` = 좌우 5, 상하 2 여백
- `rounded` = 모서리 둥글게

**장점:** CSS 파일을 안 만들어도 됩니다!

---

### 2.7 TypeScript vs JavaScript

둘의 차이는 "타입 체크"입니다.

#### JavaScript (자유로움)

```javascript
let age = 25;
age = "스물다섯";  // 가능 (숫자에서 글씨로 바뀜)
```

#### TypeScript (엄격함)

```typescript
let age: number = 25;
age = "스물다섯";  // 에러! (숫자여야 함)
```

**언제 어떤 걸 쓸까?**
- **JavaScript:** 간단한 프로젝트, 빠르게 만들고 싶을 때
- **TypeScript:** 큰 프로젝트, 에러를 미리 잡고 싶을 때

"오늘은 JavaScript로 시작합니다."

---

### 2.8 API란? (외부 데이터 가져오기)

API는 "다른 서비스의 기능을 빌려쓰는 방법"입니다.

**예: Claude API로 텍스트 생성하기**

```javascript
const response = await fetch('https://api.anthropic.com/...', {
  method: 'POST',
  headers: { 'Authorization': `Bearer ${API_KEY}` },
  body: JSON.stringify({
    model: 'claude-3-5-sonnet-20241022',
    messages: [{ role: 'user', content: '안녕?' }]
  })
});

const data = await response.json();
console.log(data.content[0].text);  // Claude의 응답 출력
```

간단히 말해:
```
당신 → "Claude야, 뭐 해?"
Claude API → "안녕! 뭘 도와줄까?"
당신이 받은 응답 → "안녕! 뭘 도와줄까?"
```

---

### 2.9 환경변수 (.env 파일)

API 키 같은 민감한 정보는 **절대 코드에 직접 써면 안 됩니다.**

#### 나쁜 예 (위험함!)

```javascript
const apiKey = "sk-ant-xxxxx";  // ❌ GitHub에 노출될 위험
```

#### 좋은 예 (안전함)

`.env.local` 파일:
```
REACT_APP_ANTHROPIC_API_KEY=sk-ant-xxxxx
```

코드에서:
```javascript
const apiKey = process.env.REACT_APP_ANTHROPIC_API_KEY;
```

**중요:** `.env.local` 파일은 GitHub에 올라가지 않습니다. (`.gitignore`에 설정됨)

---

### 2.10 필수 터미널 명령어

외우지 말고 참고용입니다!

| 명령어 | 역할 | 예시 |
|--------|------|------|
| `cd [폴더명]` | 폴더 이동 | `cd my-project` |
| `ls` (Mac) 또는 `dir` (Windows) | 파일 목록 보기 | - |
| `npm install` | 패키지 설치 | - |
| `npm run dev` | 개발 서버 실행 | - |
| `git add .` | 파일 준비 | - |
| `git commit -m "메시지"` | 버전 저장 | - |
| `git push` | GitHub에 업로드 | - |
| `clear` (또는 `cls` Windows) | 터미널 깨끗하게 | - |

---

### 2.11 에러 읽는 법 (절대 당황 금지)

프로그래밍의 50%는 에러를 읽고 해결하는 것입니다.

#### 에러 메시지의 구조

```
❌ Error: Cannot find module 'react'
   at Function.Module._resolveFilename ...
   at /Users/name/project/src/App.jsx:1:28
```

- **Error:** 뭐가 문제인가? → "Cannot find module 'react'" (react를 찾을 수 없음)
- **Location:** 어디서 문제인가? → "App.jsx:1:28" (App.jsx 파일의 1번째 줄 28번째 글자)
- **Trace:** 어떻게 연쇄적으로 발생했나? → (기술적 세부사항)

#### 에러 해결 3단계
1. **에러 메시지를 Claude에게 복사-붙여넣기**
2. **"이 에러를 어떻게 해결할까?"라고 물어보기**
3. **Claude의 제안을 따르기**

---

### 2.12 Debugging 기초

에러 없이도, 코드가 "예상과 다르게 작동"할 수 있습니다.

#### Console.log로 확인하기

```javascript
const name = "John";
console.log("현재 name의 값:", name);  // 터미널에 출력됨
```

#### 브라우저의 개발자 도구 (F12)

1. 웹사이트에서 F12 누르기 (또는 우클릭 → 검사)
2. "Console" 탭으로 이동
3. console.log 결과가 여기에 표시됨

---

**Part 3 이상은 다음 파일에서 계속됩니다.**
