# Vibe Coding 워크샵 Part 3-5 (계속)

## Part 3: AI 도구 & 통합 (1.5시간)

### 3.1 Cursor Rules 작성하기

`.cursorrules` 파일은 "Claude에게 이 프로젝트에서 어떻게 행동할지 알려주는 설정"입니다.

#### Step 1: .cursorrules 파일 생성

Cursor에서:
1. `File` → `New File`
2. 파일명: `.cursorrules` (점으로 시작)
3. 다음 내용을 복사-붙여넣기

---

#### 템플릿 A: 디자인 시스템 중심 프로젝트

```
당신은 React + Tailwind CSS 전문가입니다.

## 규칙
- 모든 스타일은 Tailwind CSS 클래스로만 작성
- Shadcn UI 컴포넌트를 우선 사용
- 모든 색상은 디자인 시스템 변수 사용 (예: bg-primary-500)
- 반응형 디자인 필수 (모바일, 태블릿, 데스크톱)
- 다크모드 지원

## 컴포넌트 구조
- 모든 컴포넌트는 src/components 폴더에
- 파일명은 PascalCase (예: MyButton.jsx)
- 각 컴포넌트는 props로 설정 가능하게

## 성능
- 이미지는 최적화 필수
- 불필요한 렌더링 피할 것

## 코드 스타일
- 명확한 변수명 사용
- 한국어 주석 가능
- 에러 처리 명확히
```

---

#### 템플릿 B: AI 통합 프로젝트

```
당신은 Claude API를 전문으로 다루는 개발자입니다.

## API 사용
- Anthropic API 키는 .env.local에만 저장
- API 키는 절대 하드코딩 금지
- API 호출 시 에러 처리 필수
- 토큰 사용량 고려 (비용 관리)

## 환경변수 관리
- REACT_APP_ANTHROPIC_API_KEY=your_key_here
- .env.local은 .gitignore에 추가됨
- Vercel 배포 시 환경변수 설정 필수

## 사용자 경험
- API 호출 중 로딩 상태 표시
- 에러 메시지는 사용자 친화적으로
- 응답 시간을 표시

## 보안
- 클라이언트에서만 API 호출 (또는 서버 라우트 사용)
- Rate limiting 고려
```

---

#### 템플릿 C: 프로토타입 빠른 제작용

```
당신은 빠른 프로토타입 제작 전문가입니다.

## 속도 우선
- 완벽하기보다 빠르게
- 라이브러리는 간단한 것 우선
- 복잡한 최적화는 나중에

## 디자이너 친화
- 모든 설정은 한 곳에서 (config.js)
- 색상, 폰트, 간격은 변수로 관리
- UI 요소는 쉽게 추가/제거 가능

## 코드 양이 많아야 좋은 건 아니다
- 짧고 이해하기 쉬운 코드 우선
```

---

### 3.2 Shadcn UI로 고품질 컴포넌트 사용하기

Shadcn UI는 "복붙 가능한 고품질 컴포넌트 라이브러리"입니다.

#### Step 1: Shadcn UI 초기화

```bash
npx shadcn-ui@latest init
```

질문이 나오면:
- "Which style would you like to use?" → `Default`
- "Which color would you like as the base color?" → `Blue`
- 나머지는 엔터로 기본값 선택

#### Step 2: 컴포넌트 추가하기

버튼을 예로:

```bash
npx shadcn-ui@latest add button
```

그럼 `src/components/ui/button.jsx` 파일이 자동 생성됨.

#### Step 3: 컴포넌트 사용하기

```jsx
import { Button } from "@/components/ui/button"

export default function App() {
  return (
    <div>
      <Button>클릭하세요</Button>
      <Button variant="outline">테두리만</Button>
      <Button disabled>비활성</Button>
    </div>
  )
}
```

#### 자주 쓰는 Shadcn 컴포넌트

