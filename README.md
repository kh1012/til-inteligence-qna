# 디렉토리 구조

```py
src/
├─ app/                         # 앱 전역 설정 (라우터/프로바이더/전역 상태 등)
│  ├─ router/
│  │  ├─ routes.tsx            # 라우트 트리 정의(createBrowserRouter)
│  │  └─ guards.tsx            # 권한/진입가드(HOC 또는 loader)
│  ├─ providers/
│  │  ├─ query-client.ts       # react-query 등 클라이언트
│  │  └─ AppProviders.tsx      # 전역 Provider 조합
│  ├─ store/                    # 전역 상태(zustand/redux) 선택
│  └─ index.tsx                 # App 엔트리(라우터 Provider 연결)
│
├─ layouts/                     # 레이아웃 (중첩 라우팅의 상위 레이아웃)
│  ├─ RootLayout.tsx            # 공통(Header/Footer 등)
│  ├─ AuthLayout.tsx            # 인증 페이지용
│  └─ DashboardLayout.tsx       # 대시보드(사이드바 포함)
│
├─ pages/                       # 라우팅 대상 페이지(화면 단위)
│  ├─ home/
│  │  └─ HomePage.tsx
│  ├─ about/
│  │  └─ AboutPage.tsx
│  ├─ login/
│  │  └─ LoginPage.tsx
│  └─ dashboard/
│     ├─ DashboardHomePage.tsx
│     └─ SettingsPage.tsx
│
├─ components/                  # 재사용 UI (프레젠테이셔널)
│  ├─ ui/                       # Button, Input 같은 원자/분자 단위
│  └─ layout/                   # Header, Footer, Sidebar 등
│
├─ features/                    # 기능 단위(도메인 중심: auth, user, projects 등)
│  ├─ auth/
│  │  ├─ api/                   # signIn, signOut
│  │  ├─ hooks/                 # useCurrentUser 등
│  │  └─ components/            # AuthForm 등
│  └─ project/
│     └─ ...
│
├─ lib/                         # 유틸, axios 인스턴스, 형식화 함수 등
├─ hooks/                       # 범용 커스텀 훅(useToggle, useDebounce 등)
├─ styles/                      # 글로벌 스타일 (tailwind, reset, theme)
│  └─ index.css
├─ assets/                      # 이미지/폰트(웹폰트는 가능하면 CDN 또는 public/)
├─ types/                       # 공용 TS 타입
├─ main.tsx                     # Vite 진입(ReactDOM.createRoot)
└─ App.tsx                      # 최상위 App 컴포넌트(경량)
```
