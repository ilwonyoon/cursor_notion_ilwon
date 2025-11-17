# VIBE CODING WORKSHOP - 완전 초보자를 위한 가이드

---

## 파트 0: 핵심 철학 & 메시지

### 0.1 최종 정의
**"AI is magic, but we are the magicians."**

- AI는 강력한 도구이지만, 방향과 비전은 **인간**이 설정한다
- 마법처럼 보이지만 실제로는 체계적이고 의도적인 행동 (articulated, intentional behavior)
- 인간이 제어하는 것이 critical — AI는 **accelerator일 뿐**

### 0.2 마법과 마술의 차이
- **마술(magic)** = 의도적이고 계획된 행동, 명확한 목표를 향한 체계적 움직임
- **마법같음(magical)** = 놀라움, 예측 불가, 새로운 가능성

**우리가 강조하는 것:** AI와의 상호작용은 마술처럼 체계적이고 의도적이어야 하며, 동시에 마법같은 놀라움도 있다.

### 0.3 AI와의 대화 방식
- AI와 인간은 대화처럼 상호작용한다
- **확인이 필요**: "Did you understand what I requested?"
- AI가 이해했는지 검증하고, 필요하면 반복해서 명확히 한다
- 이것은 마법이 아니라 협력적인 작업

---

## 파트 1: 워크숍 목표 & 톤

### 1.1 우리가 하려는 것

**핵심 목표:**
- 코딩 경험이 없는 디자이너들을 위한 **접근 가능한** 입문
- "재미있게" 만들기 — 덜 위협적으로, 더 empowering하게
- AI 활용으로 **기술 장벽 제거**
- 워크숍 후 참여자들이 실제로 "나도 이걸 할 수 있다"는 **확신** 갖게 하기

### 1.2 워크숍의 톤

- **친근하고 실용적**: 거창한 이론 아니라 바로 사용할 수 있는 것
- **마법같지만 신비롭지 않음**: 투명성 있게 작동 원리 설명
- **AI가 enabler임을 강조**: 기술 장벽을 제거해주는 도구일 뿐
- **인간 중심**: 결국 당신의 상상력과 의도가 핵심

---

## 파트 2: 심리적 & 전략적 메시지

### 2.1 참여자를 위한 프리앰블

**워크숍 시작할 때 명확히 할 것:**
```
"Forget about your daily job, forget who you are, forget who you have been.
For the next 6 hours, you are a student. No titles, no hierarchy, just exploration."
```

- 현재의 직급, 배경, 경험을 모두 잠시 내려놓기
- 호기심과 탐구정신으로 임하기
- 실패를 두려워하지 않는 마음가짐

### 2.2 AI 시대 현실 직시

**불편한 진실:**
- 5년 내 현재 직무가 "eliminated"가 아니라 **"diminished"**될 가능성이 높다
- 주니어 디자이너와 언더그래드도 이미 채용 시장에서 어려움을 겪고 있다
- "You just didn't see the wave come. You are ignoring the wave coming to your front door."

**이 워크숍의 목적:**
- 지금 준비하지 않으면 당신도 그 피해를 입을 것
- 두렵게 하려는 게 아니라 현실을 인식하게 하기
- **지금이 배울 절호의 기회**

### 2.3 인간의 역할 재강조

**AI는 도구일 뿐이다:**
- AI는 assistive — 가속화해준다
- **방향과 목표는 여전히 인간이 설정**
- 마치 자동차, 비행기, 배처럼: 빠르게 이동하는 것은 좋지만, 목적지를 잘못 설정하면 빨리 틀린 곳에 도착한다

**두 가지 위험:**
1. **자원의 한계**: AI도 무제한한 자원이 아니다 (API 비용, 컴퓨팅 능력 제한)
2. **인간의 피로**: "faster, faster, faster"만 강조하면 피곤해지는 것은 AI가 아니라 **너 자신**이다

**결론:**
- AI는 당신의 상상력과 의도를 구현하는 도구
- 체계적인 계획과 명확한 방향이 있을 때만 가치가 있다

---

## 파트 3: 기술 셋업 및 환경

### 3.1 필수 셋업 (순서대로)

---

## 1단계: Cursor 설치 & 필수 세팅

**왜 필요한가?**
Cursor는 코드를 짜는 공간이에요. 메모장처럼 텍스트를 쓰지만, Claude AI가 안에 있어서 "이거 수정해줄래?"하면 바로 도와줍니다. 코딩하기 편하게 만들어진 도구예요.

