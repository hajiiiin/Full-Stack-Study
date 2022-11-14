# React

: 사용자 정의 태그를 만드는 기술

- .js 확장자를 사용
- react 사이트

[시작하기 - React](https://ko.reactjs.org/docs/getting-started.html)

- 리액트 설치 : 실패! 💥

### 사용자 정의 태그 만들기

반드시 이름은 대문자로 시작!

```jsx
function Hearder(){
	return <header>
	<h1><a href="/">Web</a></h1>
	</header>
};

<!--구현할 때 -->
<Header></Header> 
```

🔼 header 태그를 함수로 만들어 봄

### props : 속성

```jsx
function Header(props) { //매개변수를 받아옴 props라고 지은 것뿐 이름 다르게 해도 됨
	return <header>
	<h1><a href="/">{props.title}</a></h1> //title에 있는 REAL 출력
	</header>
}

<Header tiltle="REAL"></Header> //title은 변수, 이름 바꿔도 됨
```

```jsx
import React from "react";
import "./style.css";

function Header(props) { 
	return <header>
	<h1><a href="/">{props.title}</a></h1> //title에 있는 REAL 출력
	</header>
}

function Nav(props) {
  const lis = []
  for(let i=0; i<props.topics.length; i++){
    let t = props.topics[i];
    lis.push(<li key={t.id}><a href={'/read/' + t.id}>{t.title}</a></li>)
  }
  return <nav>
    <ol>
      {lis}
      </ol></nav>
}

function Article(props) {
  return <article>
    <h2>{props.title}</h2>
    {props.body}
    </article>
}

function App() {
  const topics = [
    {id:1, title:'html', body:'html is ...'},
    {id:2, title:'css', body:'css is ...'},
    {id:3, title:'js', body:'js is ...'}
  ]
  return {
    <div>
      <Header title="WEB"></Header>
      <Nav topics={topics}></Nav>
      <Article title="Welcome" body="Hello"></Article>
    </div>
  };
}
 
export default App;
```

💥빨간 부분 오류: JSX expressions must have one parent element.

### 이벤트 기능 : 다시

`event` 

- [event.target](http://event.target) : 이벤트가 발생한 태그를 가리킴
    - ex) event.target.title.value; : 이벤트가 일어난 태그의 name이 title인 value를 가져옴
- event.preventDefault() : 이벤트 막기
    - 즉, 클릭할 때 이벤트를 지정해도 preventDefault면 클릭해도 반응 X

### state

`usestate()` 로 사용

[0]은 입력 값, [1]은 바꿀 값

ex)

const [newValues, setValues] = usestate(초기값);

➡️ setValues(newValues) : set과 new값이 같은지 비교 , 같으면 아무변화X 다르면 컴포넌트 실행

+ 컴포넌트 : 

초기값자리에 

1. primitive함수 : string, boolean, number, undefine
2. Object : array, object
    1. object일 때, newValues = {…value} 중괄호 안에 …하고 객체명해야 그 객체를 복사한 새로운 newValues가 생성됨
        1. 이후 newValues (복사본)을 수정(.push()사용)하고 setValues(newValues) set에 new 넣어주기 
    2. array일 때, {}말고 []대괄호 쓰기

### crate

- onClick={event⇒ //javascript 함수 (화살표 함수) [참고](https://www.notion.so/java-script-077f779093c949c1901e9e1e53444aa2)
    - const newtopic(새로운 변수 선언) = {변수명 : 받아올 파라미터명}

- <article>태그:
- placeholder : 입력해야 하는 칸에 멘트를 디폴트로 지정할 수 있음 (html form태그 속성!)

### Update

- state를 사용하는 것이 핵심
1. input으로 입력받기 , value에  …몰라
