# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

---

## 언어 및 커뮤니케이션 규칙

- **기본 응답 언어**: 한국어
- **코드 주석**: 한국어로 작성 (필요한 경우에만)
- **커밋 메시지**: 한국어로 작성
- **문 서 화**: 한국어로 작성
- **변수명/함수명**: 영어 (코드 표준 준수)

---

## 프로젝트 개요

**개발자 웹 이력서(포트폴리오) 개발 프로젝트**

- 반응형 웹 디자인 (모바일/태블릿/데스크톱)
- 라이트/다크 모드 지원
- 순수 HTML/CSS/JavaScript (의존성 최소화)
- 단계별 개발 로드맵 참조: `ROADMAP.md`

---

## 프로젝트 구조

### 파일 조직
```
/
├── index.html              # 메인 페이지 (HTML + CSS + JS 통합)
├── CLAUDE.md              # 이 파일
├── ROADMAP.md             # 개발 로드맵
└── .git/                  # Git 저장소
```

### 개발 단계별 구조 예정
- **Phase 1**: 기본 구조 및 레이아웃 (index.html)
- **Phase 2**: CSS 분리 (styles.css)
- **Phase 3**: JavaScript 분리 (script.js)
- **Phase 4+**: 필요시 모듈화 또는 프레임워크 도입

---

## 개발 환경 설정

### 필수 도구
- **텍스트 에디터**: VS Code 또는 선호하는 에디터
- **브라우저**: Chrome, Firefox, Safari (호환성 테스트)
- **Git**: 버전 관리

### 로컬 실행
```bash
# 간단한 로컬 서버 실행 (Python 3)
python -m http.server 8000

# 또는 (Python 2)
python -m SimpleHTTPServer 8000

# 또는 Node.js http-server 사용
npx http-server
```

**브라우저에서 접속**: `http://localhost:8000`

---

## 코드 아키텍처

### 현재 구조 (Phase 1-2)

#### HTML 레이아웃
- **Header/Navigation**: 상단 네비게이션 영역
- **Hero Section**: 프로필 및 자기소개
- **About**: 경력 요약
- **Experience**: 직무 경력
- **Skills**: 기술 스택
- **Projects**: 포트폴리오 프로젝트
- **Contact**: 연락처 정보
- **Footer**: 하단 정보

#### CSS 설계 철학
- **CSS 변수** (Custom Properties): 색상/폰트 관리
  - `--color-primary`: 주 색상
  - `--color-bg`: 배경색
  - `--font-display`: 제목 폰트
  - `--font-body`: 본문 폰트

- **다크모드 지원**: `prefers-color-scheme` 및 `data-theme` 속성
- **Flexbox/Grid**: 반응형 레이아웃
- **미디어 쿼리**: 모바일 최적화 (`@media (max-width: 480px)`)

#### JavaScript 로직
- **폼 유효성 검사**: Email 형식 검증
- **에러 처리**: 동적 에러 메시지 표시
- **사용자 상호작용**: 입력 필드 포커스/블러 처리

### 향후 구조 (Phase 3+)

```javascript
// script.js 예상 구조
// - Theme 관리 (Light/Dark 모드)
// - 페이지 스크롤 애니메이션
// - 모바일 메뉴 토글
// - 페이지 간 부드러운 네비게이션
// - 프로젝트 필터링 (선택사항)
```

---

## 개발 워크플로우

### 신규 기능 추가 단계

1. **ROADMAP.md에서 단계 확인**
   - 현재 개발 단계 파악
   - 체크리스트 업데이트

2. **코드 수정**
   - HTML: 구조 추가
   - CSS: 스타일링
   - JavaScript: 기능 구현

3. **로컬 테스트**
   ```bash
   python -m http.server 8000
   ```
   - 모든 브라우저에서 확인
   - 반응형 디자인 테스트 (DevTools)
   - 다크모드 테스트

4. **Git 커밋**
   ```bash
   git add .
   git commit -m "기능명: 상세 설명"
   ```

5. **배포**
   - GitHub Pages 또는 Netlify (예정)

---

## 스타일 가이드라인

### 색상 팔레트
```css
Primary Blue: #2563eb
Primary Dark: #1d4ed8
Primary Light: #dbeafe
Background: #ffffff (light) / #0f172a (dark)
Text: #1e293b (light) / #f1f5f9 (dark)
Border: #e2e8f0 (light) / #334155 (dark)
Error: #dc2626
```

### 폰트
- **제목**: Poppins (font-weight: 600, 700)
- **본문**: Inter (font-weight: 400, 500, 600)

### 간격 (Spacing)
- 기본 단위: 8px
- 일반적인 마진/패딩: 8px, 16px, 24px, 32px, 40px

### 반응형 브레이크포인트
```css
Mobile: < 480px
Tablet: 480px - 768px
Desktop: > 768px
```

---

## 코드 컨벤션

### HTML
- 한국어 주석만 필요한 경우 작성
- Semantic HTML 사용 (`<header>`, `<nav>`, `<section>`, `<article>`, `<footer>`)
- ID/Class 명명: 영어 (kebab-case)

### CSS
- CSS 변수를 통한 중앙 집중식 관리
- 세미콜론 필수
- 선택자 가독성을 위해 들여쓰기 사용

### JavaScript
- ES6+ 문법 사용 가능
- 함수명/변수명: camelCase (영어)
- 필요한 경우만 주석 작성 (로직이 복잡한 부분)
- 모든 이벤트 리스너는 명확한 함수로 분리

---

## 배포 체크리스트

- [ ] SEO 메타 태그 추가
- [ ] 이미지 최적화 완료
- [ ] 모든 브라우저 호환성 테스트
- [ ] 모바일 반응형 테스트
- [ ] 다크모드 테스트
- [ ] 페이지 로딩 속도 측정
- [ ] 접근성(A11y) 검사
- [ ] README.md 작성
- [ ] GitHub Pages/Netlify 배포

---

## 유용한 리소스

- **ROADMAP.md**: 단계별 개발 계획
- **Google Fonts**: 폰트 라이브러리
- **CSS 검증**: [W3C CSS Validator](https://jigsaw.w3.org/css-validator/)
- **반응형 테스트**: Chrome DevTools
- **배포 플랫폼**: GitHub Pages, Netlify, Vercel

---

**마지막 업데이트**: 2026-10-05