**Cursor 다운로드:**
https://www.cursor.sh → Cursor.dmg 다운로드 → Applications 폴더로 드래그

**실행:**
Applications → Cursor 더블클릭

---

**필수 세팅 (초보 바이브 코더용):**

| 설정 | 방법 | 이유 |
|------|------|------|
| **Claude API 연동** | Cursor 열기 → Settings → Claude API 활성화 | Claude와 대화하면서 코드 작성 |
| **자동 저장** | Settings → Files: Auto Save | 저장 잊어버리는 것 방지 |
| **키보드 단축키** | Cmd+K = Claude와 대화 / Cmd+Shift+L = 터미널 열기 | 빠른 작업 흐름 |
| **코드 포맷팅** | Settings → Format On Save 활성화 | 코드가 자동으로 정렬됨 |
| **터미널 표시** | Cmd+Shift+L로 하단 터미널 열기 | 명령어 실행할 때 사용 |

**완료 확인:**
```
Cursor 실행 → 터미널 열기 (Cmd+Shift+L)
→ node --version 입력
→ 버전 번호 나타나면 완료 ✓
```

---

## 2단계: Claude Mac App 설치

**왜 필요한가?**
Claude는 AI 비서 같은 거예요. Cursor에서도 쓸 수 있지만, Mac 앱을 따로 깔면 언제든 물어볼 수 있어서 편합니다. "이거 어떻게 해?" 하면 바로 답해줘요.

**다운로드:**
App Store 검색 → "Claude" → 공식 Anthropic 앱 설치

**로그인:**
설치 후 실행 → Anthropic 계정으로 로그인

**확인:**
앱이 실행되고 대화할 수 있으면 완료 ✓

---

## 3단계: GitHub 계정 생성

**왜 필요한가?**
GitHub는 구글 드라이브처럼 코드를 클라우드에 저장하는 곳이에요. 내가 만든 코드를 안전하게 보관하고, 나중에 웹에 올릴 때 이걸 거쳐서 올립니다.

**계정 만들기:**
https://github.com/signup → 이메일, 패스워드, Username 입력 → 이메일 인증

**꼭 기억할 것:**
- Username은 나중에 변경 어려우니 신중히 정하기
- GitHub 이메일 메모해두기 (나중에 필요)

**확인:**
로그인 후 대시보드 보이면 완료 ✓

---

## 4단계: Vercel 계정 생성

**왜 필요한가?**
내 코드를 실제로 웹에 올려야 다른 사람들이 볼 수 있잖아요. Vercel은 GitHub의 코드를 받아서 자동으로 웹에 올려주는 호스팅 서비스예요.

**계정 만들기:**
https://vercel.com → "Sign Up" → GitHub로 로그인 (가장 편함)

**권한 승인:**
Vercel이 GitHub 접근할 수 있도록 "Authorize" 클릭

**확인:**
Vercel 대시보드 보이면 완료 ✓

---

## 5단계: Claude Code CLI 설치

**왜 필요한가?**
터미널(검은색 창)에서도 Claude를 부를 수 있으면, 복잡한 작업을 자동화할 수 있어요. "폴더 생성해주고 파일도 만들어줄래?" 이렇게 요청할 수 있어요.

**터미널에서:**
```bash
curl -fsSL https://claude.sh/install.sh | bash
```

**확인:**
터미널 재시작 후:
```bash
claude --version
```
버전 번호 나타나면 완료 ✓

---

## 6단계: Git 로컬 설정

**왜 필요한가?**
내가 코드를 바꿀 때마다 "누가, 언제, 뭘 바꿨는가?"를 기록해둬야 해요. 나중에 실수하면 이전 버전으로 돌아갈 수 있거든요. 그래서 내 정보를 미리 등록하는 거예요.

**터미널에서:**
```bash
git config --global user.name "Your Name"
git config --global user.email "your.email@github.com"
```

(GitHub에서 사용한 이메일과 동일하게)

---

## ✅ 최종 확인 체크리스트

- ✅ Cursor 설치 & 세팅 완료
- ✅ Claude Mac App 설치 & 로그인 완료
- ✅ GitHub 계정 생성 (Username 메모)
- ✅ Vercel 계정 생성 & GitHub 연동
- ✅ Claude Code CLI 설치 (`claude --version` 작동)
- ✅ Git 로컬 설정 완료

**모두 완료하면 워크숍 준비 끝!** 🚀

---

### 3.2 버전 관리 개념 (Git)