- **Button** - 버튼
- **Card** - 카드 박스
- **Input** - 입력 창
- **Select** - 드롭다운
- **Dialog** - 팝업
- **Slider** - 슬라이더
- **Tabs** - 탭 네비게이션
- **Badge** - 라벨

#### Step 4: 컴포넌트 추가하기 (예: Slider)

```bash
npx shadcn-ui@latest add slider
```

그 다음 코드에서 사용:

```jsx
import { Slider } from "@/components/ui/slider"

export default function App() {
  const [value, setValue] = useState(50);

  return (
    <div>
      <Slider value={[value]} onValueChange={(v) => setValue(v[0])} />
      <p>현재 값: {value}</p>
    </div>
  )
}
```

---

### 3.3 환경변수 관리 (.env)

API 키와 같은 민감한 정보는 **절대 코드에 직접 쓰면 안 됩니다.**

#### Step 1: .env.local 파일 생성

프로젝트 루트에 `.env.local` 파일 생성:

```
REACT_APP_ANTHROPIC_API_KEY=sk-ant-xxxxxxxxxxxxxxx
```

#### Step 2: .gitignore에 추가 (이미 되어 있음)

GitHub에 올릴 때 이 파일이 제외되도록:

```
# .gitignore 파일 (보통 이미 설정됨)
.env.local
.env
```

#### Step 3: 코드에서 사용하기

```javascript
const apiKey = process.env.REACT_APP_ANTHROPIC_API_KEY;

const response = await fetch('https://api.anthropic.com/v1/messages', {
  method: 'POST',
  headers: {
    'Authorization': `Bearer ${apiKey}`,
    'Content-Type': 'application/json'
  },
  body: JSON.stringify({...})
});
```

#### Step 4: Vercel 배포 시 환경변수 설정

Vercel 대시보드에서:
1. 프로젝트 선택
2. Settings → Environment Variables
3. `REACT_APP_ANTHROPIC_API_KEY` 추가
4. 값 입력 (GitHub에는 안 올라감)

---

### 3.4 Vercel로 배포하기

"내 컴퓨터에서만 보이는" 웹사이트를 "인터넷에 올려서 누구나 볼 수 있게" 하기.

#### Step 1: Vercel 계정 가입 및 GitHub 연동
- https://vercel.com 접속
- "Sign Up" 클릭
- GitHub 계정으로 가입

#### Step 2: 저장소를 Vercel에 연결
1. Vercel 대시보드에서 "Add New..." → "Project"
2. GitHub 저장소 선택
3. "Import" 클릭

#### Step 3: 환경변수 설정
1. "Environment Variables" 섹션
2. `REACT_APP_ANTHROPIC_API_KEY` 추가
3. 값 입력

#### Step 4: 배포
1. "Deploy" 버튼 클릭
2. 1-2분 기다리면 배포 완료
3. "Visit" 링크로 웹사이트 확인

#### 이후 자동 배포
- GitHub에 코드를 `push`하면
- 자동으로 Vercel에 배포됨
- 누구나 인터넷으로 접근 가능

---

## Part 4: 실습 프로젝트 (4시간)

### 프로젝트 선택 가이드

| 프로젝트 | 난이도 | 학습 내용 | 추천 |
|---------|--------|---------|------|
| **A. 컬러 팔레트 생성기** | ⭐⭐ | Claude API, 환경변수 | 처음 배우는 사람 |
| **B. 타이포그래피 테스터** | ⭐ | Shadcn, State 관리, JSON | 가장 간단함 |
| **C. AI 이미지 피드백** | ⭐⭐⭐ | Vision API, 이미지 처리 | 도전하고 싶은 사람 |

**추천 순서:** B → A → C

---

### 프로젝트 A: AI 컬러 팔레트 생성기

사용자가 **"여름 해변"** 같은 키워드를 입력하면, Claude가 어울리는 5가지 색상을 추천합니다.

#### 단계 1: 프로젝트 생성
```bash
cd ~/Desktop
npx create-vite@latest color-palette-generator -- --template react
cd color-palette-generator
npm install
```

