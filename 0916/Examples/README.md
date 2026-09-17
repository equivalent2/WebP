# 3장. HTML5 문서 구조화와 웹 폼

## 강의 목표
1. HTML5의 문서 구조화의 목적과 시맨틱 태그에 대해 이해한다.
2. HTML5 시맨틱 태그로 구조화된 웹 페이지를 만들 수 있다.
3. 웹 폼의 목적을 이해한다.
4. 웹 폼의 요소를 활용하여 사용자로부터 입력 받는 웹 페이지를 작성할 수 있다.

## 1. HTML5의 문서 구조화

- 기존 HTML의 한계: 웹 문서 구조를 표현하는 태그가 없어 `<div>`나 `<table>` 태그로 구조화되어 보이게만 작성했음. 소스만 봐서는 문서 구조 파악 불가능
- 문서 구조화가 필요해진 이유: 검색 엔진이 좋아하는 웹 페이지 작성 필요성 대두, 정보 탐색이 중요해진 시대, 사물인터넷 기기들이 스스로 정보를 검색하는 시대
- 시맨틱 웹: 웹 문서를 구조화하여 의미 있는 내용 탐색이 용이한 웹
  - 기존 태그(`<p>`, `<div>`, `<h1>`, `<h2>` 등)는 문서의 구조나 의미 전달이 어려움
  - 시맨틱 태그는 문서의 구조와 의미를 전달하는 태그: `<header>`, `<section>`, `<article>`, `<main>`, `<summary>`, `<mark>`, `<time>` 등
- 구글 검색 엔진도 웹 페이지의 시맨틱 태그를 검색해 리뷰, 사람, 제품, 업체, 이벤트, 음악 등 검색 결과를 제공함

### 시맨틱 태그의 종류

- `<header>`: 페이지나 섹션의 머리말 표현. 페이지 제목, 간단한 소개 등
- `<nav>`: 하이퍼링크들을 모아 놓은 특별한 섹션. 페이지 내 목차를 만드는 용도
- `<section>`: 문서의 장(chapter)이나 절을 구성. 한 웹 페이지에 여러 `<section>` 가능. 헤딩 태그(`<h1>`~`<h6>`)로 주제 기입
- `<article>`: 본문과 연관 있지만 독립적인 콘텐트를 담는 영역. 보조 기사, 블로그 포스트, 댓글 등. 내용이 많으면 여러 `<section>`을 둘 수 있음
- `<aside>`: 본문에서 약간 벗어난 노트나 팁. 신문·잡지의 관련 기사, 삽입 어구 등. 페이지 좌우에 주로 배치
- `<footer>`: 꼬리말 영역, 주로 저자나 저작권 정보

문서의 모양(위치, 색, 배치)은 구조와 별개이며 자동으로 결정되지 않음. 개발자가 CSS3로 직접 지정해야 한다.

### 예제 3-1 구조화된 HTML5 문서 작성
`<header>`, `<nav>`, `<section>`, `<aside>`, `<footer>`를 배치하고 각 영역에 배경색과 크기를 CSS3로 지정하는 기본 시맨틱 레이아웃

문서 구조화 시 권장 사항
- 웹 페이지 전체를 시맨틱 태그로 분할
- 페이지 전체 제목과 소개는 `<header>` 태그로 작성
- 본문은 `<section>`으로 묶고, 본문 내 각 절이나 영역은 `<article>`로 작성
- 링크나 메뉴는 `<nav>` 태그로 작성
- `<header>`, `<section>`, `<article>`, `<aside>` 등에는 헤딩 태그로 제목을 붙임
- 배경 음악을 재생하는 `<audio>` 태그는 `<header>` 영역에 삽입
- 문서의 모양은 CSS3 스타일 시트로 꾸미기

## 2. 시맨틱 태그들

### 시맨틱 블록 태그
- `<figure>`: 책이나 보고서의 본문에 삽입하는 사진, 차트, 삽화, 소스 코드 등을 통상 '그림'으로 표현
- `<details>`와 `<summary>`: `<details>`는 상세 정보를 담는 시맨틱 블록 태그, `<summary>`는 그 블록의 제목을 표현

### 시맨틱 인라인 태그
- `<mark>`: 중요한 텍스트임을 표시
- `<time>`: 텍스트 내용이 시간임을 표시
- `<meter>`: 주어진 범위나 %의 데이터 양 표시
- `<progress>`: 작업의 진행 정도 표시

### 예제 3-2 `<figure>` 태그 활용
`alert()` 함수에 대한 설명과 실행 결과 스크린샷을 `<figcaption>`과 함께 하나의 `<figure>`로 블록화

### 예제 3-3 `<details>`와 `<summary>` 활용
`<details>` 태그로 Q&A 리스트를 만들어 사용자가 핸들(▶)을 클릭하면 상세 정보(답변)가 펼쳐지도록 함

### 예제 3-4 시맨틱 인라인 태그
`<mark>`, `<time>`, `<meter>`, `<progress>` 4가지 인라인 시맨틱 태그의 사용 사례. `<mark>`의 텍스트는 브라우저마다 다르게 표현되며 크롬에서는 노란색 배경으로 출력됨

