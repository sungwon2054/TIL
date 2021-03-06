# Chapter3, Chapter4
<br>

# 3. 콘텐츠모델, 시멘틱마크업, 블록 & 인라인

<br>

## 3.1. 콘텐츠모델
<img src="https://media.prod.mdn.mozit.cloud/attachments/2012/07/09/3704/07b3e5bb546840a09bb35d45b36009a6/Content_categories_venn.png" height="200">

#### 3.1.1. Metadata
 - 스타일, 동작 설정, 다른 문서와의 관계 등의 정보를 포함
 - 주로 head의 위치
#### 3.1.2. Flow
 - 문서의 자연스러운 흐름에 의해 배치
#### 3.1.3. Sectioning
 - 문서의 구조와 관련   
 ex) article, aside, nav, section
 
#### 3.1.4. Heading
 - 제목 태그   
 ex) h1, h2, h3, h4, h5, h6
 
#### 3.1.5. Phrasing
 - 텍스트 또는 텍스트를 꾸며주는 문단 내부 레벨   
 ex)a, i, span, textarea 등
 
#### 3.1.6. Embedded 
 - 외부 콘텐츠를 표현하는 요소   
 ex) audio, canvas, video, img
 
#### 3.1.7. Interative
 - 사용자와 상호작용을 하는 요소
 ex) __form요소__ 
 
<br>
 
## 3.2. 시멘틱 마크업
 - 기계(컴퓨터, 브라우저)가 잘 이해할 수 있도록 함

#### 3.2.1 시멘틱 마크업 하기
 - \<strong> : 중요한 (굵은)
 - \<em> : 강조하는 (기울임)
 - \<ins> : 새롭게 추가된(밑줄친)
 - \<del> : 삭제된(중간선)
 
#### 3.2.2 html5에 추가된 시멘틱 마크업
 - article : 문서, 페이지, 어플리케이션 등 따로 독리접으로 구분해 배포하거나 재사용   
 ex) 게시판, 뉴스기사 등
 - detail : 말 그대로 "열림" 상태일 때만 내부 정보 공개
 - header : 소개 및 탐색에 도움을 줌   
 ex) 제목, 로고, 검색 폼 등
 - main : 중요 콘텐츠 표시
 - footer : 기획 콘텐츠, 루트 등을 나타냄   
 ex) 작성자, 저작권 정보, 문서 등
 - section : 문서의 독립적인 구획   
 ex) 제목
  
<br>

## 3.3. 블록 & 인라인
- block level 요소 : 한 줄에 하나의 요소   
ex) div, ul, li
- inline level 요소 : 한 줄에 여러개   
ex) span, i, img
<img src="https://lh3.googleusercontent.com/proxy/R-pr6E0i-Naii3YU0NDpDN0BHenZstMMO7haZ8FCQeDzuIREsiQQCjzCDIYXjCoRs-AcDjtjbxLCo-yXWR4weaRzGfAfqJJNuy7yBznTzOcfM8wv2bTht_4xEt5by16LM3tuXJAOnwMlprXlb46R7A" height="200">

<br>
<br>

# 4. CSS 이해하기
#### CSS : Cascading Style Sheets
 - HTML을 꾸며주는 언어
 - HTML은 __정보__ CSS는 __디자인__
 
 <img src="https://tutorial.techaltum.com/images/html-css.jpg" height=300>
 
 ## 4.1 CSS 문법과 적용
 
 #### 4.1.1 CSS 구문
 ```CSS
 h1{
  color:yellow;
  font-size:2em;
 }
 ```
- 선택자(selector) -> "h1"
- 속성(property) -> "color"
- 값(value) -> "yellow"
- 선언(declaration) -> "color:yellow", "font-size:2em"
- 선언부(declaration block) -> "{color:yellow; font-size:2em;}"
- 규칙(rule set) -> "h1{color:yellow;font-size:2em;}"

##### CSS의 속성(property)과 html의 속성(attribute) 차이가 있다.
- attribute는 속성을 변경 시킬 수 없음, property는 속성 변경이 가능

#### 4.1.2. CSS 주석
```CSS
/* 주석 */
/*
 주석
 주석
*/
```

#### 4.1.3. CSS의 적용
- Inline : 해당 요소 안에 직접 선언   
```html
<div style="color:red">내용</div>
```
- Internal : head안에 <style> 태그를 넣어 사용
```html
 <head>
  <style> div{color:red;}
  </style>
 </head>
```
- External : 외부시트를 이용   
 ```html
 <!--html코드-->
 <head>
   <link rel="stylesheet" href="CSS위치.css">
 </head>
```

```CSS
/* CSS 코드 */
div{color:red;}
```
- Import : 스타일 시트 내에서 다른 스타일 시트 불러옴
```CSS
 @import url("CSS위치.css");
```

## 4.2 CSS 선택자
#### 4.2.1 선택자 1
- 요소 선택자 : 선택자 부분에 태그를 넣어줌
```CSS
h1{color:red;}
h2{color:red;}
```
- 그룹 선택자 : 선택자를 그룹화함
```CSS
h1,h2{color:red;}
```
- 전체 선택자 : 문서 내에 모든 요소 선택
```CSS
* {color:red;}
```
- class 선택자 : 요소에 구애 받지 않고 스타일 규칙 적용   
또한 class 속성이 여러개 일 수 있음
```html
<p class="foo bar">...</p>
```
```CSS
.foo{font-size:10px;}
.bar{color:blue;}
```   
- id 선택자 : class 처럼 id속성에 값을 넣어줌
```html
<p id="foo">...</p>
```
```CSS
#foo{font-size:10px;}
```   

