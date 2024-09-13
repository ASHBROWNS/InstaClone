# styled-components 가이드
## styled-components란?

styled-components는 React 애플리케이션에서 CSS를 작성하는 방법 중 하나입니다. styled-components는 js 내에서 CSS 스타일을 정의하고 컴포넌트에 연결할 수 있어 코드 관리와 재사용성을 높여줍니다.

## 설치하기
```bash
yarn add styled-components
```


## 기본 사용법
먼저 style을 작성할 파일을 생성합니다. (네이밍: 컴포넌트이름.js)
1. 생성한 파일에 styled-components를 임포트합니다.

```js
import styled from 'styled-components';
```

2. 스타일드 컴포넌트를 만들어봅시다.
```js
export const {변수이름} = styled.태그이름`
  /*css를 작성합니다.*/
`;
```
아래와 같이 CSS처럼 스타일을 입력할 수 있습니다.
```js
export const {변수이름} = styled.button`
  border: 1px solid;
`;
```


컴포넌트에서 스타일드 컴포넌트를 사용합니다.
위에서 제작한 변수이름을 작성해주시면 됩니다.
```js
import * as _ from './style.js'

function App() {
  return (
    <div>
      <_.{변수이름}>팔로우</_.{변수이름}>
    </div>
  );
}
```

## 중첩 스타일링
```js
export const {변수이름} = styled.div`
    background-color: red;
    h2{
        color: yellow;
    }
`
```

## 프롭스 사용하기
```js
const {변수이름} =()=> {
  return (
      <_.Container
        backgroundColor={'white'}
      >
        ~
      </_.Container>
  );
}
```

```js
export const {변수이름} = styled.div`
  background-color: ${props => props.backgroundColor || 'black'};
`;
```

## 글로벌 스타일 설정하기
전역으로 스타일을 적용하려면 `createGlobalStyle`을 사용하면됩니다.
먼저 GlobalStyle.js 파일을 생성하고 다음과 같이 작성해봅시다.
```js
import { createGlobalStyle } from 'styled-components';

const GlobalStyle = createGlobalStyle`
  body {
    margin: 0;
    padding: 0;
  }
`;
```
GlobalStyle.js를 작성하였다면 `index.js`에 GlobalStyle를 추가하면 GlobalStyle을 적용할 수 있습니다.
```js
import ReactDOM from 'react-dom/client';
import App from './App';
import GlobalStyle from './styles/globalStyle';

const root = ReactDOM.createRoot(document.getElementById('root'));
root.render(
  <React.StrictMode>
    <App />
    <GlobalStyle>
  </React.StrictMode>
);
```


## 마무리
이제 여러분은 styled-components를 사용하여 React 애플리케이션에 멋진 스타일을 적용하는 방법을 배웠습니다. 이 가이드를 참고하여 인스타그램 클론 코딩을 시작해보세요. 더 많은 기능과 스타일을 추가해보며 더욱 멋진 프로젝트를 완성해보시기 바랍니다. 화이팅!