#### 단계 2: Shadcn UI 초기화
```bash
npx shadcn-ui@latest init
npx shadcn-ui@latest add button
npx shadcn-ui@latest add input
npx shadcn-ui@latest add card
```

#### 단계 3: .env.local 파일 생성
프로젝트 루트에:
```
REACT_APP_ANTHROPIC_API_KEY=sk-ant-your-api-key-here
```

#### 단계 4: App.jsx 작성
Cursor에서 `Cmd+K`를 눌러 Claude에게:

```
컬러 팔레트 생성기를 만들어줄래?
기능:
1. 텍스트 입력창 (사용자가 "여름 해변" 같은 키워드 입력)
2. "생성" 버튼
3. Claude API로 5가지 색상 추천받기
4. 각 색상을 박스로 표시 (클릭하면 코드 복사)

사용한 라이브러리: React, Shadcn UI, Tailwind CSS
```

Claude가 전체 코드를 제시할 것입니다.

#### 단계 5: 로컬 테스트
```bash
npm run dev
```

#### 단계 6: 수정 및 개선
- "색상 박스를 더 크게 해줄래?"
- "클릭할 때 알림이 나오게 해줄래?"
- "로딩 중 메시지를 보여줄래?"

#### 단계 7: GitHub에 저장
```bash
git add .
git commit -m "feat: Add color palette generator"
git push
```

#### 단계 8: Vercel 배포
1. https://vercel.com 접속
2. GitHub 저장소 선택
3. 환경변수 설정
4. 배포 완료

---

### 프로젝트 B: 인터랙티브 타이포그래피 테스터

슬라이더로 **폰트 크기, 행간, 자간을 조절**하고 실시간으로 텍스트를 확인합니다.

#### 단계 1: 프로젝트 생성
```bash
npx create-vite@latest typography-tester -- --template react
cd typography-tester
npm install
```

#### 단계 2: Shadcn UI 설정
```bash
npx shadcn-ui@latest init
npx shadcn-ui@latest add slider
npx shadcn-ui@latest add card
```

#### 단계 3: App.jsx 작성
Cursor에서:

```
타이포그래피 테스터를 만들어줄래?

기능:
1. 3개의 슬라이더:
   - 폰트 크기 (12px ~ 72px)
   - 행간 (1 ~ 2.5)
   - 자간 (-0.5px ~ 2px)
2. 실시간 프리뷰 텍스트:
   "디자이너를 위한 Vibe Coding 워크샵입니다"
3. 현재 CSS 값 표시
4. "JSON으로 다운로드" 버튼 (개발자에게 전달용)

CSS 예시:
{
  "fontSize": "32px",
  "lineHeight": "1.5",
  "letterSpacing": "0px"
}
```

#### 단계 4: 로컬 테스트
```bash
npm run dev
```

슬라이더를 움직이면 텍스트 크기가 실시간으로 변해야 합니다.

#### 단계 5: 개선
- "다크모드를 지원해줄래?"
- "더 예쁜 레이아웃으로 디자인해줄래?"
- "폰트 종류도 선택할 수 있게 해줄래?"

#### 단계 6-8: GitHub 저장 및 Vercel 배포
(프로젝트 A와 동일)

---

### 프로젝트 C: AI 디자인 피드백 챗봇 (고급)

디자인 스크린샷을 업로드하면, **Claude Vision이 분석**해서 피드백을 주고, 계속 질문할 수 있습니다.

#### 단계 1: 프로젝트 생성
```bash
npx create-vite@latest design-feedback-bot -- --template react
cd design-feedback-bot
npm install
```

#### 단계 2: Shadcn UI 설정
```bash
npx shadcn-ui@latest init
npx shadcn-ui@latest add button
npx shadcn-ui@latest add input
npx shadcn-ui@latest add card
```

#### 단계 3: .env.local 생성
```
REACT_APP_ANTHROPIC_API_KEY=sk-ant-your-api-key
```

