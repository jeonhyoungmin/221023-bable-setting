<!-- 마크다운 markdown 문법으로 작성되었습니다. -->
# setup order
## 1. npm init
> 명령을 통해 프로젝트 관리 시작
`package.json` 파일이 생성된다.
- 파이썬에서는 별도로 파일이 생성되지 않고, pip freeze 라는 명령으로 의존 모듈을 확인 할 수 있다.

## 2. babel 계열 패키지 설치
###### babel은 필요한 기능에 따라 패키지를 개별 설치한다.
[babel 공식 홈페이지 링크](https://babeljs.io/setup#installation)
---
> npm install --save-dev @babel/core
- core : 말 그대로 핵심이 되는 본체
> npm install --save-dev @babel/cli
- cli : 바벨을 cli 환경에서 실행하기 위한 기능
> npm install --save-dev @babel/preset-env
- preset-env : 프리셋 환경 설정 기능 (지원 브라우저 등)
> npm install --save-dev @babel/node
- node.js runtime 환경에서 실행하기 위한 기능
---
###### 바벨은 사용처가 다양하다.
그저 node.js 런타임 환경, cli에서 명령을 하기 위해 위와 같은 개별설치를 수동으로 진행해야 하는데 반대의 관점으로 다양한 기능들이 준비되어 babel이라는 컴파일러가 지원하는 다양한 기능을 커스텀 할 수 있다.
###### 물론 번잡한 것을 싫어하는 개발자들은,
> npm install --save-dev @babel/standalone
- 이와 같은 라이브러리를 사용하기도 한다.
- 자동화된 만큼 성능과 커스텀을 일정부분 포기해야 한다.
- HTML에서 CDN방식으로 설치하여, react JSX 작성을 컴파일한 경험이 있다.

## 3. babel.config.json 파일 생성
> 바벨과 같은 컴파일러는 동작을 수행할 '목적코드'에 대한 정의가 필요하다.
- config : 실행할 바벨의 `컴파일 방식 정의`
###### babel.config.json 파일에 아래의 속성 작성(주석제외)
{
  "presets": [
    "@babel/env"
  ]
  // preset-env 기능에는 target이라는 별도의 key가 있다.
  // 현재의 설정은 기본 컴파일 환경 설정으로 비유 할 수 있다.
}
## 4. 기본 설정 완료