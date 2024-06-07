# Installation

System Requirements:

> 시스템 요구사항

- [Node.js 18.17](https://nodejs.org/en) or later
- macOS, Windows (including WSL), and Linux are supported.

## Automatic Installtion

We recommend starting a new Next.js app using `create-next-app`, which sets up everything automatically for you. To create a project, run:

> 모든 것을 자동으로 설정하는 `create-next-app`을 사용하여 새 Next.js 앱을 만드는 것을 좋습니다. 프로젝트를 생성하기 위해 실행하세요.

```bash
> npx create-next-app@latest
```

On installation, you'll see the following prompts:

> 설치 과정에서 다음 프롬프트를 볼 수 있을 것입니다.

```bash
> Would you like to use TypeScript? No / Yes
> Would you like to use ESLint? No / Yes
> Would you like to use Tailwind CSS? No / Yes
> Would you like to use `src/` directory? No / Yes
> Would you like to use App Router? (recommended) No / Yes
> Would you like to customize the default import alias (@/*)? No / Yes
> What import alias would you like configured? @/*
```

After the prompts, `create-next-app` will create a folder with your project name and install the required dependencies.

> 프롬프트 이후 `create-next-app`은 필요한 의존성을 설치하고 프로젝트 이름의 폴더를 생성합니다.

If you're new to Next.js, see the [project structure](https://nextjs.org/docs/getting-started/project-structure) docs for an overview of all the possible files and folders in your application.

> 만약 Next.js가 처음이라면, 애플리케이션에서 가능한 모든 파일과 폴더의 개요를 위해 [project structure](https://nextjs.org/docs/getting-started/project-structure) 문서를 참고하세요.

**Good to know**:

- Next.js now ships with [TypeScript](https://nextjs.org/docs/app/building-your-application/configuring/typescript), [ESLint](https://nextjs.org/docs/app/building-your-application/configuring/eslint), and [Tailwind CSS](https://nextjs.org/docs/app/building-your-application/styling/tailwind-css) configuration by default.
- You can optionally use a [`src` directory](https://nextjs.org/docs/app/building-your-application/configuring/src-directory) in the root of your project to separate your application's code from configuration files.

> **알아두면 좋은 점**:
>
> - Next.js는 이제 기본적으로 [TypeScript](https://nextjs.org/docs/app/building-your-application/configuring/typescript), [ESLint](https://nextjs.org/docs/app/building-your-application/configuring/eslint), [ESLint](https://nextjs.org/docs/app/building-your-application/configuring/eslint) 그리고 [Tailwind CSS](https://nextjs.org/docs/app/building-your-application/styling/tailwind-css)를 제공합니다.
> - 구성 파일에서 애플리케이션 코드를 분리하기 위해 프로젝트의 최상단 [`src` directory](https://nextjs.org/docs/app/building-your-application/configuring/src-directory)를 선택적으로 사용할 수 있습니다.

```
nextjs/                                nextjs-with-src/
│                                      │
├── pages/                             ├── 🗂️src/
├── components/                        │   ├── pages/
├── styles/                            │   ├── components/
├── .gitignore                         │   └── styles/
├── next.config.js                     │
├── package.json                       ├── .gitignore
└── README.md                          ├── next.config.js
                                       ├── package.json
                                       └── README.md
```

## Manual Installation

To manually create a new Next.js app, install the required packages:

> 새 Next.js 앱을 수동적으로 만들고 싶다면 필요한 패키지를 설치하세요:

```bash
> npm install next@latest react@latest react-dom@latest
```

Open your `package.json` file and add the follwing `scripts`:

> `package.json` 파일을 열고 다음 `scripts`를 추가하세요:

```json
{
  "scripts": {
    "dev": "next dev",
    "build": "next build",
    "start": "next start",
    "lint": "next lint"
  }
}
```

These scripts refer to the different stages of developing an application:

> 이 스크립트들은 애플리케이션 개발의 다양한 단계를 나타냅니다.

- `dev`: runs `next dev` to start Next.js in development mode.
- `build`: runs `next build` to build the application for production usage.
- `start`: runs `next start` to start a Next.js production server.
- `lint`: runs `next lint` to set up Next.js built-in ESLint configuration.

> - `dev`: 개발 모드에서 Next.js를 시작하기 위해 `next dev`를 실행합니다.
> - `build`: 프로덕션 용도의 애플리케이션을 구축하기 위해 `next build`를 실행합니다.
> - `start`: Next.js 프로덕션 서버를 시작하기 위해 `next start`를 실행합니다.
> - `lint`: Next.js 내장 ESLint 구성을 설정하기 위해 `next lint`를 실행합니다.

### Creating directories

Next.js uses file-system routing, which means the routes in your application are determined by how you structure your files.

> Next.js는 파일 시스템 라우팅을 사용합니다. 즉, 파일 구조 방식에 따라 애플리케이션의 경로가 결정됩니다.

#### The `app` directory

For new applications, we recommend using the [App Router](https://nextjs.org/docs/app). This router allows you to use React's latest features and is an evolution of the [Pages Router](https://nextjs.org/docs/pages) based on community feedback.

> 새로운 애플리케이션에서 [App Router](https://nextjs.org/docs/app)를 사용하는 것을 권장합니다. 이 라우터를 사용하면 React의 최신 기능을 사용할 수 있으며 커뮤니티 피드백을 기반으로 한 [Pages Router](https://nextjs.org/docs/pages)의 진화 형태입니다.

Create an `app/` folder, then add a `layout.tsx` and `page.tsx` file. These will be rendered when the user visits the root of your application (`/`).

> `app/` 폴더를 만들고, `layout.tsx`와 `page.tsx` 파일을 추가하세요. 이들은 사용자가 애플리케이션의 최상단(`/`)을 방문할 때 렌더링될 것입니다.

![image](https://github.com/BangDori/nextjs-study/assets/44726494/735d5ae1-3cd9-4105-ae0a-4ece4e46e997)

Create a [root layout](https://nextjs.org/docs/app/building-your-application/routing/pages-and-layouts#root-layout-required) inside `app/layout.tsx` with the required `<html>` and `<body>` tags:

> 필수적인 `<html>`과 `<body>` 태그와 함께 `app/layout.tsx` 내부에 [root layout](https://nextjs.org/docs/app/building-your-application/routing/pages-and-layouts#root-layout-required)을 생성합니다.

```tsx
// app/layout.tsx

export default function RootLayout({
  children,
}: {
  children: React.ReactNode;
}) {
  return (
    <html lang="en">
      <body>{children}</body>
    </html>
  );
}
```

Finally, create a home page `app/page.tsx` with some initial content:

> 마지막으로, 일부 내용이 포함된 `app/page.tsx` 홈 페이지를 만듭니다.

```tsx
// app/page.tsx

export default function Page() {
  return <h1>Hello, Next.js!</h1>;
}
```

**Good to know**: If you forget to create `layout.tsx`, Next.js will automatically create this file when running the development server with `next dev`.

> **알아두면 좋은 점**: `layout.tsx`를 만드는 것을 잊었다면, Next.js는 `next dev`로 개발 서버를 실행할 때 이 파일을 자동으로 생성합니다.

Learn more about [using the App Router](https://nextjs.org/docs/app/building-your-application/routing/defining-routes).

> [using the App Router](https://nextjs.org/docs/app/building-your-application/routing/defining-routes)에 대해 자세히 알아보세요.

#### The `pages` directory (optional)

If you prefer to use the Pages Router instead of the App Router, you can create a `pages/` directory at the root of your project.

> 앱 라우터 대신 페이지 라우터를 사용하고 싶다면, 프로젝트의 최상단에 `pages/` 디렉터리를 만들 수 있습니다.

Then, add an `index.tsx` file inside your `pages` folder. This will be your home page(`/`):

> `pages` 폴더 내부에 `index.tsx` 파일을 추가하세요. 이것이 홈 페이지입니다:

```tsx
// pages/index.tsx

export default function Page() {
  return <h1>Hello, Next.js!</h1>;
}
```

Next, add an `_app.tsx` file inside `pages/` to define the global layout. Learn more about the [custom App file](https://nextjs.org/docs/pages/building-your-application/routing/custom-app).

> 다음으로 전역 레이아웃을 정의하기 위해 `pages/` 내부에 `_app.tsx` 파일을 추가하세요. [custom App file](https://nextjs.org/docs/pages/building-your-application/routing/custom-app)에 대해 자세히 알아보세요.

```tsx
// pages/_app.tsx

import type { AppProps } from "next/app";

export default function App({ Component, pageProps }: AppProps) {
  return <Component {...pageProps} />;
}
```

Finally, add a `_document.tsx` file inside `pages/` to control the initial response from the server. Learn more about the [custom Document file](https://nextjs.org/docs/pages/building-your-application/routing/custom-document).

> 마지막으로 서버로부터 초기 응답을 조정하기 위해 `pages/` 내부에 `_document.tsx`를 추가하세요. [custom Document file](https://nextjs.org/docs/pages/building-your-application/routing/custom-document)에 대해 자세히 알아보세요.

```tsx
// pages/_document.tsx

import { Html, Head, Main, NextScript } from "next/document";

export default function Document() {
  return (
    <Html>
      <Head />
      <body>
        <Main />
        <NextScript />
      </body>
    </Html>
  );
}
```

Learn more about [using the Pages Router](https://nextjs.org/docs/pages/building-your-application/routing/pages-and-layouts).

> [using the Pages Router](https://nextjs.org/docs/pages/building-your-application/routing/pages-and-layouts)에 대해 더 자세히 알아보세요.

**Good to know**: Although you can use both routers in the same project, routes in `app` will be prioritized over `pages`. We recommend using only one router in your new project to avoid confusion.

> **알아두면 좋은 점**: 동일한 프로젝트 내에서 두 라우터를 모두 사용할 수 있지만, `app` 경로가 `pages`보다 우선시됩니다. 혼란을 피하기 위해 새 프로젝트에서는 오직 하나의 라우터만 사용하는 것을 권장합니다.

#### The `public` folder (optional)

Create a `public` folder to store static assets such as images, fonts, etc. Files inside `public` directory can then be referenced by your code starting from the base URL(`/`).

> 이미지, 폰트 등과 같은 정적 자산들을 저장하기 위해 `public` 폴더를 생성하세요. 그러면 `public` 디렉터리 내부 파일들은 기본 URL(`/`)로부터 시작하는 코드에 의해 참조되어질 수 있습니다.

## Run the Development Server

1. Run `npm run dev` to start the development server.
2. Visit `http://localhost:3000` to view your application.
3. Edit `app/page.tsx` (or `pages/index.tsx`) file and save it to see the updated result in your browser.

> 1. 개발 서버를 시작하기 위해 `npm run dev`를 실행하세요.
> 2. 애플리케이션 보기 위해 `http://localhost:3000`을 방문하세요.
> 3. 브라우저에 업데이트된 결과를 확인하기 위해 `app/page.tsx` (혹은 `pages/index.tsx`) 파일을 수정하고 저장하세요.

# Q&A

## 왜 Node.js 18.17 버전 이상이여야 할까?

> Why does NextJS require Node.js version 18.17.0 or higher?

위 문장으로 구글링을 해봤는데, 원하는 답을 찾을 수 없어서 GPT 4o에 질문해서 얻은 답변입니다.

---

Next.js는 여러 가지 이유로 Node.js 버전 18.17.0 이상을 요구합니다. 이는 주로 호환성, 성능 그리고 새로운 기능을 활용하기 위함입니다. 주요 이유는 다음과 같습니다.

1. 향상된 성능 및 안정성
2. 새로운 기능 및 API
3. 보안 강화
4. LTS 버전 중 하나 (현재 LTS는 v20.14.0)
5. V8 엔진 업그레이드
6. 최신 도구와의 호환성

> #### reference
>
> - https://nodejs.org/en/blog/announcements/v18-release-announce
> - https://nodejs.org/en/blog/release/v18.17.0