#### 단계 4: App.jsx 작성
Cursor에서:

```
AI 디자인 피드백 챗봇을 만들어줄래?

기능:
1. 이미지 업로드 (drag & drop 또는 클릭)
2. 업로드된 이미지 표시
3. Claude Vision API로 이미지 분석
4. 초기 피드백 표시 (UX, 색상, 타이포그래피 등)
5. 채팅 인터페이스:
   - 사용자가 더 물어볼 수 있음
   - "버튼 배치를 어떻게 개선할까?"
   - "색상 조화가 좋은가?"
6. 대화 히스토리 유지

라이브러리: React, Anthropic API, Tailwind CSS
```

#### 단계 5: 로컬 테스트
```bash
npm run dev
```

이미지를 업로드하고 "분석" 버튼 클릭하면 피드백이 나와야 합니다.

#### 단계 6: 개선
- "로딩 중 애니메이션을 보여줄래?"
- "이전 대화도 저장되게 해줄래?"
- "내보내기 기능을 추가해줄래?"

#### 단계 7-8: GitHub 저장 및 Vercel 배포
(프로젝트 A와 동일)

---

## Part 5: 트러블슈팅 & 다음 스텝 (30분)

### 5.1 자주 만나는 에러들

#### 에러 1: "Cannot find module"
```
❌ Error: Cannot find module 'react'
```

**원인:** 패키지가 설치되지 않음
**해결:**
```bash
npm install
```

---

#### 에러 2: "API key not found"
```
❌ Error: API key is undefined
```

**원인:** .env.local 파일이 없거나 키가 잘못됨
**해결:**
1. `.env.local` 파일이 있는지 확인
2. `REACT_APP_ANTHROPIC_API_KEY=...` 확인
3. 터미널 종료 후 다시 시작

---

#### 에러 3: "npm: command not found"
```
❌ Command 'npm' not found
```

**원인:** Node.js가 제대로 설치되지 않음
**해결:**
```bash
node --version  # Node가 설치되었는지 확인
# 설치 안 되었으면 https://nodejs.org에서 다시 설치
```

---

#### 에러 4: "CORS Error"
```
❌ Access to XMLHttpRequest has been blocked by CORS policy
```

**원인:** 브라우저 보안 정책
**해결:**
- 로컬 개발(`localhost`)에서 테스트할 때는 대부분 무시 가능
- Vercel 배포하면 자동 해결

---

#### 에러 5: "포트 5173이 이미 사용 중"
```
❌ Port 5173 is already in use
```

**원인:** 이전 npm run dev가 종료되지 않음
**해결:**
```bash
# 새로운 터미널 창 열기 또는
# 기존 npm run dev 창에서 Ctrl+C 눌러 종료
```

---

### 5.2 Vercel 배포 후 환경변수 안 먹힘

**문제:** 로컬에서는 작동하는데 Vercel에서 안 됨

**원인:** Vercel 환경변수 설정 안 함

**해결:**
1. Vercel 대시보드 → 프로젝트 선택
2. Settings → Environment Variables
3. `REACT_APP_ANTHROPIC_API_KEY` 추가
4. 값 입력 (GitHub에는 노출 안 됨)
5. 재배포 (Redeploy 버튼 또는 GitHub에 다시 push)

---

### 5.3 GitHub 푸시 시 에러

**문제:** `git push` 했는데 에러

**해결:**
```bash
# 최신 변경 확인
git status

# 만약 파일이 있으면 추가
git add .

# 커밋
git commit -m "작업 내용 설명"

# 푸시
git push
```

---

### 5.4 Claude에게 더 잘 물어보는 방법

#### 좋은 질문
```
"App.jsx에서 버튼을 클릭했을 때 색상이 파란색으로 바뀌게 해줄래?
현재 코드: [현재 코드 붙여넣기]
원하는 결과: 버튼 클릭 시 배경색이 파란색으로 변함"
```

#### 나쁜 질문
```
"버튼이 작동 안 해"
```

