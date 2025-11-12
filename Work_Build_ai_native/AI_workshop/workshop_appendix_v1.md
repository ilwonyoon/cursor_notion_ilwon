# Vibe Coding 워크샵 - 부록

## 부록 A: 치트시트

### A.1 터미널 명령어 (복붙용)

#### 폴더 이동
```bash
cd my-folder          # 폴더로 이동
cd ..                 # 상위 폴더로 이동
cd ~                  # 홈 폴더로 이동
pwd                   # 현재 위치 확인
```

#### 파일/폴더 보기
```bash
ls (Mac/Linux)        # 파일 목록 보기
dir (Windows)         # 파일 목록 보기
ls -la                # 숨김 파일 포함
```

#### 파일/폴더 생성 및 삭제
```bash
mkdir folder-name     # 새 폴더 만들기
rm -rf folder-name    # 폴더 삭제
touch file.txt        # 파일 생성
rm file.txt           # 파일 삭제
```

#### 기타
```bash
clear (Mac/Linux)     # 터미널 화면 清
cls (Windows)         # 터미널 화면 清
exit                  # 터미널 종료
code .                # Cursor에서 열기
```

---

### A.2 Git 명령어 (복붙용)

```bash
# 설정 (처음 한 번)
git config --global user.name "Your Name"
git config --global user.email "your.email@example.com"

# 기본 워크플로우
git status            # 현재 상태 확인
git add .             # 모든 파일 준비 (staging)
git add filename      # 특정 파일만 준비
git commit -m "메시지"  # 버전 저장
git push              # GitHub에 업로드
git pull              # GitHub에서 최신 가져오기

# 확인
git log               # 커밋 히스토리 보기
git diff              # 변경 사항 보기

# 브랜치
git branch            # 브랜치 목록 보기
git branch name       # 새 브랜치 만들기
git checkout name     # 브랜치 전환
```

---

### A.3 NPM 명령어 (복붙용)

```bash
# 프로젝트 생성
npm create vite@latest my-app -- --template react

# 설치
npm install           # 모든 패키지 설치
npm install package-name  # 특정 패키지 설치

# 개발 & 빌드
npm run dev           # 개발 서버 실행
npm run build         # 프로덕션 빌드
npm run preview       # 빌드 결과 미리보기

# 확인
npm list              # 설치된 패키지 보기
npm outdated          # 오래된 패키지 확인
```

---

### A.4 Tailwind CSS 자주 쓰는 클래스

#### 색상
```jsx
// 배경색
<div className="bg-red-500">빨강</div>
<div className="bg-blue-300">연한 파랑</div>
<div className="bg-gray-900">검정</div>

// 텍스트 색
<p className="text-white">흰 글씨</p>
<p className="text-gray-700">어두운 회색</p>
<p className="text-blue-600">파란색</p>
```

#### 크기 & 간격
```jsx
// 너비, 높이
<div className="w-full">전체 너비</div>
<div className="w-96">384px 너비</div>
<div className="h-64">256px 높이</div>

// 패딩 (안쪽 여백)
<div className="p-4">모든 방향 16px</div>
<div className="px-4">좌우 16px</div>
<div className="py-2">상하 8px</div>
<div className="pt-4">위 16px</div>

// 마진 (바깥쪽 여백)
<div className="m-4">모든 방향 16px</div>
<div className="mx-auto">좌우 자동 (가운데 정렬)</div>
```

#### 정렬
```jsx
// Flex 정렬
<div className="flex justify-center">가운데 정렬</div>
<div className="flex justify-between">양쪽 끝 정렬</div>
<div className="flex items-center">수직 중앙</div>
<div className="flex gap-4">간격 16px</div>

// Grid
<div className="grid grid-cols-3">3열 그리드</div>
```

#### 텍스트
```jsx
<p className="text-lg">큰 글씨</p>
<p className="text-sm">작은 글씨</p>
<p className="font-bold">굵은</p>
<p className="italic">기울임</p>
<p className="underline">밑줄</p>
```

