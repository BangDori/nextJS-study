# Next.js Project Structure

This page provides an overview of the project structure of a Next.js application. It covers top-level files and folders, configuration files, and routing conventions within the app and pages directories.

> 이 페이지는 Next.js 애플리케이션의 프로젝트 구조에 대한 개요를 제공합니다. 여기에는 최상위 파일과 폴더, 구성 파일 및 app과 pages 디렉토리 내의 라우팅 규칙이 포함됩니다.

## Top-level folders

Top-level folders are used to organize your application's code and static assets.

> 최상위 폴더는 애플리케이션의 코드와 정적 자산을 구성하는 데 사용됩니다.

| ------------------------------- | ---------------------------------- |
| app | App Router |
| pages | Pages Router |
| public | Static assets to be served |
| src | Optional application source folder |

> app: App Router
> pages: Pages Router
> public: 제공할 정적 자산
> src: 선택적인 app 소스 폴더

## Top-level files

Top-level files are used to configure your application, manage dependencies, run middleware, integrate monitoring tools, and define environment variables.

> 최상위 파일은 애플리케이션을 구성하고, 종속성을 관리하며, 미들웨어를 실행하고, 모니터링 도구를 통합하고, 환경 변수를 정의하는 데 사용됩니다.

| Next.js            |                                         |
| ------------------ | --------------------------------------- |
| next.config.js     | Configuration file for Next.js          |
| package.json       | Project dependencies and scripts        |
| instrumentation.ts | OpenTelemetry and Instrumentation file  |
| middleware.ts      | Next.js request middleware              |
| .env               | Environment variables                   |
| .env.local         | Local environment variables             |
| .env.production    | Production environment variables        |
| .env.development   | Development environment variables       |
| .eslintrc.json     | Configuration file for ESLint           |
| .gitignore         | Git files and folders to ignore         |
| next-env.d.ts      | TypeScript declaration file for Next.js |
| tsconfig.json      | Configuration file for TypeScript       |
| jsconfig.json      | Configuration file for JavaScript       |

> Next.js
> next.config.js: Next.js 구성 파일
> package.json: 프로젝트 종속성 및 스크립트
> instrumentation.ts: OpenTelemetry 및 계측 파일, 모니터링 및 로깅을 위해 사용
> middleware.ts: Next.js 요청 미들웨어
> .env: 환경 변수
> .env.local: 로컬 환경 변수
> .env.production: 프로덕션 환경 변수
> .env.development: 개발 환경 변수
> .eslintrc.json: ESLint 구성 파일
> .gitignore: Git에 올리지 않을 파일/폴더
> next-env.d.ts: Next.js용 TypeScript 선언 파일
> tsconfig.json: TypeScript 구성 파일
> jsconfig.json: JavaScript 구성 파일

## app Routing Conventions

The following file conventions are used to define routes and handle metadata in the app router.

> 다음 파일 규칙은 app 라우터에서 라우트를 정의하고 메타데이터를 처리하는 데 사용됩니다.

### Routing Files

| ------------------------- | ---------------------------- |
| layout.js .jsx .tsx       | Layout                       |
| page.js .jsx .tsx         | Page                         |
| loading.js .jsx .tsx      | Loading UI                   |
| not-found.js .jsx .tsx    | Not found UI                 |
| error.js .jsx .tsx        | Error UI                     |
| global-error.js .jsx .tsx | Global error UI              |
| route.js .ts              | API endpoint                 |
| template.js .jsx .tsx     | Re-rendered layout           |
| default.js .jsx .tsx      | Parallel route fallback page |

> layout.js .jsx .tsx: 레이아웃
> page.js .jsx .tsx: 페이지
> loading.js .jsx .tsx: 로딩 UI
> not-found.js .jsx .tsx: 찾을 수 없는 UI
> error.js .jsx .tsx: 오류 UI
> global-error.js .jsx .tsx: 글로벌 오류 UI
> route.js .ts: API 엔드포인트
> template.js .jsx .tsx: 다시 렌더링된 레이아웃
> default.js .jsx .tsx: 병렬 경로 폴백 페이지(기본적으로 보여줄 페이지)

### Nested Routes

| ------------- | -------------------- |
| folder        | Route segment        |
| folder/folder | Nested route segment |

> folder: 경로 세그먼트
> folder/folder: 중첩된 경로 세그먼트

### Dynamic Routes

| ------------- | -------------------------------- |
| [folder]      | Dynamic route segment            |
| [...folder]   | Catch-all route segment          |
| [[...folder]] | Optional catch-all route segment |

> [folder]: 동적 경로 세그먼트
> [...folder]: 모든 경로 세그먼트
> [[...folder]]: 선택적 모든 경로 세그먼트

### Route Groups and Private Folders

| -------- | ------------------------------------------------ |
| (folder) | Group routes without affecting routing           |
| \_folder | Opt folder and all child segments out of routing |

> (folder): 라우팅에 영향을 주지 않고 경로 그룹화
> \_folder: 폴더 및 모든 하위 세그먼트를 라우팅에서 제외

### Parallel and Intercepted Routes

| -------------- | -------------------------- |
| @folder        | Named slot                 |
| (.)folder      | Intercept same level       |
| (..)folder     | Intercept one level above  |
| (..)(..)folder | Intercept two levels above |
| (...)folder    | Intercept from root        |

> @folder: 명명된 슬롯
> (.)folder: 동일 레벨 가로채기
> (..)folder: 한 레벨 위 가로채기
> (..)(..)folder: 두 레벨 위 가로채기
> (...)folder: 루트에서 가로채기

### Metadata File Conventions

#### App Icons