### HTML5에서 제거된 태그
문서의 시맨틱 구조를 저해한다는 이유로 다음 태그들은 HTML5에서 제거됨(사용 금지)
`<big>`, `<center>`, `<dir>`, `<font>`, `<tt>`, `<u>`, `<xmp>`, `<acronym>`, `<applet>`, `<basefont>`, `<frame>`, `<frameset>`, `<noframes>`, `<strike>`

## 3. 웹 폼

- 웹폼: 웹 페이지에서 사용자 입력을 받는 폼. 로그인, 등록, 검색, 예약, 쇼핑 등에 사용
- 폼 요소: 폼을 만드는 다양한 태그 — `<input>`, `<textarea>`, `<select>` 등

### 예제 3-5 간단한 로그인 폼 만들기
사용자 ID(`<input type="text">`)와 비밀번호(`<input type="password">`) 입력창, 완료 버튼(`<input type="submit">`)으로 구성된 로그인 폼

### `<form>` 태그
`<form name="..." method="...">...</form>` 형태로 폼 요소들을 감쌈
- `name` 속성: 폼의 이름 지정
- `action` 속성: 폼 데이터를 처리할 웹 서버 응용프로그램의 이름. submit 버튼을 누르면 브라우저가 action에 지정된 프로그램의 실행을 요청함 (서버 프로그램은 Java, JSP, PHP, C/C++ 등으로 작성)
- `method` 속성: 폼 데이터를 웹 서버로 전송하는 형식. 대표적으로 GET, POST

### 네이버 검색 사례로 폼 전송 과정 이해

```
<form name="sform" action="https://search.naver.com/search.naver" method="get">
  <input name="query" type="text">
  <button type="submit">"검색"</button>
</form>
```

1. 사용자가 검색어를 입력하고 검색 버튼을 누르면 브라우저는 `<form>`의 `action`에 지정된 서버 주소를 확인
2. 웹 서버로 보낼 폼 데이터(`?query=Elvis` 등)를 URL 형태로 만듦
3. 브라우저가 해당 서버에 접속하여 응용프로그램 실행을 요청하며 데이터를 전달
4. 웹 서버에서 응용프로그램이 실행되고 검색 결과를 브라우저로 보냄
5. 브라우저가 검색 결과를 화면에 출력

### 텍스트 입력

- `<input type="text">`: 한 줄짜리 입력 창
- `<input type="password">`: 암호 입력 창. 사용자 입력 문자 대신 `*` 등 다른 글자로 출력
- `<textarea>`: 여러 줄 입력 창

### 예제 3-6 텍스트 입력
이름(`text`), 암호(`password`, `maxlength="4"`), 자기소개서(`<textarea cols rows>`)를 입력받는 폼

### `<datalist>`로 데이터 목록을 가진 텍스트 입력 창
- `<datalist>`: 목록 리스트를 작성하는 태그. `<option>` 태그로 항목 하나를 표현
- `<input type="text">`에 `list` 속성으로 연결하면 입력 가능한 데이터 목록을 드롭다운으로 제공

### 예제 3-7 데이터 목록을 가진 텍스트 입력
`<datalist>`를 사용하여 나라, 가보고 싶은 곳에 대한 선택 목록을 드롭다운으로 제공

### 텍스트/이미지 버튼 만들기
- `<input type="button|reset|submit|image" value="버튼의 문자열">`
- `<button type="button|reset|submit">버튼의 문자열</button>`

### 예제 3-8 다양한 버튼 만들기
일반(`button`), submit, reset, 이미지 버튼(`<input type="image">`와 `<button>` 안에 `<img>`)을 각각 두 가지 방식으로 작성

### 선택형 입력: 체크박스와 라디오버튼
- `<input type="checkbox">`: 체크박스 만들기
- `<input type="radio">`: 라디오버튼 만들기. `name` 속성 값이 같은 라디오버튼들이 하나의 그룹을 형성

### 예제 3-9 체크박스 만들기
짜장면·짬뽕·탕수육 체크박스. `checked` 속성이 있으면 초기에 체크된 상태로 출력

### 예제 3-10 라디오버튼 만들기
같은 `name`을 가진 라디오버튼 중 하나만 선택 가능하도록 구성, 각 항목 옆에 이미지 표시

### 선택형 입력: 콤보 박스
`<select>`: 드롭다운 리스트에 목록을 출력하고 선택하는 입력 방식. `<option>` 태그로 항목 하나를 표현

### 예제 3-11 콤보박스 만들기
짜장면·짬뽕·탕수육 3개의 선택 항목을 가지는 콤보박스. `selected` 속성이 있으면 해당 항목이 선택된 상태로 출력

### `<label>`로 폼 요소의 캡션 만들기
`<label>` 태그로 캡션과 폼 요소를 한 단위로 묶어 캡션 텍스트를 명료하게 함. 2가지 방법
```
<label>사용자 ID : <input type="text"></label>
```
```
<label for="loginID">사용자 ID : </label>
<input type="text" id="loginID">
```