#### 반응형
```jsx
// 화면 크기에 따라 다르게
<div className="text-lg md:text-2xl lg:text-4xl">
  모바일: 큼 | 태블릿: 더 큼 | 데스크톱: 매우 큼
</div>

// 조건부 표시
<div className="hidden md:block">
  데스크톱에서만 보임
</div>
```

#### 다크모드
```jsx
<div className="bg-white dark:bg-gray-900">
  밝은 모드: 흰색 배경
  어두운 모드: 검정색 배경
</div>
```

#### 기타
```jsx
// 모서리
<div className="rounded">약간 둥글게</div>
<div className="rounded-lg">더 둥글게</div>
<div className="rounded-full">원형</div>

// 그림자
<div className="shadow">약한 그림자</div>
<div className="shadow-lg">강한 그림자</div>

// 경계선
<div className="border">기본 경계선</div>
<div className="border-2 border-blue-500">파란 2px 경계선</div>

// 불투명도
<div className="opacity-50">50% 투명</div>
<div className="hover:opacity-75">호버 시 75% 투명</div>
```

---

### A.5 Claude에게 물어보기 좋은 패턴

#### 기본 패턴
```
"[파일명]에서 [구체적인 요청]을 해줄래?
현재 코드: [현재 코드나 에러 메시지]
원하는 결과: [예상되는 결과]"
```

#### 구체적인 예시
```
"App.jsx에서 버튼을 클릭했을 때 텍스트가 '준비 중'에서 '완료!'로 바뀌게 해줄래?

현재 코드:
  <button onClick={handleClick}>준비 중</button>

원하는 결과:
  클릭 시 버튼 텍스트가 '완료!'로 변경됨"
```

#### 에러 해결 패턴
```
"이 에러가 뭘 의미하는지 설명해줄래?
에러 메시지:
[전체 에러 메시지 붙여넣기]

이 에러를 어떻게 해결할까?"
```

#### 기능 추가 패턴
```
"[기능 설명]을 추가해줄래?

현재 기능:
- 색상 입력받기
- 색상 표시하기

새로운 기능:
- 색상 코드 복사 버튼
- 색상 이름 표시"
```

#### 설명 요청 패턴
```
"이 코드가 뭐 하는 거야?
[해당 코드 붙여넣기]

그리고 [구체적인 부분]이 어떻게 작동하는지 설명해줄래?"
```

---

### A.6 자주 쓰는 정규 표현식

```javascript
// 이메일 검증
const email = /^[^\s@]+@[^\s@]+\.[^\s@]+$/;

// URL 검증
const url = /^(https?|ftp):\/\/[^\s]+$/;

// 숫자만 추출
const numbers = /\d+/g;

// 공백 제거
const text = "  hello  ".trim();

// 특수문자 제거
const clean = text.replace(/[^a-zA-Z0-9]/g, '');
```

---

## 부록 B: Cursor Rules 템플릿 (상세 버전)

### 템플릿 1: 디자인 시스템 프로젝트

```
당신은 React + TypeScript + Tailwind CSS 전문가입니다.
이 프로젝트는 디자인 시스템 컴포넌트를 구축하고 있습니다.

## 규칙

### 스타일링
- 모든 스타일은 Tailwind CSS 사용
- CSS 파일 생성 금지
- 모든 색상은 디자인 시스템 변수 사용
- 다크모드 지원 필수
- 반응형 디자인 필수 (모바일 우선)

### 컴포넌트
- Shadcn UI 컴포넌트 우선 사용
- 모든 컴포넌트는 src/components 폴더
- 파일명은 PascalCase (MyButton.jsx)
- Props를 통해 완전히 커스터마이징 가능
- Props는 TypeScript로 명확히 정의
- 기본값(Default Props) 설정

### 성능
- 불필요한 리렌더링 방지 (useMemo, useCallback)
- 이미지는 최적화 필수
- 번들 크기 의식
- 동적 import 고려

### 코드 스타일
- 명확한 변수명 사용
- 한국어 주석 가능
- 에러 처리 명확히
- console.log 제거

### 접근성
- ARIA 속성 고려
- 키보드 네비게이션 지원
- 색상만으로 정보 전달 금지 (아이콘 추가)
```