| File Name                     | Description              |
| ----------------------------- | ------------------------ |
| favicon.ico                   | Favicon file             |
| icon.ico .jpg .jpeg .png .svg | App Icon file            |
| icon.js .ts .tsx              | Generated App Icon       |
| apple-icon.jpg .jpeg .png     | Apple App Icon file      |
| apple-icon.js .ts .tsx        | Generated Apple App Icon |

> favicon.ico: 파비콘 파일
> icon.ico .jpg .jpeg .png .svg: 앱 아이콘 파일
> icon.js .ts .tsx: 생성된 앱 아이콘
> apple-icon.jpg .jpeg .png: 애플 앱 아이콘 파일
> apple-icon.js .ts .tsx: 생성된 애플 앱 아이콘

#### Open Graph and Twitter Images

| File Name                           | Description                |
| ----------------------------------- | -------------------------- |
| opengraph-image.jpg .jpeg .png .gif | Open Graph image file      |
| opengraph-image.js .ts .tsx         | Generated Open Graph image |
| twitter-image.jpg .jpeg .png .gif   | Twitter image file         |
| twitter-image.js .ts .tsx           | Generated Twitter image    |

> opengraph-image.jpg .jpeg .png .gif: 오픈 그래프 이미지 파일
> opengraph-image.js .ts .tsx: 생성된 오픈 그래프 이미지
> twitter-image.jpg .jpeg .png .gif: 트위터 이미지 파일
> twitter-image.js .ts .tsx: 생성된 트위터 이미지

#### SEO

| File Name      | Description           |
| -------------- | --------------------- |
| sitemap.xml    | Sitemap file          |
| sitemap.js .ts | Generated Sitemap     |
| robots.txt     | Robots file           |
| robots.js .ts  | Generated Robots file |

> sitemap.xml: 사이트맵 파일
> sitemap.js .ts: 생성된 사이트맵
> robots.txt: 로봇 파일
> robots.js .ts: 생성된 로봇 파일

## pages Routing Conventions

The following file conventions are used to define routes in the pages router.

> 다음 파일 규칙은 pages 라우터에서 라우트를 정의하는 데 사용됩니다.

### Special Files

| File Name               |                   |
| ----------------------- | ----------------- |
| \_app.js .jsx .tsx      | Custom App        |
| \_document.js .jsx .tsx | Custom Document   |
| \_error.js .jsx .tsx    | Custom Error Page |
| 404.js .jsx .tsx        | 404 Error Page    |
| 500.js .jsx .tsx        | 500 Error Page    |

> \_app.js .jsx .tsx: 커스텀 앱
> \_document.js .jsx .tsx: 커스텀 문서
> \_error.js .jsx .tsx: 커스텀 에러 페이지
> 404.js .jsx .tsx: 404 에러 페이지
> 500.js .jsx .tsx: 500 에러 페이지

### Routes

#### Folder convention

| File Name                 |             |
| ------------------------- | ----------- |
| index.js .jsx .tsx        | Home page   |
| folder/index.js .jsx .tsx | Nested page |

> index.js .jsx .tsx: 홈 페이지
> folder/index.js .jsx .tsx: 중첩된 페이지

#### File convention

| File Name          |             |
| ------------------ | ----------- |
| index.js .jsx .tsx | Home page   |
| file.js .jsx .tsx  | Nested page |

> index.js .jsx .tsx: 홈 페이지
> file.js .jsx .tsx: 중첩된 페이지

### Dynamic Routes

#### Folder convention

| File Name                        |                                  |
| -------------------------------- | -------------------------------- |
| [folder]/index.js .jsx .tsx      | Dynamic route segment            |
| [...folder]/index.js .jsx .tsx   | Catch-all route segment          |
| [[...folder]]/index.js .jsx .tsx | Optional catch-all route segment |

> [folder]/index.js .jsx .tsx: 동적 경로 세그먼트
> [...folder]/index.js .jsx .tsx: 모든 경로 세그먼트
> [[...folder]]/index.js .jsx .tsx: 선택적 모든 경로 세그먼트

#### File convention

| File Name                |                                  |
| ------------------------ | -------------------------------- |
| [file].js .jsx .tsx      | Dynamic route segment            |
| [...file].js .jsx .tsx   | Catch-all route segment          |
| [[...file]].js .jsx .tsx | Optional catch-all route segment |

> [file].js .jsx .tsx: 동적 경로 세그먼트
> [...file].js .jsx .tsx: 모든 경로 세그먼트
> [[...file]].js .jsx .tsx: 선택적 모든 경로 세그먼트

# Q&A

## OpenTelemetry의 정의

- Open과 Telemetry 의 조합어, 개방적인 모니터링 도구

#### reference

- https://jennifersoft.com/ko/blog/tech/opentelemetry

## MiddleWare의 정의

![image](https://github.com/BangDori/nextjs-study/assets/101088491/b053bbd6-d0e1-46d7-ac3f-b60b974a56a7)

- 클라이언트 요청과 서버의 응답 사이에 위치하는 소프트웨어로, 특정 작업을 수행하거나 요청을 변환하는 역할

#### reference

- https://medium.com/twolinecode/13-%EB%AF%B8%EB%93%A4%EC%9B%A8%EC%96%B4-middleware-%EB%9E%80-23abb33ec4f4

## SEO files

- sitemap은 검색 엔진 로봇에게 사이트의 구조를 제공하는 파일
- robots.txt는 search bot에게 크롤링을 위한 웹 사이트의 url별 접근 허용여부를 결정하는 파일

#### reference

- https://developers.google.com/search/docs/crawling-indexing/special-tags?hl=ko