### 예제 3-12 `<label>` 태그로 로그인 폼 만들기
예제 3-5의 로그인 폼 캡션을 `<label>` 태그로 감싸 다시 작성

### 선택형 요소의 캡션을 `<label>`로 감싸기
선택형 요소(체크박스, 라디오버튼)에 `<label>`을 사용하면 캡션 텍스트나 이미지를 클릭해도 폼 요소가 선택된 것으로 처리됨

### 예제 3-13 `<label>`로 라디오버튼에 캡션 만들기
예제 3-10의 라디오버튼에 `<label>` 태그로 캡션(텍스트+이미지)을 감싸 클릭 가능 영역을 넓힘

## 4. 그 밖의 폼 요소

### HTML에서의 색 표현
- 색 코드는 `#rrggbb` 형식: rr(빨강), gg(초록), bb(파랑) 농도를 각각 8비트(0~255) 범위를 16진수(00~FF)로 표기
- 예: `#8000FF`는 빨간색 성분 0x80(128), 초록색 없음, 파란색 0xFF(255)가 혼합된 보라색

### 예제 3-14 컬러 다이얼로그로 색 입력 응용
`<input type="color" value="#00BFFF">`로 컬러 다이얼로그를 열어 색을 선택하고, `onchange`로 선택한 색을 본문 글자색에 적용

### 시간 정보 입력 폼 요소
`<input type="month|week|date|time|datetime-local">`로 시간 정보만 입력받는 폼 요소를 만들 수 있음

### 예제 3-15 시간 정보 입력 폼 요소 활용
`month`, `week`, `date`, `time`, `datetime-local` 타입의 입력 요소들을 한 폼에 모아 보여줌

### 예제 3-16 생일 날짜 입력
`<input type="date">`로 생일을, `<input type="time">`으로 파티 시간을 표 형태의 폼으로 입력받음

### 스핀버튼과 슬라이드 바로 편리한 숫자 입력
- `<input type="number" min max step">`: 스핀버튼으로 정교한 값 입력
- `<input type="range" min max list="...">`: 슬라이드 바로 대략적인 값 입력. `<datalist>`의 `<option>`에 `label`을 지정하면 슬라이드 바에 눈금으로 표시됨

### 예제 3-17 `<input type="number|range">`로 편리한 숫자 입력
지속시간을 `number` 타입 스핀버튼으로, 온도를 `range` 타입 슬라이드 바(Low/Medium/High 눈금)로 입력받는 폼

### 입력할 정보의 힌트 보여주기
`placeholder` 속성으로 사용자가 입력할 데이터의 힌트를 보여줄 수 있음

### 형식을 가진 텍스트 입력
- `<input type="email">`: 이메일 주소 입력. 형식이 틀리면 전송 시 경고 표시
- `<input type="url">`: URL 입력
- `<input type="tel">`: 전화번호 입력
- `<input type="search">`: 검색어 입력

### 예제 3-18 형식을 가진 텍스트 입력
email, url, tel, search 타입의 입력 요소를 각각 `placeholder`와 함께 구성

### 예제 3-19 폼 요소의 그룹핑
`<fieldset>`과 `<legend>`로 이메일·홈페이지·전화번호 입력 요소를 하나의 그룹 박스로 묶음

## 실습 파일
- `01_structured_html5.html` — 예제 3-1 (구조화된 HTML5 문서 작성)
- `02_figure_tag.html` — 예제 3-2 (`<figure>` 태그 활용)
- `03_details_summary.html` — 예제 3-3 (`<details>`와 `<summary>` 활용)
- `04_inline_semantic_tags.html` — 예제 3-4 (시맨틱 인라인 태그)
- `05_simple_login_form.html` — 예제 3-5 (간단한 로그인 폼 만들기)
- `06_text_input.html` — 예제 3-6 (텍스트 입력)
- `07_datalist_text_input.html` — 예제 3-7 (데이터 목록을 가진 텍스트 입력)
- `08_various_buttons.html` — 예제 3-8 (다양한 버튼 만들기)
- `09_checkbox.html` — 예제 3-9 (체크박스 만들기)
- `10_radio_button.html` — 예제 3-10 (라디오버튼 만들기)
- `11_combo_box.html` — 예제 3-11 (콤보박스 만들기)
- `12_label_login_form.html` — 예제 3-12 (`<label>` 태그로 로그인 폼 만들기)
- `13_label_radio_caption.html` — 예제 3-13 (`<label>`로 라디오버튼에 캡션 만들기)
- `14_color_input.html` — 예제 3-14 (컬러 다이얼로그로 색 입력 응용)
- `15_datetime_input.html` — 예제 3-15 (시간 정보 입력 폼 요소 활용)
- `16_birthday_input.html` — 예제 3-16 (생일 날짜 입력)
- `17_number_range_input.html` — 예제 3-17 (`<input type="number|range">`로 편리한 숫자 입력)
- `18_formatted_text_input.html` — 예제 3-18 (형식을 가진 텍스트 입력)
- `19_form_grouping.html` — 예제 3-19 (폼 요소의 그룹핑)