---

### 템플릿 2: AI 통합 프로젝트

```
당신은 Claude API를 전문으로 다루는 개발자입니다.

## API 사용 원칙

### 환경 변수
- API 키는 .env.local에만 저장
- 절대 하드코딩 금지
- GitHub에 .env* 파일 올리지 않기
- .gitignore에 설정 확인

### 에러 처리
- API 호출 시 try-catch 필수
- 사용자 친화적인 에러 메시지
- 로깅 (개발자 확인용)
- 재시도 로직 (타임아웃 시)

### 보안
- 클라이언트에서만 API 호출 (간단한 경우)
- 복잡한 경우 서버 라우트 사용
- API 키 노출되면 즉시 재발급
- Rate limiting 고려

### 사용자 경험
- API 호출 중 로딩 상태 표시
- 응답 시간 표시
- 장시간 대기 시 취소 옵션
- 실패 시 명확한 안내

### 비용 관리
- 토큰 사용량 모니터링
- 불필요한 API 호출 제거
- 적절한 모델 선택 (비용 vs 성능)
```

---

### 템플릿 3: 데이터 시각화 프로젝트

```
당신은 데이터 시각화 전문가입니다.

## 라이브러리 선택
- 간단한 차트: Recharts
- 복잡한 차트: D3.js
- 테이블: TanStack Table
- 맵: Mapbox 또는 Leaflet

## 성능
- 대용량 데이터는 페이지네이션
- 가상화 고려 (1000+ 항목)
- 무거운 계산은 Web Worker로
- 차트 리렌더링 최소화

## 접근성
- 색맹자를 위한 패턴 사용
- 범례/라벨 명확히
- 키보드 네비게이션 지원
- 마우스 호버 정보는 포커스에도 표시

## 반응형
- 모바일에서도 가독성 유지
- 터치 인터랙션 고려
- 작은 화면에서 세로 레이아웃

## 사용자 경험
- 데이터 로딩 중 상태 표시
- 줌/팬 기능 (필요시)
- 데이터 내보내기 (CSV, PNG)
- 도움말 또는 가이드
```

---

## 부록 C: Tech Stack 추천표

| 프로젝트 유형 | 추천 스택 | 이유 |
|-------------|---------|------|
| **간단한 랜딩페이지** | React + Tailwind + Vercel | 빠르고 간단, 배포 쉬움 |
| **인터랙티브 도구** | React + Shadcn + TypeScript | 컴포넌트 재사용, 타입 안정성 |
| **AI 통합** | React + Next.js + API | 서버 라우트로 보안 강화 |
| **데이터 시각화** | React + Recharts + Tailwind | 차트 라이브러리 풍부, 스타일 간단 |
| **디자인 시스템** | Storybook + Shadcn + TypeScript | 컴포넌트 문서화, 재사용성 높음 |
| **실시간 협업** | Next.js + WebSocket + Supabase | 실시간 동기화, DB 간단 |
| **모바일 앱** | React Native | 크로스 플랫폼 |
| **대시보드** | Next.js + TailwindCSS + Chart.js | SEO, 성능, 차트 라이브러리 |

---

## 부록 D: 용어 사전