**Git의 역할:**
- **로컬 메모리**: 당신이 지금까지 뭘 했는지 기록
- **변경 추적**: 각 단계마다 "뭘 변경했는가?"를 메모로 남기기

**주요 명령어 (외울 필요 없음):**
- `git add` → 파일 준비하기
- `git commit` → 버전 저장하기 (메모와 함께)
- `git push` → GitHub에 업로드하기
- `git pull` → GitHub에서 받아오기
- `git checkout` → 이전 버전으로 돌아가기

**핵심 원칙:**
```
"모든 명령을 외울 필요는 없다.
개념만 이해하면 되고, 필요할 때 AI에 요청할 수 있다:
'폴더 구조를 이렇게 유지하고 싶은데, 버전 관리해줄래?'"
```

### 3.3 로컬호스트 개념

**로컬호스트란:**
- 당신의 컴퓨터에서 웹앱을 미리 보기하는 것
- 예: `localhost:3000` → 자신의 컴퓨터에서만 접근 가능

**왜 필요한가:**
- 공개하기 전에 로컬에서 테스트
- "내가 만든 게 어떻게 보이는가?"를 바로 확인
- 버그 수정 후 바로 반영

### 3.4 배포 (Vercel)

**Vercel의 역할:**
- GitHub의 코드를 가져와서 인터넷에 배포
- 실제 URL로 누구나 접근 가능하게 만들기
- 예: `your-project.vercel.app`

**자동 배포:**
- GitHub에 push하면 자동으로 Vercel에 배포됨
- 별도의 복잡한 절차 불필요

### 3.5 Claude.yaml 설정

**Claude.yaml란:**
- AI 에이전트에게 줄 "가이드라인" 또는 "지침서"
- "이 프로젝트에서는 이런 규칙을 따라줘"라고 명시

**예시:**
```yaml
guidelines:
  - Use TypeScript for type safety
  - Always use Tailwind for styling
  - Use ShadCN components when available
  - Make code responsive by default
```

**유연성:**
- 프로젝트 도중에 언제든지 업데이트 가능
- 새로운 도구나 라이브러리 추가할 때 업데이트

---

## 파트 4: 워크숍 실행 방식론

### 4.1 계획 → 실행 → 검토 방식

**절대 금지:**
```
"Just build me an app for me."
```

**올바른 방식:**
```
1. 계획: "뭘 만들고 싶은가?"
2. 설계: "어떻게 나눌까?"
3. 구현: "한 단계씩 실행해보자"
4. 검토: "예상대로 작동하는가?"
5. 반복: "다음 단계로"
```

**왜 이렇게 해야 하는가:**
- 뭘 원하는지 모르면 결과도 모른다
- 작은 단계로 나누면 문제가 생겼을 때 어디서 문제가 났는지 알 수 있다
- 반복 검토로 예상치 못한 버그를 일찍 발견

### 4.2 과도한 엔지니어링 금지

**마인드셋:**
```
"Don't over-engineer, don't over-spec.
Start small, be thought through."
```

**실제로:**
- MVP(Minimum Viable Product) 사고방식
- 한 번에 100% 완벽하게 하려고 하지 말기
- 80% 수준에서 먼저 구현하고, 피드백 받은 후 20% 개선하기

### 4.3 AI와의 상호작용

**대화 원칙:**
1. **명확하게 요청**: 모호한 말보다는 구체적인 말
   - 나쁜 예: "이거 이쁘게 해줘"
   - 좋은 예: "App.jsx에서 버튼 색깔을 파란색으로 바꾸고, 호버했을 때 진한 파란색으로 되게 해줘"

2. **이해도 확인**: AI가 이해했는지 물어보기
   - "내가 요청한 게 맞나?"
   - "이 부분에서 이건 어떻게 하지?"

3. **반복 개선**: 첫 번째 결과가 완벽하지 않으면 계속 다듬기
   - AI와 인간의 협력

### 4.4 기술적 권장사항

**모든 명령을 외울 필요는 없다:**
```
"I need version control and specific folder structure.
Can you help me with that?"
```
→ AI가 필요한 git 명령어들을 실행해줌

**Claude.yaml로 가이드:**
- 프로젝트의 규칙을 한 곳에 정리
- AI가 이 규칙을 따르면서 코드 생성
- 필요하면 중간에 수정

---

## 파트 5: 프로젝트 범위 & 기술 스택

### 5.1 프로젝트 제약

**타임프레임:**
- 총 6시간 내에 완성 가능한 프로젝트
- 너무 야심차지 않기
- MVP 수준으로