##### id와 class의 차이는 id는 유일해야 하고 구체성의 값이 다름
#### 4.2.2. 선택자 2
- 선택자의 조합
```CSS
/* p요소이면서 class가 bar */
p.bar{}

/* class가 foo이면서 bar */
.foo.bar{}

/* id가 foo이면서 class가 bar */
#foo.bar{}
```
- 단순 속성
 ```CSS
 /* p태그이면서 class가 있는 경우 */
 p[class]{color:white;}
 /* p태그이면서 class가 있고, id가 있는 경우 */
 p[class][id]{text-decoration:underline;}
 ```
   + 정확한 속성
 ```CSS
 /* p태그이면서 classa가 foo인 경우 */
 p[class="foo"]{color:white;}
 /* p태그이면서 id가 title인 경우 */
 p[id="title"]{text-decoration:underline;}
 ```
  - 부분 속성값
   
    - \[class~="bar"] : 공백으로 구분한 __"bar" 단어가 포함__되는 요소 선택
    - \[class^="bar"] : "bar"로 __시작__하는 요소 선택
    - \[class$="bar"] : "bar"로 __끝나는__ 요소 선택
    - \[class*="bar"] : "bar" __문자가 포함__되는 요소 선택
    
#### 4.2.3. 선택자 3
- 자식 선택자 : 현재 요소의 바로 밑 요소
```CSS
div > span{color:red;}
```
- 자손 선택자 : 현재 요소 밑에 있는 요소
```CSS
div span{color:red;}
```
- 인접 형제 선택자 : 부모가 같은 요소
```CSS
div + span{color:red;}
```

#### 4.2.4. 가상 선택자
- 가상 클래스와 가상 요소로 나뉨
- 가상 클래스 : 미리 정의 해놓은 상황이 되면 스스로 클래스가 적용됨
  - :first-child : 첫 번째 자식 요소 선택
  - :last-child : 마지막 자식 요소 선택
  - :link : 하이퍼 링크이면서 __아직 방문하지 않음__
  - :visited : 이미 __방문한__ 하이퍼 링크
  - :focus : 현재 위치(초점)의 요소에 적용
  - :hover : 마우스 포인터가 있는 요소에 적용
  - :active : 사용자의 입력으로 활성화된 요소에 적용

- 가상요소 : 문서에 존재하지 않는 요소에 내용을 추가하거나 스타일 지정   
 CSS3부터 ::를 사용하지만 하위 브라우저에서 지원하지 않으면 :를 사용
  - ::before : 가장 앞에 요소를 삽입(없는 내용 생성이므로 content 속성을 추가해야함)
  - ::after : 가장 뒤에 요소를 삽입(없는 내용 생성이므로 content 속성을 추가해야함)
  - ::first-line : 요소의 첫 번째 줄에 있는 텍스트
  - ::first-letter : 요소의 첫 번째 글자
  
#### 4.3 구체성
- 선택자(selector)가 우선으로 적용해야 할 규칙(구체성이 높을수록 우선 적용)
- 구체성은 0, 0, 0, 0 으로 이루어져있음
  - !important 사용시 가장 우선권
  - 1, 0, 0, 0 : 인라인 스타일 ( ex. \<p style="color:red">\</p> )
  - 0, 1, 0, 0 : id 속성 값
  - 0, 0, 1, 0 : class 속성, 기타 속성, 가상 클래스
  - 0, 0, 0, 1 : 모든 요소, 가상 요소
  - 0, 0, 0, 0 : * (전체 선택자)
  
```CSS
h1 { ... }  /* 0,0,0,1 */
body h1 { ... }  /* 0,0,0,2 */
.grape { ... }  /* 0,0,1,0 */
*.bright { ... }  /* 0,0,1,0 */
p.bright em.dark { ... }  /* 0,0,2,2 */
#page { ... }  /* 0,1,0,0 */
div#page { ... }  /* 0,1,0,1 */
```

#### 4.4 상속
- 부모 요소를 그대로 물려 받아 자손 요소까지 적용
- 박스 모델의 속성(margin, padding, background, border 등)은 상속되지 않음
```CSS
/* CSS */
* { color: red; }
h1#page { color: gray; }
```
```html
<!--html-->
<h1 id="page">Hello, <em>CSS</em></h1>
```   

###### 다음과 같은 코드가 있을시 "Hello," 회색, "CSS" 빨간색으로 나옴
###### 상속은 구체성이 0,0,0,0 보다 더 낮음 -> 만약 전체 선택자가 없을시 "CSS"도 회색으로 나옴

#### 4.5 캐스케이딩(Cascading)
- 스타일 규칙들이 어떠한 기준으로 요소에 적용되는지
- 규칙
  1. 중요도가 선언되었는지 확인
  2. CSS의 출처에 따라 분류(제작자 > 사용자 > 사용자 에이전트)
  3. 구체성
  4. 선언순서
