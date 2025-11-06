# 카카오뱅크 과제

카카오뱅크 종합정보개발팀 코딩테스트 과제에 참여할 기회를 주신 것에 감사드립니다.
(규정상 모든 소스를 올리진 못하여 일부만 공유드립니다.)
---

## 🚧 종합정보개발팀 기술 스택에 맞춰 과제를 진행합니다. 🚧

## ⚡ Stack

<img src="https://img.shields.io/badge/Vue3-4FC08D?style=for-the-badge&logo=vuedotjs&logoColor=white" alt="Vue3"/>
<img src="https://img.shields.io/badge/Vite-646CFF?style=for-the-badge&logo=Vite&logoColor=white" alt="Vite"/>
<img src="https://img.shields.io/badge/Vitest-6E9F18?style=for-the-badge&logo=Vitest&logoColor=white" alt="Vite"/>
<img src="https://img.shields.io/badge/Typescript-3178C6?style=for-the-badge&logo=typescript&logoColor=white" alt="typescript"/>
<img src="https://img.shields.io/badge/sass-CC6699?style=for-the-badge&logo=sass&logoColor=white" alt="sass"/>
<img src="https://img.shields.io/badge/storybook-FF4785?style=for-the-badge&logo=storybook&logoColor=white" alt="storybook"/>
<img src="https://img.shields.io/badge/Yarn-2C8EBB?style=for-the-badge&logo=yarn&logoColor=white" alt="yarn"/>

---

## 🚥 실행 방법
- 공통
```markdown
* 의존성 설치 *
yarn install --frozen-lockfile
```

- 개발 모드
```
yarn dev
```

- 운영 모드
```
1. yarn build

2. yarn start
```

---

## 🏭 개발 환경 설정 

### vscode에서 저장(command + s)시 자동으로 prettier 실행하기

  1. command + ,를 누르고 검색에 format on save를 입력합니다.

  2. Editor: Format on Save를 체크하고 vscode를 재부팅합니다.

  3. 만약 저장시 포맷팅이 안된다면 다시 command + ,를 누르고 검색창에 default formatter를 검색하고 none으로 되어 있으면 Prettier - Code formatter로 변경 후 재부팅합니다.
---

## ❗ Troubleshooting

### Theme 만들기
1. 상대 경로에 대한 설정
```
outDir: 'dist', >> 명령어 실행 위치 기준으로 생성.
outDir: path.resolve(__dirname, 'dist'), >> 스크립트 기준으로 생성.
```
2. 기존 common.scss 와 generate 한 코드를 합치는 방식으로 변경
```
- 기존 main.scss 파일에 generate 한 코드를 합치는 방식으로 구현.
- theme 코드가 변경 됐을때 다시 빌드하기가 번거로움.
- 기존 빌드 파일들은 지우고 common.scss와 생성한 코드를 합쳐서 main.scss 파일을 생성하는 방식으로 변경 
```
3. yarn generate-theme 명령어로 생성시 public 파일도 같이 빌드된다.
4. 빌드 할 때 마다 삭제 후 새로운 파일을 생성해서 형상(git)에 반영된다. 

### Eslint typescript parsing error
1. [공식 문서](https://eslint.vuejs.org/user-guide/#configuration-eslint-config-js)를 따라서 Typescript eslint 설정. 
2. error Parsing error: Unexpected token <, :, type, as 등 Typescript 특정 문구를 파싱하지 못하는 에러 발생.
3. [이슈](https://github.com/vuejs/eslint-config-typescript/issues/76) 확인 후 수정

### UI 컴포넌트
1. button 디자인 컴포넌트를 만들었는데 태그에 따라 크기가 다르다.
2. button, input, select 등 태그에서 body 태그에 적용한 폰트 적용이 안돼서 전체적인 디자인 크기가 다름.
3. 일단 모든 태그에 폰트를 상속 받도록 설정
```
* {
  box-sizing: border-box;
  font: inherit;
};
```

### Vue + Typescript
[Vue type compiler](https://github.com/vuejs/core/blob/main/packages/compiler-sfc/src/script/resolveType.ts)  
```
type Props<Tag extends ElementType> = VNodeProps & Omit<JSX.IntrinsicElements[Tag], 'as'>
```

Vue에서 위와 같이 타입을 정의 했는데 `Unsupported type when resolving index type` 에러가 발생했다.
타입을 Tag에 따라 동적으로 할당하고 싶은데 에러가 발생한다.

아직 해결하지 못했고, [key: string]: any 처리 해놓았다.🥲

### dayjs <> Vue Datepicker 충돌?
Datapicker 값을 dayjs의 기능으로 핸들링 했는데 `dayjs is not a function` 에러가 발생한다.  
Vue Datepicker 데이터를 핸들링 할 때를 제외한 몇몇 경우에는 정상적으로 동작하는데.. 이상하다.  
일단 익숙한 moment로 불을 꺼놓은 상태.🔥

---