**참여자들의 상황:**
- 대부분 아이디어가 없을 것
- Simple project prompts 제공 (3-5개의 예제)
- 자유도는 있지만, 범위는 명확하게

### 5.2 권장 기술 스택 (고정)

```
Frontend:   TypeScript + React (with Next.js option)
Styling:    Tailwind CSS
Components: ShadCN UI
Hosting:    Vercel
```

**왜 이 스택인가:**
- 신뢰성이 높음 (산업 표준)
- 초보자도 배우기 쉬움
- 실제 회사에서 많이 사용
- 이 조합으로 빠르게 만들 수 있음

### 5.3 API 키 & 비용

**API 키 사용:**
- 선택사항 (필수 아님)
- 사용하려면 신용카드 등록 필요
- 비용 발생 가능성 (작은 프로젝트는 무료 범위 내)

**보안 주의:**
```
"NEVER expose your API keys to GitHub or any insecure websites."
```
- Environment variables 사용 (`.env.local`)
- 절대 `.env.local`을 Git에 commit하지 말기
- GitHub에 올릴 때는 `.gitignore`에 명시

### 5.4 초기 학습 범위

**워크숍 중에 다루는 것:**
- 기본 웹앱 빌드
- TypeScript, Next.js, Tailwind, ShadCN 기초
- Git 버전 관리
- Vercel 배포

**워크숍 후 심화할 수 있는 것:**
- Firebase (데이터베이스)
- API 키 통합 (외부 서비스)
- Open source libraries
- Web scraping / 데이터 수집 도구
- Voice APIs (음성 기능)
- 자신만의 데이터베이스 구축

**철학:**
```
"우선 기초를 다진 후, 필요할 때마다 추가하기."
```

---

## 파트 6: 워크숍 구조 & 시간 배분

### 6.1 전체 개요 (6시간)

| 시간 | 섹션 | 내용 |
|------|------|------|
| 0:00-0:20 | 오프닝 | 철학 & 심리적 메시지 |
| 0:20-1:00 | 기술 셋업 | Cursor, GitHub, CLI 설치 |
| 1:00-2:00 | 개념 이해 | Git, localhost, Vercel |
| 2:00-4:30 | 실습 프로젝트 | MVP 스코핑 & 빌드 |
| 4:30-5:30 | 배포 & 마무리 | Vercel 배포, 코드 리뷰 |
| 5:30-6:00 | 클로징 | 이후 학습 경로, Q&A |

### 6.2 각 세션별 상세 내용

**세션 0: 오프닝 (20분)**
- "AI is magic, but we are the magicians" 개념 설명
- 워크숍의 목표와 철학
- 참여자 마음가짐 (학생 모드로 전환)
- AI 시대의 현실 인식

**세션 1: 기술 셋업 (40분)**
- Cursor 설치 및 기본 사용법
- GitHub 계정 생성
- Claude Code CLI 설치
- 첫 프로젝트 폴더 생성

**세션 2: 개념 이해 (1시간)**
- Git/GitHub: 버전 관리의 개념
- Localhost: 로컬 미리보기
- Claude.yaml: AI 가이드라인
- 코드 구조 이해 (TypeScript, React, Tailwind)

**세션 3: 실습 프로젝트 (2.5시간)**
- MVP 아이디어 스코핑 (30분)
- 계획 & 설계 (30분)
- 구현 (1.5시간)
- 검토 & 피드백 (리얼타임)

**세션 4: 배포 & 마무리 (1시간)**
- Vercel 배포 (20분)
- 코드 리뷰 및 개선 (20분)
- 마무리 및 피드백 (20분)

**세션 5: 클로징 (30분)**
- 이후 학습 경로 안내
- 다음 프로젝트 아이디어
- Q&A 시간
- 축하 & 격려

### 6.3 프로젝트 아이디어 예제 (강의자가 제공)

**간단한 수준 (3-4시간 가능):**
1. Color Palette Generator — 키워드 입력 → AI가 색상 제안
2. Typography Tester — 슬라이더로 폰트 크기, 라인 높이 조정하며 미리보기
3. To-Do List with AI — 할 일 추가 + AI가 우선순위 제안
4. Quote Generator — 매번 새로운 명언 표시 (API 활용)
5. Mood Tracker — 감정 기록 → 통계 표시

**중간 수준 (5-6시간 가능):**
1. Simple Blog — 마크다운 글 작성 후 표시
2. Design Inspiration Collector — 이미지 수집 + 분류
3. Time Zone Converter — 여러 도시의 시간 표시

