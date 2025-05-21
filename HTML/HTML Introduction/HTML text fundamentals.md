HTML는 브라우저가 텍스트를 올바르게 표시하도록 텍스트 구조와 의미(시멘틱sementics)를 제공해야 한다.<br>
이번에는 HTML을 사용하여 제목 및 단락을 추가하고 단어를 강조, 목록을 만드는 방법 등으로 텍스트 페이지를 구성하는 방법을 설명한다.

## 제목과 단락
- 대부분의 구조화된 텍스트는 제목과 단락으로 구성된다. 
- HTML에서 각 단락은 ```<p>```요소 안에 둘러싸여야 한다. 각 제목도 heading(```<h1>```)요소 안에 둘러싸여야 한다.
- heading 요소는 총 6개다. ```<h1>,<h2>,<h3>,<h4>,<h5>,<h6>``` 각 요소는 문서에서 다른 수준의 내용을 나타낸다.
예시로 메인 제목은 ```<h1>``` 소제목은 ```<h2>``` 소제목의 소제목을 ```<h3>```로 나타내는 방법이 있다.

```html
<!-- 실습 -->
<h1>제목입니다.</h1>
<h2>소제목입니다.</h2>
<p>
요소 h1을 사용하느냐, h1처럼 보이게 하느냐는 엄연히 다릅니다.
요소로써 h1을 사용해야 검색엔진에 반영되어 도움이 됩니다.
</p>
```


### 구조화된 계층 구현
예시로 한 이야기에서 ```<h1>```은 제목을 나타내고 ```<h2>```는 각 장의 제목을 나타내고 ```<h3>```는 각 장의 하위 절을
나타낸다.
```html
<h1>The Crushing Bore</h1>

<p>By Chris Mills</p>

<h2>Chapter 1: The dark night</h2>

<p>
  It was a dark night. Somewhere, an owl hooted. The rain lashed down on the ...
</p>

<h2>Chapter 2: The eternal silence</h2>

<p>
  Our protagonist could not so much as a whisper out of the shadowy figure ...
</p>

<h3>The specter speaks</h3>

<p>
  Several more hours had passed, when all of a sudden the specter sat bolt
  upright and exclaimed, "Please have mercy on my soul!"
</p>
```
### 구조화된 계층을 만들 때 기억할 관례

- 가급적이면 페이지 당 하나의 ```<h1>```만 사용한다.
- 각 표제는 올바른 순서로 사용한다. ```<h2>```를 ```<h3>```의 하위 표제로 사용하지 않는다.
- Heading의 종류는 6개지만, 꼭 필요하지 않다면 한 페이지에 3개 이상 다루지 않는다. 많아지면 다루기 힘들고 탐색하기 어렵다. 필요하다면
- 컨텐츠를 여러 페이지로 나누자.

### 구조가 필요한 이유
- 유저는 필요한 컨텐츠를 빠르게 훑어보는 경향이 있어, 자주 heading만 읽기도 한다. 몇 초 안에 필요한 정보를 찾지 못하면 그들을 떠나기 쉽상이다.
- 검색 엔진은 페이지 내 heading을 페이지 검색 순위에 영향을 주는 중요한 키워드로 고려해 indexing한다. heading이 없다면 검색 엔진 최적화가 되지 못한다.
- 시각 장애인은 소프트웨어를 사용해 웹페이지를 듣는다. heading이 없다면 그들은 문서 전체를 읽게되고 만다.
- 컨테츠를 CSS로 꾸미거나 JavaScript로 동작시키기 위해 컨텐츠를 감싸는 요소가 필요하다.

### Semantic이 필요한 이유

Semantic은 주변 어디서나 사용된다. 우리는 정확한 요소를 사용하는지, 컨텐츠에 정확한 의미와 기능, 모습을 담았는지 확실시 해야한다.
```<h1>```요소도 페이지 최상위 heading이라는 역할로 감싸는 semantic요소다. semantic은 검색 엔진이나 screen reader에서 사용되기에 작업과 관련된 요소를 사용해야 한다.
## Lists
### Unordered list 순서 없는 리스트
정렬되지 않은 목록은 항목의 순서가 중요하지 않은 목록을 만들 때 사용한다.
```html
<!-- 쇼핑 리스트 -->
<ul>
  <li>milk</li>
  <li>cookie</li>
  <li>bread</li>
</ul>
```
리스트를 정렬하기 위해 ```<ul>``` element로 감싸주고 리스트 항목들을 ```<li>```(list item) 태그로 감싸줍니다.
### Ordered list 순서 있는 리스트
항목의 순서가 중요한 목록은 순서가 존재하는 리스트를 사용합니다.
```html
<ol>
  <li>옷을 입는다.</li>
  <li>신발을 신는다.</li>
  <li>학교에 간다.</li>
  <li>어린이 날인걸 깨닫고 집으로 돌아온다.</li>
</ol>
```
```<ol>```태그로 감싸기만 하면 마크업 구조는 순서가 없는 리스트와 동일하다.
```html
<!-- 레시피 만들기 -->
<h1>에그 치즈 토스트</h1>
<p>빵 한장으로 만들기 때문에 부담스럽지 않고 설거지도 불편하지 않게 팬 하나로 만들 수 있습니다!</p>
<h2>준비물</h2>
<ul> 
  <li>식빵 2장</li>
  <li>계란 2개</li>
  <li>체다치즈 1개</li>
</ul>
<h2>조리법</h2>
<ol>
  <li>소금을 살짝 넣고 섞는다.</li>
  <li>프라이팬에 식용유를 넣고 예열한다</li>
  <li>...</li>
</ol>
```
### 리스트 내부의 리스트 Nesting lists
리스트 내부에 다른 리스트를 추가해도 된다. 
```html
<ol>
  <li>옷을 입는다.</li>
    <ul>
      <li>코트</li>
      <li>후드티<li>
      <li>패딩<li>
    </ul>
</ol>
```
<img width="401" alt="image" src="https://github.com/user-attachments/assets/27d5897b-6b09-458b-b5d3-d28a876cc8b9" />

## 중요와 강조

### 중요 Emphasis
- 글에서는 단어에 강세를 두기 위해 이탤릭체로 표현하는 경향이 있다.
<img width="494" alt="image" src="https://github.com/user-attachments/assets/d40807a4-9667-4681-bd93-e667dbdffec4" />

- 첫 문장과 다르게 두 번째 문장은 짜증을 표현하는 것처럼 보인다.
- HTML은 이런 경우를 표시하기 위해 ```<em>```emphasis 요소를 사용한다.
- 문서가 더 흥미롭고 화면판독기에 다른 톤의 목소리로 표현된다.
- 브라우저에서 기본은 이탤릭체로 스타일을 지정하지만 이탤릭체를 쓰기 위해 ```<em>```태그를 사용하는 일은 지양한다.

### 강조 Strong importance
- 중요한 단어를 강조하기 위해 강세를 두고 말하거나 글자를 두껍게 표현한다.
<img width="495" alt="image" src="https://github.com/user-attachments/assets/38091704-092f-4f4e-a672-6a1075b62ac2" />

- HTML에서는 이런 경우 ```<strong>```strong importance 요소를 사용한다.
- 문서를 더 유용하게 만들고 화면판독기에 인식되면 다른 톤의 목소리로 표현된다.
- 브라우저에서는 기본적으로 굵은 텍스트로 지정하지만, 마찬가지로 굵게 표현하기 위해 사용하는 일은 지양한다.

```
밑줄에 대한 위험성.
사람들은 밑줄을 하이퍼링크와 강하게 연관시킨다.
따라서 링크에만 밑줄을 긋는게 좋다.
```







