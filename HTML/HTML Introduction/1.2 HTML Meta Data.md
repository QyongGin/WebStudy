# HTML Meta Data
HTML의 head를 사용하는 목적과 HTML 문서에 어떤 영향을 끼치는지 학습한다.
### 메타데이터(metadata)
메타데이터는 데이터를 설명하는 데이터이다. ```<head>```안에 문서 작성자나 문서 요약과 같은 문서를 설명하는 데이터인, 메타데이터를 
넣을 수 있다.

### HTML head란?
head의 내용이 하는 일은 페이지에 대한 metadata를 포함시키는 일이다.

### 제목 달기
```<title>```은 HTML 문서 전체의 타이틀 표현을 하기 위한 메타데이터이다. 브라우저에서 사이트를 북마크할 때, ```<title>```
의 내용을 북마크 이름으로 추천하기도 하는 등, 검색결과로 사용된다.

## 메타데이터 : <meta> 요소
### 문서의 character 인코딩을 특정하기
```html
<meta charset = "utf-8" />
```
이 요소는 문서의 character 문서에서 허용하는 문서 집합(character set) encoding에 대해 간단히 표시한다.
```utf-8```은 전세계적인 character 집합으로 많은 언어를 포함한다. 
### 저자와 설명 추가
- ```name```은 메타 요소가 어떤 정보의 형태를 갖고 있는지 알려준다.
- ```content```는 실제 메타데이터의 콘텐츠이다.
이 두 가지 메타데이터는 페이지에서 관리자를 정리하고 머릿말을 요약하는데 유용하다.
```html
<meta name="author" content="Chris Mills" />
<meta
  name="description"
  content="The MDN Learning Area aims to provide
complete beginners to the Web with all they need to know to get
started with developing web sites and applications." />
```
페이지 콘텐츠 관련 키워드를 포함시키면 검색엔진에서 페이지가 더 많이 표시된다. 이러한 활동을 Search Engine Optimization, 또는 
SEO라고 한다.<br><br>
Google에서 홈페이지를 검색시 몇 가지 관련 서브 페이지가 표시되는데 이를 사이트 링크라 하며 Google의 웹 마스터 도구에서 구성한다.
참고로 많은 ```<meta>```기능들이 사용되지 않는다. 스팸 발송자들이 키워드를 남발하는 등의 악용 사례가 생겨 검색 엔진이 무시를 하게 되었다.
### 맞춤 아이콘 추가하기
커스텀 아이콘 레퍼런스를 메타데이터에 추가하고 이를 페이지의 탭 등에서 보게 한다. 
이 아이콘을 파비콘(Favicon)이라 한다.<br><br>
파비콘(Favicon)은 웹 사이트를 대표하기 위해 웹 브라우저에서 사용되는 16x16 픽셀의 작은 이미지다. 즐겨찾기 아이콘 favorite icon의
줄임말이다.<br><br>
ICO 파일 포맷은 Mincrosoft Windows의 아이콘에 쓰이는 그림 파일 포맷이다.
1. 사이트의 인덱스 페이지 같은 디렉토리에 ```.ico```포멧의 파일을 저장한다.
2. 다음 줄을 HTML ```<head>```에 추가하여 favicon을 참조한다.
   ```html
   <link rel="shortcut icon" href="favicon.ico" type="image/x-icon" />
   ```
요즘은 다양한 아이콘 타입이 있다. MDN 홈페이지를 예로 들겠다.
```html
<!-- third-generation iPad with high-resolution Retina display: -->
<link
  rel="apple-touch-icon-precomposed"
  sizes="144x144"
  href="favicon144.png" />
<!-- iPhone with high-resolution Retina display: -->
<link
  rel="apple-touch-icon-precomposed"
  sizes="114x114"
  href="favicon114.png" />
<!-- first- and second-generation iPad: -->
<link rel="apple-touch-icon-precomposed" sizes="72x72" href="favicon72.png" />
<!-- non-Retina iPhone, iPod Touch, and Android 2.1+ devices: -->
<link rel="apple-touch-icon-precomposed" href="favicon57.png" />
<!-- basic favicon -->
<link rel="shortcut icon" href="favicon32.png" />
```
주석은 각 아이콘의 용도를 설명한다. 주석에는 웹사이트가 iPad의 홈 화면에 저장될 시 사용할 고해상도
아이콘을 제공한다, 등을 포함한다.<br><br>
다른 웹사이트의 소스 코드를 Developer tools(F12)를 사용해 탐색해보자.

## HTML에 CSS와 JavaScript 적용하기
- ```<link>```는 항상 문서의 head에 위치하고 두 가지 속성을 가진다. <br>
```rel = "stylesheet"```는 문서의 스타일 시트임을 나타내고 ```href```
는 스타일 시트 파일의 경로를 나타낸다.
```html
<link rel = "stylesheet" href = "my-css-file.css" />
```
- ```<script>```는 head에 들어갈 필요가 없다. ```</body>```태그 바로 앞, 문서 본문의 맨 끝에 넣는게 좋고
JavaScript를 적용하기 전에 모든 HTML 내용을 브라우저에서 읽었는지 확인하는게 좋다. 그렇지 않으면 액세스 과정에서 JS가
아직 존재하지 않는 요소라 판단하며 에러가 나기도 한다.