**핵심 원칙:**
```
"프로젝트의 목표는 '뭘 만드느냐'가 아니라
'어떻게 AI와 협력해서 빠르게 만드느냐'이다."
```

---

## 파트 7: 워크숍 후 학습 경로

### 7.1 즉시 다음 단계 (1주일)

**1단계: 오늘 배운 것 복습**
```
"Rebuild today's project from memory without AI help."
```
- 명령어를 외워보기
- Git 명령어 익히기
- React 컴포넌트 개념 정리

**2단계: 프로젝트 확장**
- 배포한 프로젝트에 새로운 기능 추가
- 스타일링 개선
- 작은 버그 수정

### 7.2 심화 학습 (2-4주)

**API 키 통합:**
- Environment variables 관리
- 외부 서비스(날씨, 뉴스 등) 연동

**Firebase 또는 데이터베이스:**
- 사용자 데이터 저장
- 계정 관리

**Open source libraries 활용:**
- GitHub에서 유용한 라이브러리 찾아 사용
- 문서 읽고 이해하기

**Voice APIs & AI 통합:**
- Claude API를 프로젝트에 직접 통합
- Voice-enabled tools 만들기

### 7.3 장기 관점 (3개월+)

**목표:**
```
"Build real tools that your team actually needs."
```

**예시:**
- 디자인 시스템 자동화 도구
- 이미지 분석 봇
- 피드백 수집 시스템
- 프로토타입 테스팅 플랫폼

### 7.4 커뮤니티 & 리소스

**학습 자료:**
- React 공식: https://react.dev
- Tailwind: https://tailwindcss.com
- ShadCN: https://ui.shadcn.com
- Claude API: https://docs.anthropic.com
- Vercel: https://vercel.com/docs

**커뮤니티:**
- GitHub Issues로 질문하기
- Claude에 계속 물어보기
- 다른 사람의 코드 읽기

---

## 최종 메시지

### 당신이 배운 것

✅ Claude를 프로그래밍에 사용하는 방법
✅ 웹앱 빌드하고 배포하는 방법
✅ 에러 메시지를 읽고 해결하는 방법
✅ 자신감 있게 계속 배우는 방법
✅ **가장 중요: 당신이 한계 없이 만들 수 있다는 확신**

### 명심할 것

```
"AI는 기술이다. 마술이 아니다.
그래서 더 강력하고, 더 투명하고, 더 신뢰할 수 있다.

당신의 상상력이 한계다.
당신의 계획, 당신의 의도, 당신의 비전.
AI는 그것을 현실로 만들어줄 뿐이다.

당신이 마술사고, AI는 마술의 도구일 뿐이다."
```

### 다음 스텝

1. 오늘 배운 것으로 뭔가 만들기
2. 에러가 나면 Claude에게 물어보기
3. 계속 만들기
4. 6개월 후, 당신은 프로를 놀라게 할 만한 것을 만들고 있을 것이다

**You got this!** 🚀

---

## 부록: 참고 자료

### 자주 묻는 질문

**Q: API 키 비용이 많이 들지 않나요?**
A: 작은 프로젝트는 무료 범위 내에서 가능. 필요하면 예산 설정 가능.

**Q: 프로그래밍 경험이 없어도 될까요?**
A: 이 워크숍이 바로 그를 위한 것. AI가 기술 장벽을 제거해줄 거야.

**Q: 배포 후 유지보수는 어떻게 하나요?**
A: Vercel이 자동으로 처리. GitHub에 push하면 끝.

**Q: 더 고급 기능을 추가하고 싶으면?**
A: Claude에 물어보고, 필요한 라이브러리 추가하면 됨. 이후 학습 경로 참고.

### 용어 정리

| 용어 | 설명 |
|------|------|
| Repository | 코드 저장소 |
| Commit | 버전 저장하기 |
| Push | GitHub에 업로드 |
| Pull | GitHub에서 받아오기 |
| Branch | 독립적인 작업 버전 |
| API | 외부 서비스 연동 |
| Environment Variable | 보안이 필요한 정보 (API 키 등) 저장소 |
| Deployment | 웹앱을 인터넷에 올리기 |
| Localhost | 자신의 컴퓨터에서만 접근 가능한 주소 |
| MVP | Minimum Viable Product (최소한의 완성된 제품) |

---

**마지막:** 이 문서는 워크숍 진행 중에 언제든지 업데이트될 수 있습니다.
질문이나 피드백은 언제든 환영합니다.