#### 팁
1. **파일명 명시:** "App.jsx에서..."
2. **현재 상태 보여주기:** 에러 메시지, 현재 코드
3. **원하는 결과 명확히:** "이렇게 되었으면 좋겠어"
4. **한번에 많이 요청하지 말기:** 하나씩

---

### 5.5 더 배우기 위한 리소스

#### 공식 문서
- **React 공식 튜토리얼:** https://react.dev
- **Tailwind CSS:** https://tailwindcss.com/docs
- **Shadcn UI:** https://ui.shadcn.com
- **Claude API:** https://docs.anthropic.com
- **Vercel:** https://vercel.com/docs

---

### 5.6 다음 단계 (워크샵 후)

#### 1주차: 개념 정착
- 오늘 배운 프로젝트 다시 한번 만들어보기 (복붙 없이)
- Claude와의 대화 기록 정리하기

#### 2주차: 커스터마이징
- 오늘 만든 프로젝트에 새로운 기능 추가
- 예: "컬러 팔레트 생성기에 이미지 업로드 기능 추가"

#### 3주차: 새로운 프로젝트
- 팀에서 필요한 작은 도구 정의
- "디자인 메타데이터 추출기" 같은 실무 도구
- Claude에게 "이런 걸 만들 수 있을까?" 물어보기

#### 1개월 후: 습관화
- 주 2-3시간 "코딩 시간" 정하기
- 작은 아이디어부터 해결해나가기

---

### 5.7 팀 내 활용 아이디어

#### 프로토타이핑 속도 향상
```
"디자인하고 → Figma에서 보여주고 → 개발 대기"
→
"디자인하고 → 간단한 인터랙티브 프로토타입 → 개발팀과 구체적으로 협의"
```

#### 간단한 도구 직접 개발
```
필요한 도구:
- 컬러 팔레트 생성/관리
- 타이포그래피 가이드 생성
- 디자인 시스템 문서 자동 생성
- A/B 테스트 시뮬레이터
```

#### 개발팀과 협업 개선
```
"이 기능 어떻게 만들어야 할까?"
→ Claude와 빠르게 프로토타입 만들어서
→ "대충 이렇게 보여야 해" 보여주기
→ 개발팀이 정확하게 이해
```

#### 개인 프로젝트
```
- 포트폴리오 웹사이트 (동적)
- 개인 블로그 (AI 추천 기능)
- 시간 관리 앱
- 피드백 수집 도구
```

---

## 마치며

축하합니다! 이 워크샵을 끝내면 당신은:

✅ **AI와 협력하는 방법**을 배웠습니다
✅ **간단한 웹 도구**를 만들 수 있습니다
✅ **인터넷에 배포**할 수 있습니다
✅ **에러를 두려워하지 않습니다**
✅ **계속 배울 수 있는 기초**를 가졌습니다

**가장 중요한 건: 꾸준함입니다.**

매주 1-2시간, 작은 프로젝트부터 시작하세요.
"완벽하지 않은 결과물"도 괜찮습니다.
**만드는 과정이 배움입니다.**

**다음 주에 할 일:**
1. 오늘 만든 프로젝트 다시 한번 만들어보기
2. Claude에게 "이것도 가능할까?" 물어보기
3. 팀에서 필요한 작은 도구 하나 정의하기
4. Claude와 함께 그것을 만들어보기

**질문이 있으시면:**
- Claude에게 물어보세요 (99% 답변 가능)
- 에러 메시지를 Claude에게 보여주세요
- "왜 이렇게 하는가?"를 물어보세요

**행운을 빕니다!** 🚀

---

**마지막으로:**
이 가이드는 "처음" 배우는 사람들을 위해 만들어졌습니다.
완벽하지 않은 부분이 있을 수 있습니다.
그럴 땐 **당신의 최고 친구 Claude에게 물어보세요.**

**Claude는 항상 도와줄 준비가 되어 있습니다.** 😊
