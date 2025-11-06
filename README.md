# 카카오뱅크 과제

카카오뱅크 종합정보개발팀 코딩테스트 과제에 참여할 기회를 주신 것에 감사드립니다.
(규정상 모든 소스를 올리진 못하여 일부만 공유드립니다.)

---

## 🚧 종합정보개발팀 기술 스택에 맞춰 과제를 진행합니다. 🚧

## ⚡Stack

<img src="https://img.shields.io/badge/Vue3-4FC08D?style=for-the-badge&logo=vuedotjs&logoColor=white" alt="Vue3"/>
<img src="https://img.shields.io/badge/Nuxt.js-00DC82?style=for-the-badge&logo=nuxtdotjs&logoColor=white" alt="Nuxt.js"/>
<img src="https://img.shields.io/badge/Typescript-3178C6?style=for-the-badge&logo=typescript&logoColor=white" alt="typescript"/>
<img src="https://img.shields.io/badge/Yarn-2C8EBB?style=for-the-badge&logo=yarn&logoColor=white" alt="yarn"/>


## ❗ Troubleshooting
### huskey + lint-staged 적용 과정 및 문제 해결
[Huskey issue](https://github.com/typicode/husky/issues/1246)
1. huskey, lint-staged 설정
2. yarn lint-staged 수동 실행 시 정상적으로 동작
3. commit 시 `husky/pre-commit: line 6: 34188 Segmentation fault: 11  yarn lint-staged` 에러 발생(npx는 정상적으로 동작)
4. `Segmentation fault 11` 에러 코드는 메모리 관련 오류임을 확인.
5. huskey, lint-staged Segmentation fault 11 오류를 찾아보니 node version up 이 해결 방법이라고 한다.
6. node 20.11.0v --> 20.15.1v 업데이트
- 정확한 원인은 아직 파악하지 못했지만 여러 Node 버전에서 동일한 에러가 발생, lint-staged 에서도 required node version 을 지속적으로 업데이트 등 node에 문제가 있었을거라고 추측한다. 
