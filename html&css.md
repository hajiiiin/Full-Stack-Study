# HTML이란

- 태그로 이루어진 마크업 언어

### tag

<태그명 속성명=”속성값”>내용</태그>

### 기본 구조

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/a6159d1b-ba53-4a72-a7f6-63f1ed69a2eb/Untitled.png)

### 주석

<!— 내용—>

+ 쫘아아악 드래그하고 ctrl+/하면 주석 처리됨 

# Emmet

: 자동 완성 확장 프로그램

### 글꼴 태그

- `<h1>` 제목 표시 2,3,4,5,6  있음
- `<hr>` 구분선
- `<p>` 한칸 뜀
- `<br>` 줄바꿈
- `<strong>` 진하게 강조
- `<b>` 진하게 표시
- `<em>` 이탤릭체
- `<i>` 이탤릭체

`<strong>과 <b>` `<em>과 <i>` : 각각 두 개의 기능은 같음 (둘 다 볼드체, 둘 다 이탤릭체)

<strong>과 <em>은 낭독기 기능이 가능 / 나중에 시각장애인들을 위한 화면 출력 시 유용
  
### 목록 태그

- `<ol>` : 순서가 있는 목록 표현 (type속성으로 글머리 기호 변경 가능)
- `<ul>` : 순서가 없는 목록 표현
- `<li>` : 목록 하위 항목으로 사용 `<ul>` 태그 or `<ol>` 태그 하위에 위치
- `<dl>` : definition list(정의 목록), 사전처럼 용어를 설명하는 목록
    
    ex) A는 B이다. key = value로 사용
    
- `<dt>` : definition term(정의 용어), 정의되는 용어의 제목을 넣을 때  - <dl> 태그 하위
- `<dd>` : definition description / 용어를 설명하는 데 사용, <dt>에 적은 제목에 대한 설명 - <dl>태그 하위

### 주의사항

- `<dl>` 태그는 하나 이상의 `<dt>-<dd>` 쌍의 태그  `<dl>`쓸 때  `<dt>`나 `<dd>`하나는 있어야함
    
    단, `<dt>-<dd>` 태그가 반드시 하나의 짝일 필요는 없음 
    
- `<li>` 태그는  `<ul>`의 하위 태그

## 표 태그

### table 기본 태그

`<table>` : 표를 만듦 , `<table border = "1">` 하면 두께 1의 선으로 표 만듦 → 웹 표준이 아님

`<tr>` : 행 , `<th>` 두껍게 가운데 정렬 (표 제목)

`<td>` : 열 (<tr>태그 안에 있어야함)

### table 그룹 태그

`<colgroup>` :열을 그룹으로 묶음

`<col>` : 열 단위를 나눌 수 있음 ㄴ 자식 태그

<col span = “3”> → 세 개의 열을 그룹으로 묶음

`<thead>` :표 제목 묶어

`<tbody>` : 표의 일반적인 데이터 묶음

`<tfoot>` : 표 마지막행 묶음
  
  ## semantic (의미론적) 태그 — 의미를 가지는 태그

### 이점

- 검색엔진 최적화
- 웹 접근성 향상
- 가독성 향상

`<div> </div>` : (division) 가상의 레이아웃을 설계 / 영역을 구분 (컨테이너 역할)  **block-level element**  *display값이 block*

`<span> </span>` : 영역을 구분  **inline-level element**  *display값이 inline*

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/805bbac2-57ea-4d0d-bc58-7d1cee52df88/Untitled.png)

red는 div태그 - 칸 자체를 차지함

yellow는 span태그 - 특정 부분만 공간 차지

- display값을 변경할 수도 있음

### block element VS inline element

block : 전체 공간 차지, 세로 배치 `<div>1</div><div>2</div>`하면 <div>1</div><div>2</div> 이렇게 1줄 쫙 공간 차지 그 다음 줄에 2 공간이 생김, width&height 적용o

inline: 콘텐츠만큼 공간 차지, 가로 배치 `<span>1</span><span>2</span>`하면 
  <span>1</span><span>2</span><br>
  이렇게 1 다음 바로 2나옴 1의 콘텐츠 만큼만 공간을 차지하기 때문, width&height 적용x