| 용어 | 설명 | 예시 |
|------|------|------|
| **Component** | 재사용 가능한 UI 블록 | `<Button />`, `<Card />` |
| **Props** | 컴포넌트에 전달하는 데이터 | `<Button color="blue" size="lg">` |
| **State** | 시간에 따라 변하는 데이터 | `const [count, setCount] = useState(0)` |
| **Hook** | React 함수들 (상태, 효과 등) | `useState`, `useEffect`, `useContext` |
| **API** | 외부 서비스와 통신하는 인터페이스 | Claude API, OpenWeather API |
| **Endpoint** | API의 주소 | `https://api.anthropic.com/v1/messages` |
| **Method** | HTTP 요청 방식 | GET, POST, PUT, DELETE |
| **Request** | API에 보내는 요청 | { "model": "claude-3-5-sonnet", ... } |
| **Response** | API가 돌려주는 결과 | { "content": [{"text": "..."}] } |
| **Environment Variable** | 민감한 정보 저장 | `REACT_APP_ANTHROPIC_API_KEY` |
| **Git** | 버전 관리 도구 | 코드 변경 사항 추적 |
| **Commit** | Git에 저장하는 행위 | `git commit -m "메시지"` |
| **Repository** | 코드 저장소 | GitHub의 폴더 |
| **Branch** | 독립적인 코드 버전 | `main`, `feature/new-button` |
| **Pull Request** | 코드 변경을 병합하는 요청 | GitHub에서 코드 리뷰 |
| **Merge** | 브랜치를 병합하기 | main 브랜치로 병합 |
| **Deploy** | 코드를 웹에 올리기 | Vercel에 배포 |
| **localhost** | 내 컴퓨터 (개발 환경) | `http://localhost:5173` |
| **Production** | 인터넷에 공개된 상태 | 배포된 실제 웹사이트 |
| **Build** | 코드를 실행 가능한 형태로 변환 | `npm run build` |
| **node_modules** | 설치된 패키지들 | `npm install`로 생성됨 |
| **package.json** | 프로젝트 설정 파일 | 의존성, 스크립트 정의 |
| **ESLint** | 코드 품질 검사 | 에러, 스타일 규칙 확인 |
| **Webpack** | 모듈 번들러 | 여러 파일을 하나로 합치기 |
| **Transpile** | 최신 문법을 구형 문법으로 변환 | ES6 → ES5 |
| **Polyfill** | 오래된 브라우저 호환성 처리 | Promise 구현 추가 |
| **Cache** | 빠른 접근을 위해 데이터 저장 | 브라우저 캐시, CDN 캐시 |
| **CDN** | Content Delivery Network (빠른 배포) | 이미지, CSS, JS 캐싱 |

---

## 부록 E: 트러블슈팅 체크리스트

### 설치 문제
- [ ] Node.js 버전 확인: `node --version`
- [ ] npm 캐시 삭제: `npm cache clean --force`
- [ ] node_modules 삭제 후 재설치: `rm -rf node_modules && npm install`
- [ ] Python 설치 여부 확인 (일부 패키지 필요)

### 포트 문제
- [ ] 포트 5173이 사용 중인지 확인: `lsof -i :5173` (Mac)
- [ ] 다른 포트로 실행: `npm run dev -- --port 3000`
- [ ] 기존 프로세스 종료

### 환경변수 문제
- [ ] `.env.local` 파일이 프로젝트 루트에 있는지 확인
- [ ] 파일명이 정확한지 확인 (`.env.local`, `.env` 아님)
- [ ] 개발 서버 재시작 (터미널 Ctrl+C, 다시 npm run dev)
- [ ] 변수 이름이 `REACT_APP_` 로 시작하는지 확인

### Git 문제
- [ ] `git status` 로 현재 상태 확인
- [ ] 커밋 전 `git add .` 실행했는지 확인
- [ ] GitHub 계정 정보 설정: `git config --global user.name`
- [ ] SSH 키 또는 Personal Access Token 설정

### API 문제
- [ ] API 키가 유효한지 확인
- [ ] API 키가 정확히 복사되었는지 확인 (공백 없이)
- [ ] 해당 API가 해당 모델을 지원하는지 확인
- [ ] Rate limiting 확인 (너무 많은 요청)

### 배포 문제
- [ ] Vercel 환경변수 설정 확인
- [ ] GitHub 저장소가 공개인지 확인 (필요시)
- [ ] 배포 로그 확인 (Vercel 대시보드)
- [ ] 캐시 무효화: Vercel → Settings → Deployments → Redeploy
