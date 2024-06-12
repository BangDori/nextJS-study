# Next.js Project Structure
This page provides an overview of the project structure of a Next.js application. It covers top-level files and folders, configuration files, and routing conventions within the app and pages directories.
> Next.js 애플리케이션의 프로젝트 구조에 대한 개요를 알아봅시다.
최상위 파일 및 폴더, 구성 파일, 그리고 app 및 pages 디렉터리 내의 라우팅 규칙이 포합되어 있습니다.

## Top-level folders
Top-level folders are used to organize your application's code and static assets.
> 최상위 폴더는 애플리케이션의 코드와 정적인 에셋들을 구성하는 데 사용됩니다.

![image](https://github.com/BangDori/nextjs-study/assets/119780428/41d4528b-c137-43ef-b935-fb9b78393d17)

`app` 앱 라우터

`pages` 페이지 라우터

`public` 정적 에셋들

`src` 선택적인 애플리케이션 소스 폴더

## Top-level files
Top-level files are used to configure your application, manage dependencies, run middleware, integrate monitoring tools, and define environment variables.
> 최상위 파일은 애플리케이션을 구성, 종속성 관리, 미들웨어 실행, 모니터링 도구 통합, 환경 변수를 정의하는 데 사용됩니다.

|File|Description|
|:------|:---|
|`next.config.js`|Next.js 초기 설정 구성 파일|
|`package.json`|프로젝트 종속성과 스크립트|
|`instrumentation.ts`|OpenTelemetry(trace, metric, logs 데이터를 만들고 관리하는 API, SDK, 도구 통합 세트) 및 계측 파일|
|`middleware.ts`|리퀘스트 미들웨어|
|`.env`|환경 변수|
|`.env.local`|로컬 환경 변수|
|`.env.production`|프로덕션 환경 변수|
|`env.development`|개발 환경 변수|
|`eslintrc.json`|ESLint 구성 파일|
|`gitignore`|Git에서 무시할 파일 및 폴더|
|`next-env.d.ts`|Next.js용 TypeScript 선언 파일|
|`tsconfig.json`|TypeScript 구성 파일|
|`jsconfig.json`|JavaScript 구성 파일|


## App Routing Convention
The following file conventions are used to define routes and handle metadata in the [`app` router](https://nextjs.org/docs/app).
> 앱 라우터에서 라우트를 정의하고 메타데이터를 처리하는 데 사용되는 룰

### Routing Files

|File|Extension|Description|
|:------|:---|:---|
|`layout`|`.js` `.jsx` `.tsx`|레이아웃|
|`page`|`.js` `.jsx` `.tsx`|페이지|
|`loading`|`.js` `.jsx` `.tsx`|로딩 UI|
|`not-found`|`.js` `.jsx` `.tsx`|페이지를 찾을 수 없을 시 UI|
|`error`|`.js` `.jsx` `.tsx`|에러 UI|
|`global-error`|`.js` `.jsx` `.tsx`|글로벌 에러 UI|
|`route`|`.js` `.ts`| API 엔드포인트(API가 서버에서 리소스에 접근할 수 있도록 가능하게 하는 URL)|
|`template`|`.js` `.jsx` `.tsx`|리렌더링되는 레이아웃|
|`default`|`.js` `.jsx` `.tsx`|병렬 라우팅시의 폴백 페이지|

### Nest Routes

`folder` 라우트 세그먼트

`folder/folder` 중첩 라우트 세그먼트


### Dynamic Routes

|File|Description|
|:------|:---|
|`[folder]`|동적 라우트 세그먼트|
|`[...folder]`|캐치-올 라우트 세그먼트 ( ex.[...computer] 로 파일명을 설정하면 computer/cpu/intel 와도 매치하게 된다.)|
|`[[...folder]]`|선택적 캐치-올 라우트 세그먼트 (위 형태에 더해서 /machine 과 같은 상위 주소에서도 일치한다.)|


### Route Groups and Private Folders
|File|Description|
|:------|:---|
|`(folder)`|라우팅에 영향을 주지 않고 라우트를 그룹화 (라우팅시에 주소에 포함되지 않음)|
|`_folder`|폴더 및 모든 자식 세그먼트를 라우팅에서 제외 (라우팅 불가)|


### Parallel and Intercepted Routes
> Intercepted route 는 다른 URL의 페이지를 이동 없이 현재 페이지에서 보여주고 싶을 때(ex. 모달) 사용.

|File|Description|
|:------|:---|
|`@folder`|슬롯(슬롯들은 부모 레이아웃 페이지에 props 공유되어 자식컴포넌트와 함께 렌더링 가능)|
|`(.)folder`|동일 레벨에서 intercept|
|`(..)folder`|한 레벨 위|
|`(..)(..)folder`|두 레벨 위|
|`(...)folder`|루트에서|


### Metadata File Conventions

#### App Icons

|File|Extension|Description|
|:------|:---|:---|
|`favicon`|`.ico`|파비콘|
|`icon`|`.ico` `.jpg` `.jpeg` `.png` `.svg`|앱 아이콘|
|`icon`|`.js` `.ts` `.tsx`|생성된 앱 아이콘|
|`apple-icon`|`.jpg` `.jpeg` `.png`|애플 앱 아이콘|
|`apple-icon`|`.js` `.ts` `.tsx`|생성된 애플 앱 아이콘|

#### Open Graph and Twitter Images

|File|Extension|Description|
|:------|:---|:---|
|`opengraph-image`|`.jpg` `.jpeg` `.png` `.gif`|오픈 그래프 이미지|
|`opengraph-image`|`.js` `.ts` `.tsx`|생성된 오픈 그래프 이미지|
|`twitter-image`|`.jpg` `.jpeg` `.png` `.gif`|트위터 이미지|
|`twitter-image`|`.js` `.ts` `.tsx`|생성된 트위터 이미지|

#### SEO
|File|Extension|Description|
|:------|:---|:---|
|`sitemap`|`.xml`|사이트맵|
|`sitemap`|`.js` `.ts`|생성된 사이트맵|
|`robots`|`.txt`|로봇|
|`robots`|`.js` `.ts`|생성된 로봇|


## Page Routing Convention
The following file conventions are used to define routes in the [`pages`router](https://nextjs.org/docs/pages).
> 다음 파일 규칙은 pages 라우터에서 라우트를 정의하는 데 사용됩니다.

### Special Files

|File|Extension|Description|
|:------|:---|:---|
|`_app`|`.js` `.jsx` `.tsx`|커스텀 앱|
|`_document`|`.js` `.jsx` `.tsx`|커스텀 문서|
|`_error`|`.js` `.jsx` `.tsx`|커스텀 에러 페이지|
|`404`|`.js` `.jsx` `.tsx` |404 에러 페이지|
|`500`|`.js` `.jsx` `.tsx`|500 에러 페이지|

### Routes

#### Folder convention
|File|Extension|Description|
|:------|:---|:---|
|`index`|`.js` `.jsx` `.tsx`|홈 페이지|
|`folder/index`|`.js` `.jsx` `.tsx`|중첩 페이지|
#### File convention

|File|Extension|Description|
|:------|:---|:---|
|`index`| `.js` `.jsx` `.tsx`|홈 페이지|
|`file`|`.js` `.jsx` `.tsx`|중첩 페이지|

### Dynamic Routes

#### Folder convention
|File|Extension|Description|
|:------|:---|:---|
|`[folder]/index`| `.js` `.jsx` `.tsx`|동적 라우트 세그먼트|
|`[...folder]/index`|`.js` `.jsx` `.tsx`|캐치-올 라우트 세그먼트|
|`[[...folder]]/index`|`.js` `.jsx` `.tsx`|선택적 캐치-올 라우트 세그먼트|

#### File convention
|File|Extension|Description|
|:------|:---|:---|
|`[file]`|`.js` `.jsx` `.tsx`|동적 라우트 세그먼트|
|`[...file]`|`.js` `.jsx` `.tsx`|캐치-올 라우트 세그먼트|
|`[[...file]]`|`.js` `.jsx` `.tsx`|선택적 캐치-올 라우트 세그먼트|
