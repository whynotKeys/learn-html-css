# 2025-02-17

**HTML // WAI-ARIA, 목록(ul/ol), 프레이징 요소, 인용문과 줄바꿈, 테이블, 컨테이너**

## 찾아볼 내용

- WAI-ARIA

## 수업 내용

### WAI-ARIA

- 참고 링크
  - 사람인 다니는, 접근성연구반 참여자 블로그  
    https://mulder21c.io/
  - sr-only 관련 영상  
     https://www.youtube.com/watch?v=lmYSIiZFxPI&list=PLtaz5vK7MbK3EAPhmB2gFnCU9qU72YMq3&index=1
  - (Web Accessibility Initiative - Accessible Rich Internet Applications)
  - https://www.w3.org/WAI/standards-guidelines/aria/
  - https://velog.io/@ohmy0418/WAI-ARIA
- 메뉴 정의 (role 이라는 속성으로 태그에 역할 정의)
- 속성(Properties) &상태(States)  
  -> 요소가 기본적으로 갖고 있는 특징이나 상황
  `aria-\*` 접두어를 가진다.  
  -> 상태는 요소의 상황이기에 애플리케이션 실행 중에
  자주 바뀌지만 속성은 상대적으로 잘 바뀌지 않음

  - 예시:  
    `aria-expanded="true"` : 확장된 상태
    `aria-pressed="true"` : 눌린 상태
  - `aria-hidden` : 역할/속성/상태 중 속성에 해당.  
    true로 하면 해당 태그 안에 내용을 스크린리더가 읽지 않도록 설정함

- Rich Internet Application // 서드파티 기술
  ex\_플래시

### 목록(`<ul>`/`<ol>`)

- `<ul>`의 자식은 `<li>` 태그만 허용됨
- style로 불렛 스타일 바꿀 수 있지만 요새는 css로 조정하는 방식을 많이 사용함

- 정의형 목록  
  `<dl>`(definition list) : 설명 목록 요소  
  `<dt>`(difinition term) : 용어 제목 요소  
  `<dd>`(definition description) : 용어 설명 요소

  - `<dt>` & `<dd>`는 형제, 다대다 다대일 일대다 모두 가능
  - `<dl>` 안에 `<div>` 들어갈 수 있으나, `<dt>`와 `<dd>`세트를 통으로 묶어서 모든 항목에 적용해야 문법오류 없음

  ```html
  <dl>
    <div>
      <dt>이름</dt>
      <dd>홍길동</dd>
    </div>
    <div>
      <dt>나이</dt>
      <dd>25</dd>
    </div>
  </dl>
  ```

  ※ hgroup // 제목 그룹! heading group

### 프레이징 요소

- 강조 : `<em>` 태그, `<strong>` 태그
- `<b>`,`<i>`는 강조 태그가 아님  
  `<b>` : 구분 // `<i>` : 인용, 법률용어 표현 시 사용

- 인용문과 줄바꿈 // `<q>`,`<cite>`,`<blockquote>`,`<br>`  
  ※ block : 한 줄을 통으로 차지하는 요소  
   inline : 큰 박스 안에 적용되는 작은 요소

### 캐릭터 엔티티(character entity)

- 엔터티 보는 사이트
  https://entitycode.com/  
  https://www.w3schools.com/html/html_entities.asp
- HTML에서는 스페이스 공백 무시되기 때문에 `&nbsp;` 엔터티로 입력해야 인식함!

### 테이블 관련 요소

- 참고 링크
  https://www.w3.org/WAI/tutorials/tables/
- `<table>`전체 표를 감쌈
- `<caption>`표에 대한 설명
- `<tr>`테이블 행 // `<td>`1개의 셀
- `<thead>``<tfoot>``<tbody>` 현업에서는 주로 thead->tfoot->fbody 순서로 작성  
  (어차피 렌더링 됐을 땐 foot이 맨 아래로 내려와 보임)
- `colgroup` :열(column) 단위로 스타일을 적용하거나 속성을 지정할 때 사용
- `scope`속성 : 제목셀의 유효범위(row/col). 제목태그(th)만 가질 수 있음
- th태그의 `headers` 속성 // 어떤 항목의 영향을 받는 셀인지 id로 기재해서 명시

### 컨테이너 요소

- 블록 컨테이너 요소 : `<div>`
- 인라인 컨테이너 요소 : `<span>`

**※ alias // git status 처럼 자주 쓰는 명령어 번거로우면 alis 로 등록해서 짧게 쓸 수 있음**

- 원하면 등록 해보걸아  
   `git config --global alias.st status`  
   `git config --global alias.ci commit`  
   `git config --global alias.lg "log --oneline --graph --all"`  
   `git config --global core.pager "less -X -F"`
  <br />
  <br />
  <br />

---

---

# 2025-02-18

**HTML // 섹션, 텍스트, 소스(이미지/비디오), 폼(input)**

## 수업 내용

### 섹션과 메인 요소

> 문서 또는 사이트, 애플리케이션의 각 섹션, 메인 영역을 구조화하기 위한 요소  
> &nbsp;&nbsp; ex\_ `<header>, <nav>, <main>, <**section**>, <article>, <aside>, <footer>`  
> ※ 모두 블록 레벨 엘리먼트에 해당  
> ※ section/article 구분 자체가 좀 모호하기 때문에 너무 집착할 필요는 없음.

- 특징

  - `<header>`와 `<footer>`는 한 페이지에서 여러번 쓸 수 있지만
    메인 요소는 딱 1번만 쓸 수 있음!
  - 이런 태그 요소들은 항상 위치가 같진 않음. 시멘틱 마크업에 집중해서 분석/구현.
  - 세분화된 섹션 태그가 없었을 때는 div에 역할을 부여해서 설계했음
    `html
    <div role= "banner">                 <!-- <header>태그 역할-->
    <div role= "navigation">             <!-- <nav>태그의 역할-->
    <div role= "main">                   <!-- <main>태그의 역할-->
    <div role= "article">                <!-- <article>,<section>태그의 역할-->
    <div role= "complementary">          <!-- <sidebar>태그의 역할-->
    <div role= "contentinfo">            <!-- <footer>태그의 역할-->
    `
    ---> 시멘틱 태그/SEO 관점에서 봤을 때 이제는 추가된 섹션 관련 네이티브 태그를 사용하는 것이 좋다.

- 참고 링크
  - html 섹션 태그  
     https://developer.mozilla.org/en-US/docs/Learn_web_development/Core/Structuring_content/Structuring_documents
  - 역할 부여  
     https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles

### 텍스트 레벨 요소

> 하나의 태그가 브라우저에서 실제로 코딩된 그 영역(행 안의 일부분)만 차지하는 요소  
> &nbsp;&nbsp; ex\_ `<sup>, <sub>, <abbr>, <time>, <s>, <small>, <mark>`

- 사용 예시
  ```html
  <!-- 아래첨자(sub)와 위첨자(sup) -->
  <div>H<sub>2</sub>SO<sup>4</sup></div>
  <!-- 축약어 : abbr// title 속성으로 커서 올렸을 때 tooltip에 전체 단어 표시 -->
  <abbr title="저녁메뉴추천">저메추</abbr>
  <abbr title="HyperText Markup Language">HTML</abbr>
  <!-- 날짜 및 시간 정보 : time// datetime속성이 시간 정보를 지정해줌 -->
  <time datetime="2022-01-02T09:00:00">2025년 2월 18일</time>
  <div>개발자<time datetime="2022-01-02"> 시작일</time></div>
  <!-- 취소 정보 : s -->
  정상가: <s>100,000원</s>
  할인가: 9,900원
  <!-- 저작권 정보 : small -->
  <small>copyright &copy; 회사명 2025</small>
  <!-- 하이라이트 정보 : mark -->
  <div>저녁은 역시 <mark>치킨</mark></div>
  ```
- ✅출력 결과
   <div>H<sub>2</sub>SO<sup>4</sup></div>
   <abbr title="저녁메뉴추천">저메추</abbr>
   <abbr title="HyperText Markup Language">HTML</abbr>
  <time datetime="2022-01-02T09:00:00">2022년 1월 2일</time>
  <div>개발자<time datetime="2022-01-02"> 시작일</time></div>
   <div> 정상가: <s>100,000원</s>  할인가: 9,900원</div>
   <small>copyright &copy; 회사명 2025</small>
  <div>저녁은 역시 <mark>치킨</mark></div>

### address 요소(그룹핑 요소)

> 사용자 및 조직, 단체 등의 주소 및 연락처 정보를 마크업 할 때 사용

- 🤖사용 예시
  ```html
  <address>
    <span>(주)야근에서 새벽까지</span>
    <span aria-hidden="true">|</span>
    <span>대표이사 김사장</span> <br />
    <span>ㅇㅇ시 ㅇㅇ구 ㅇㅇ1길 대박타워 13층</span> <br />
    <span>사업자 번호 <span aria-hidden="true">:</span> 000-00-00000</span>
    <span aria-hidden="true">|</span>
    <span
      >문의처
      <a href="mailto:contact@email.com?subject=문의사항">
        contact@email.com
      </a>
    </span>
  </address>
  ```
- ✅출력 결과
  <address>
    <span>(주)야근에서 새벽까지</span>
    <span aria-hidden="true">|</span>
    <span>대표이사 김사장</span> <br />
    <span>ㅇㅇ시 ㅇㅇ구 ㅇㅇ1길 대박타워 13층</span> <br />
    <span>사업자 번호 <span aria-hidden="true">:</span> 000-00-00000</span>
    <span aria-hidden="true">|</span>
    <span
      >문의처
      <a href="mailto:contact@email.com?subject=문의사항">
        contact@email.com
      </a>
    </span>
  </address>

### 이미지, 소스 요소

> `<source>` 태그를 이용하여 화면 사이즈에 따라 보여주는 이미지가 달라지는 반응형 웹 설계할 수 있음

- window.devicePixelRatio \-\> device의 픽셀 밀도를 말함
  \: Css pixel 기존\(1pixel이 점 4개\) vs 레티나\(1pixel이 점 16개\)  
  \: 레티나 디스플레이는 망막으로 볼 수 없을만큼 고밀도의 좋은 화질을 말함  
  ※ 일반 이미지를 사용할 경우 작은 픽셀을 잡아늘리기 때문에
  오히려 화질이 안 좋아 보일 수 있음
- 참고 링크

  - Responsive Web Design // image  
    https://developer.mozilla.org/en-US/docs/Web/HTML/Responsive_images
  - 내 화면 정보 확인  
    https://www.mydevice.io/

- 사용법 : `<img>` 태그 안에 `srcset`속성 추가하여 디바이스 사이즈에 따라 다른 src를 사용하도록 정의  
  &nbsp;&nbsp; ※ `<picture>` 안에 `<source>`1,`<source>`2,`<img>` 등의 여러 대안을 넣는 방식으로도 구현 가능
- 🤖사용 예시
  ```html
  <img
    srcset="
      /src/assets/logo/파일명@1x.png 1x,
      /src/assets/logo/파일명@2x.png 2x
    "
    src="/src/assets/logo/파일명@1x.png"
    alt="로고"
  />
  ```
  ```html
  <!-- picture요소 : 이미지를 담기 위한 컨테이너. picture태그 안에는 반드시 이미지가 있어야 함! -->
  <!-- figure요소와 picture요소는 조금 다름. 
      figure는 이미지를 담기 위한 용도가 아니며 보통 figure 안에 picture 넣고 figcaption에 설명하는 형식으로 사용함 -->
  <!-- srcset 옆에 w는 원본크기 들어가는 것. 기재된 숫자의 +1부터 다음 사이즈 이미지가 적용 됨 -->
  <!-- 100vw <- 100% 같은 것으로 이해 -->
  <picture>
    <source
      srcset="/src/assets/small-550.jpg 550w"
      media="(max-width: 500px)"
    />
    <source
      srcset="/src/assets/medium-1024.jpg 1024w"
      media="(max-width: 768px)"
    />
    <source
      srcset="/src/assets/large-1600.jpg 1600w"
      media="(max-width: 1280px)"
    />
    <img src="/src/assets/normal-1920.jpg" alt="" />
  </picture>
  ```
- 참고사항

  - descriptor \(x\:pixel\(배율\) or w\:width\) \-\> w를 권장
  - sizes \: 기준을 잡아서 일정 사이즈 이상일 때 보여줄 대안을 지정하면 DPR\(Device Pixel Ratio\)에 따라 부르는 이미지가 달라짐
  - 브라우저가 가장 적절한 소스를 가져와서 보여준다.  
    \_ex\_차세대이미지포맷인 webp 이미지를 사용할 때, 구형 브라우저가 웹피를 지원 안 하는 경우를 대비해서 src에 png를 넣고 srcset에 webp를 넣어서 SEO 향상

- 참고 링크
  - Picture 요소에 관한 설명  
    https://developer.mozilla.org/en-US/docs/Web/HTML/Element/picture

### 비디오, 아이프레임 요소

> `<iframe>`태그로 웹 요소\(비디오\) 삽입

- 🤖사용 예시 // 영상 넣기

  ```html
  <!-- ※ allowfullscreen 안 넣으면 전체화면 사용 불가  -->
  <iframe
    width="560"
    height="315"
    src="https://www.youtube.com/embed/Dbml-Ru7hMY?si=tLFAL6arpUVBehf4"
    title="YouTube video player"
    referrerpolicy="strict-origin-when-cross-origin"
    allowfullscreen
  ></iframe>
  ```

### object 요소

> `<object>`을 활용하여 pdf 파일 삽입

- 🤖사용 예시 // pdf파일 넣기
  ```html
  <figure>
    <object
      type="application/pdf"
      data="/src/pdf/파일명.pdf"
      width="600"
      height="400"
    ></object>
    <figcaption>WAI-ARIA</figcaption>
  </figure>
  ```

### image-map 요소

> `<map>`,`<img>`, `<area> `를 결합하여 하나의 이미지에서 여러 포인트를 생성 가능
> 이미지맵(image-map) : 클릭할 수 있는 영역을 가지는 이미지

- 요새는 HTML에서 name보다는 id를 많이 쓰는 추세(Form과는 별도의 이야기)
- 서버가 가지고 있어야 하는 asset의 양/request하는 이미지의 양이 적어서 좋긴 하지만 css에서 더 좋은 기능을 만들 수 있기 때문에 최근에 이미지맵을 많이 쓰지는 않음
- 정의 및 예시 참고링크  
   https://developer.mozilla.org/en-US/docs/Web/HTML/Element/map
- 맵핑을 위한 좌표값(image Map area) 생성 사이트  
   https://www.image-map.net/  
  ※ `a`링크과 결합하여 한 이미지 안에서 어디를 클릭하느냐에 따라 다른 링크로 연결할 수도 있음

- 🤖사용 예시

  ```html
  <img src="/src/assets/이미지명.png" usemap="#image-map" alt="SNS 서비스" />

  <map id="image-map">
    <area
      target="_blank"
      alt="FaceBook"
      href="https://www.facebook.com/"
      coords="15,15,15"
      shape="circle"
    />
    <area
      target="_blank"
      alt="Instagram"
      href="https://www.instagram.com/"
      coords="65,15,15"
      shape="circle"
    />
  </map>
  ```

### 폼(input)요소

> `<Form>` : 다양한 값을 담아서 서버에 submit 할 수 있는 양식

- Form 태그의 속성 중 action은 제출 시에 가야할 곳\, method는 전송 방식으로 get\/post 중 선택
- fieldset은 필수 입력 항목/선택 입력 항목처럼 연관있는 항목끼리 묶어두는 용도로 사용  
  \(HTML5에서는 fieldset+legend 생략하기도 함\(참고로 HTML4는 생략, XHTML는 필수\)\)
- 모든 입력폼(input)은 1대1로 대응하는 label과 한 세트여야 함  
   \: input 외의 태그로 생성한 경우 aria-label 사용해서 입력
- 자주 사용하는 속성
  - `required`: 논리속성. 해당 항목을 필수 입력 항목으로 만들어줌
  - `aria-required`: 스크린 리더가 필수 입력 서식으로 읽어주게 함(div로 만든 경우 꼭 필요)
  - `placeholder`: 입력에 대한 참고사항 안내

## 수업시간에 언급돼서 별도로 찾아서 정리한 내용

### GNB, LNB, SNB

> GNB(Global Navigation Bar)
> LNB(Local Navigation Bar or Left Navigation Bar)
> SNB( Side Navigation Bar)
> --->

### 다양한 방식의 변수명 표기법 \: Naming Rule, Namig Convention

1. camelCase (카멜 표기법)
   - 첫 단어는 소문자로 시작, 이후 단어는 대문자로 구분
   - JavaScript, Java, TypeScript에서 일반적으로 변수명, 함수명에 사용
2. PascalCase (파스칼 표기법)
   - 모든 단어의 첫 글자를 대문자로 시작
   - 클래스명, 생성자 함수명 등에 주로 사용됨
3. snake_case (스네이크 표기법)
   - 모든 글자는 소문자로 작성하며, 언더스코어(\_)로 단어를 구분
   - Python, C 언어에서 주로 사용됨
4. SCREAMING_SNAKE_CASE (대문자 스네이크 표기법)
   - 모든 글자를 대문자로 작성하며, 언더스코어(\_)로 단어를 구분
   - 상수(Constant) 값 정의에 사용됨
5. kebab-case (케밥 표기법)
   - 모든 글자를 소문자로 작성하며, 하이픈(-)으로 단어를 구분
   - HTML, CSS 클래스명, 파일명, URL에서 사용됨
6. Hungarian Notation (헝가리안 표기법)
   - 변수의 타입을 접두사로 명시
   - 과거 C 계열 언어에서 사용되었지만, 최근에는 잘 사용되지 않음
7. UPPERCASE WITH SPACES (대문자 + 공백)
   - SQL에서 사용되는 스타일

<br />
<br />

---

---

# 2025-02-19

**HTML // 다양한 폼(input/button) 요소, select \& textarea 요소, details, summary 요소**  
**CSS // 기초 지식, 연결 방법**

## 수업 내용

### Form (input)

- 폼 받을 수 있는 링크 (가입 필요)
  : https://formspree.io/

- 다양한 폼 예시 링크
  https://www.miketaylr.com/pres/html5/forms2.html

  ```html
  <label>Click me<input /></label>
  ```

- 암묵적 레이블링: 라벨 안에 input 있으면 for 속성이 없어도 암묵적으로 한 세트임을 정의
  : SEO 관점에서는 모호할 수 있으니 지양하는 방식. for/id를 넣는 것을 추천
- jQuery 에서 제공하는 datetime폼 캘린더들 대부분 키보드로 날짜 선택 불가
  SEO 측면에서 네이티브처럼 마우스/키보드 둘 중 하나로도 선택할 수 있도록 보장해야함
- 정규패턴식, 정규식으로 입력 형식 제한 가능

  ```html
  <!-- 10자리 숫자로만 입력 가능 -->
  <input type="text" id="phone" name="phone" pattern="[0-9]{10}" required />
  <!--010-1234-5678 등 하이픈이 들어간 전화번호 형식만 허용 -->
  <input type="text" pattern="[0-9]{3}-[0-9]{4}-[0-9]{4}" />
  <!--최소 10자리 이상 숫자만 허용 -->
  <input type="text" pattern="[0-9]{10,}" />
  ```

- output-> input값을 읽어서 보여주는 태그
  https://developer.mozilla.org/ko/docs/Web/HTML/Element/output

  - 사용 예시
    ```html
    <form oninput="result.value=parseInt(a.value)+parseInt(b.value)">
      <input type="range" id="b" name="b" value="50" /> +
      <input type="number" id="a" name="a" value="10" /> =
      <output name="result" for="a b">60</output>
    </form>
    ```

### Form (button)

### Form (select & textarea)

- sr-only class : 보이진 않으나 스크린리더는 읽어주도록 함
  ```css
  .sr-only {
    position: absolute;
    width: 1px;
    height: 1px;
    padding: 0;
    margin: -1px;
    overflow: hidden;
    clip: rect(0, 0, 0, 0);
    white-space: nowrap;
    border-width: 0;
  }
  ```
- 레이블 없이 만들고싶으면 대신 aria-label 넣어서 설명. 둘 다 할 필요는 없음 택1
- 여러줄 글상자 : textarea
  ```html
  <h2>textarea 요소</h2>
  <form action="/" method="post">
    <div>
      <label for="message"
        >내용
        <span aria-hidden="true">*</span>
        <span class="sr-only">필수</span>
      </label>
      <!-- cols=열의 너비 // rows=행의 개수 -->
      <!-- placeholder에는 긴 내용을 넣으면 안됨! 원한다면 p로 긴 내용 넣었다가 클릭하면 없어지게 하는 식으로 구현 -->
      <textarea
        name="message"
        id="message"
        cols="30"
        rows="10"
        placeholder="이곳에 의견을 적어주세요"
      ></textarea>
    </div>
  </form>
  ```

### dialog 요소, popover 속성

- 팝업 = 모달 윈도우 = 모달창
- 접근성 측면을 고려한 다양한 패턴의 요소들  
  https://www.w3.org/WAI/ARIA/apg/patterns/
- dialog로 만든 모달은 구동을 위해 자바스크립트 필요, 팝오버는 바로 구현 가능(하지만 브라우저 호환성 아직 높지 않음)

### details, summary 요소

- 노션에서 접었다 폈다 하는 그거
  ```html
  <!-- 상세 및 요약 정보 제공 예시-->
  <details>
    <!-- summary 부분만 표시됐다가 ▶ 클릭하면 아래로 상세 내용 펼쳐짐 -->
    <summary>국민 내일배움카드</summary>
    <figure>
      <img src="/src/assets/thumbnail/learn-card.png" alt="" />
    </figure>
    <p>
      급격한 기술 발전 및 노동시장 변화에 대응하는 사회안전망 차원에서 국민
      스스로 직업능력개발훈련을 실시할 수 있도록 훈련비 등을 지원받을 수 있는
      카드를 의미한다.
    </p>
  </details>
  ```

### script 요소

- `<script>` 태그에 js 코드 넣거나 파일을 연결해서 구동
- defer, async 요소// 실행 시 주의
  : html 위에서부터 읽다가 head안에 script가 있으면 그거 쭉 읽고 실행시켜버림  
  -> body에 있는 코드 할 때는 이미 끝난 상태라 실행X
  ===> defer를 속성으로 주거나 or type에 method를 주면 head에 놔도 잘 작동함

※ gitHub setting-copilot 시작, VSC extension도 설치

**===HTML 진도 끝===**

**===CSS 진도 시작===**

### CSS(Cascading Style Sheet)란?

> 마크업 언어가 실제로 표시되는 방법을 기술하는 언어로 W3C 표준
>
> - 1996년 W3C 주도 하에 CSS Level1 발표 // A4 한장만큼 빈약했음
> - 1998년에 CSS Level2 등장 : 버그 수정된 2.1이 널리 쓰여짐
> - Level3은 모듈 단위로 돌아감

- CSS3 모듈들 status & 웹 기술의 공식적인 기술명세서 링크
  https://www.w3.org/Style/CSS/Overview.en.html  
  ※ WD > CR > PR > REC의 순서로 표준 확정

  1. Working Draft (WD:초안)
  2. Candidate Recommendation (CR:권고안후보)
  3. Proposed Recommendation (PR:제안권고안)
  4. Recommendation (REC:표준화)

- CSS의 표시 정도 : 브라우저 별로 css 보여주는 정도 상이  
  https://css3test.com/

- CSS 사용의 의의 : 문서의 구조와 표현을 분리 -> 컴포넌트화  
  https://csszengarden.com/ // 동일한 html문서에 다양한 css를 입혀서 볼 수 있음

### CSS Syntax (구문)

- 선택자(Selector)와 선언부(Declasration Block) 로 이루어지며 선언부는 속성(property)와 속성 값(value)로 이루어짐
- 세미콜론(;)으로 속성과 속성 값을 구분해서 여러 개의 선언(declaration) 지정 가능
- CSS 적용 방법 3가지

  1.  external style sheet -> css 파일 별도로 만들어서 link요소로 HTML 문서에 연결
  2.  Embedded Style Sheet -> head 태그 안에 style 태그로 감싸서 스타일 선언
  3.  Inline Style Sheet -> 각각의 요소에 style 속성 부여해서 선언  
      ※ Inline이 우선순위 높으나 유지보수 빡셈 => 지양

- DOM Tree + CSSOM => Render Tree
- CSS 단위 (일단 자주 쓰이는 것만 써봄)
  - rem
  - vw -> 뷰포트 기준
  - % -> 컨테이너 기준(부모)
  - vh
  - px
- 색깔 형식
  - rgba -> Red, Green, Blue + 4번째 값은 투명도
  - HSLA-> 색상, 채도, 명도, 투명도

※ 무료 코파일럿 // 한달에 질문 50개, 코드 2000개

<br />
<br />

---

---

# 2025-02-20

**CSS // 선택자, 상속, 단위**

## 수업 내용

### CSS Selector (선택자)

> CSS에서 스타일을 지정할 웹 페이지의 HTML 요소를 대상으로 선택할 때 사용

- 다양한 Selector

  - 태그 선택자: `p`,`a` 등 일반적인 태그를 선택하는 것
    ```css
    /* 해당 태그 안에 들어간 모든 요소에 적용됨(=상속) */
    body {
      color: red;
    }
    ```
  - 클래스 선택자 : `.` \+ 클래스명

    ```css
    /* 클래스가 일반 태그보다 우선시 됨 + !important하면 우선순위 짱짱됨 */
    /* important는 흔히 쓰진 않고 동적으로 적용시킬 때 주로 사용 */
    .like {
      color: green;
    }
    /* 이것도 동일하긴 함(손 많이 가서 위처럼 사용) */
    [class='like'] {
      color: green;
    }
    ```

  - 아이디 선택자 : `#` \+ id
    ```css
    #lion {
      color: plum;
    }
    /* 이것도 동일하긴 함(손 많이 가서 위처럼 사용) */
    [id='lion'] {
      color: green;
    }
    ```
  - 속성 선택자 : `[]`로 속성을 감쌈
    ```css
    [title] {
      color: blueviolet;
    }
    /* 이런 식으로 특정 속성이 특정한 값을 가진 것만 잡을 수도 있음 */
    [title='lion'] {
      color: green;
    }
    /* ^= -> ""로 시작하는 것  */
    a[href^='https'] {
      text-decoration: none;
    }
    /* ^= -> ""로 끝나는 것  */
    a[href$='pdf'] {
      background-color: violet;
    }
    ```
  - 가상 요소 선택자 : 태그 \+ `:`뒤에 정해진 명령어를 붙임

    ```css
    /* ▼ 한 번도 방문하지 않으면 */
    a:link {
      color: green;
      background-color: red;
    }

    /* ▼ 방문한 이후에는 이 양식 적용 */
    a:visited {
      color: olive;
      background-color: aqua;
    }

    /* ▼ 마우스 올렸을 때 */
    a:hover {
      color: yellow;
    }
    /* ▼ tab 등으로 포커싱 됐을 때 */
    a:focus {
      color: red;
    }
    /* ▼ 작동할 때(눌릴 때) */
    a:active {
      color: chartreuse;
      background-color: #000;
    }
    ```

  - 가상 클래스 선택자 : 태그 \+ `::`뒤에 정해진 명령어를 붙임

    ```css
    /* 가상 요소 선택자 중 before, after는 반드시 content를 가져야 함 */
    h1::before {
      content: '멋있는 사나이';
    }

    h1::after {
      content: '많고많지만';
    }
    ```

  - 전체 선택자(유니버셜 셀렉터) : `*` \/\/ 모든 걸 선택\: 보통 초기화 할 때 사용

    ```css
    /* 가상 요소 선택자 중 before, after는 반드시 content를 가져야 함 */
    * {
      margin: 0;
    }

    /* 이런 식으로 특정 태그 안의 모든 걸 선택하기도 함 */
    body * {
      color: red;
    }
    ```

  **※ `<a>`의 밑줄처럼 기본적인 요소를 없애고 싶을 때 : text-decoration none으로 설정**

  ```css
  /* 가상 요소 선택자 중 before, after는 반드시 content를 가져야 함 */
  a {
    text-decoration: none;
  }
  ```

- 참고 링크  
  https://developer.mozilla.org/ko/docs/Web/CSS/Attribute_selectors
- css에서 `&` 사용 관련
  https://frontendmasters.com/blog/three-approaches-to-the-ampersand-selector-in-css/

<br />

### CSS 상속, 겹침, 우선순위

**상속이란?**

> 상속(Inheritance)이란 상위(부모, 조상) 요소에 적용된 프로퍼티를 하위(자식, 자손) 요소가 물려 받는 것을 의미. 상속 기능이 없다면 각 요소의 Rule set에 프로퍼티를 매번 각각 지정해야 함  
> 한 CSS 파일 내에서 선택자가 겹쳤다면(Cascade) 나중에(=아랫쪽에) 선언한 사항이 우선시하여 적용됨  
> 우선순위 한줄 요약 (더 복잡하지만..요약에 의의)  
> : !important >>> inline >>> id선택자 >>> class명 >>> HTML 태그명 >>> DOM구조의 상위 상속

**※ 현재 페이지에 적용된 스타일 보기**

- 웹페이지에 적용되는 스타일시트의 종류 (개발자도구(F12)에서 Styles로 확인 가능)
  - user agent stylesheet `->` 웹 브라우저에서 기본스타일을 제공하는 스타일시트
  - author stylesheet `->` 개발자가 작성한 내용을 적용하는 스타일시트
  - user Stylesheet `->` 사용자가 설정한 내용을 적용하는 스타일시트

**※ Font 관련 속성**

- font-family에 기재한 순서대로 표시가능한 폰트를 찾아서 보여줌
  마지막에는 generic-family를 넣음  
  **※ Generic-family**
  - CSS에서 글꼴을 그룹화한 최상위 카테고리
  - serif, sans-serif, monospace, cursive, fantasy 등등

### CSS 단위

- CSS 에서 사용되는 em\/rem의 정의

  - em \: 부모요소의 폰트 사이즈에 따라 결정
  - rem \: root의 폰트 사이즈에 따라 결정  
    ※ 기본 body의 폰트 크기 \: 16px

- CSS 값과 단위 참고 링크
  https://developer.mozilla.org/ko/docs/Learn_web_development/Core/Styling_basics/Values_and_units

**※ 웹폰트 가져다 쓰기**

- 폰트를 CDN으로 가져와서 쓰기 : pretendard/suit CMD로 글꼴 적용함
  https://github.com/orioncactus/pretendard
- html기본세트 스니펫 등록
- @font-face // @(앳)사인 규칙
- font 기본 font-weight는 4(400). 100~900으로 쓸 수 있음

## 수업 중 언급돼서 따로 찾아본 내용

- favicon
  - 웹사이트 또는 웹 페이지를 대표하기 위해 웹 브라우저에서 사용되는 16x16 픽셀의 작은 이미지(title 옆에 들어감)
  - 즐겨찾기 아이콘(favorite icon)의 줄임말
  - 초기에는 ICO형식 이미지를 사용하였으나 근래에는 png,JPEG // SVG를 흔히 사용함
  - SVG 외의 이미지 사용 시 다양한 사이즈가 필요
    - 16x16: 브라우저용
    - 32x32: 작업표시줄 단축키용
    - 96x96: 데스크탑 단축키용
    - 180x180: 애플 터치용
  - ico/svg 둘 다 두면 svg 지원 안 하는 브라우저에서 ico 보여줌!
  - 사용예
    ```html
    <link
      rel="shortcut icon"
      href="/src/assets/favicon/likelion.ico"
      type="image/x-icon"
    />
    ```
- saas // 회고조 참고
- & has (checked) <- css에서 쓰이는 형태 참고
  https://frontendmasters.com/blog/three-approaches-to-the-ampersand-selector-in-css/
- crossorigin
- dvw, dvh, lvh, svh

## 과제 관련 안내

1.  **degit 설치**  
    likelion-bootcamp 폴더에서 `$npm i -g degit` 명령어 실행
2.  **강사님 gitHub-resources-figma 폴더만 가져오기**  
     `$degit seulbinim/resources/figma figma`  
     (아이디 폴더명)  
    **--> 이렇게 degit으로 가져오면 git연결할 필요 없이, 리포지토리 통째로 당겨올 필요 없이 필요한 폴더만 가져올 수 있음!!**

<br />
<br />

---

---

# 2025-02-21

**CSS // 박스 모델, 리셋, 네스팅, 포지션**

## 수업 내용

> ※ 웹 페이지 안에서 드래그했을 때 이미지가 잡히면 실제 컨텐츠, 텍스트인데 안 잡히면 가상 요소 컨텐츠일 가능성이 높다.
> 육안으로만 확인하지 말고 항상 개발자도구로 확인하는 습관을 기를 것

### Atomic Design (Methodology)

### CSS 박스 모델

- 모든 HTML 요소를 포함하는 상자
- 패딩과 마진
  - `padding` : border를 기준으로 안쪽 여백
  - `margin` : border를 기준으로 바깥쪽 여백
- **Display** : 화면에 들어가는 방식 결정  
   flex, inline-flex, grid, inline-grid, table, table-row, flow-root(니가 flow의 root야~) inline-block(inline인데 공간 부족하면 다음줄로 가는 아이, inline은 공간 부족하면 쪼개짐!)등등
- Float요소는 다른 요소들을 밀어냄!
- BFC(Block Formatting Context) <- IFC(Inline Formatting~)
- span과 같은 inline 요소는 weight/height 적용되지 않음
  : inline 상자의 높이는 line-height의 영향을 받음

### CSS Reset

- Reset/Normalize 참고 링크
  https://brunch.co.kr/@euid/2
  - CSS Reset : 다양한 브라우저의 기본 스타일을 초기화
  - CSS Normalize : 일관되지 않은 스타일만 제거. 가능한 기본스타일 유지  
    => 섞어서 쓰기도 함
- 다양한 리셋

  - 에릭마이어 리셋
    https://meyerweb.com/eric/tools/css/reset/
  - 모던리셋
    https://www.joshwcomeau.com/css/custom-css-reset/
  - 미니리셋 : 최소한의 사항 리셋  
    https://jgthms.com/minireset.css/
  - Normalize
    https://necolas.github.io/normalize.css/

- 리셋/노멀라이즈 요소들
  - 현대에서는 모든 요소의 box-sizing을 border-box로 지정해서 씀
  - 모든 margin 0, line-height는 1.5로 지정함(:가독성 가장 좋음)  
    ※ line-height:1 일 때 한글은 폰트에 따라 위가 짤림(ㅊ->ㅈ)
    요새는 1.15가 유행하는 추세라고 함
  - font-smoothing: antialiased -> 글자 각 둥글어져서 보기 편함
  - img, picture, video... block으로 바꿈
  - isolation(격리) -> 루트나 \_\_next 는 isolate를 쓰겟다

### 실습

- figma 시안 보고 css 맞추기
- html에서 enter, tab 등 공백을 인식해서 a 태그 사이에 틈 생김
  -> 부모요소에 font-size를 0으로 두고 상속시켜서 공백문자가 크기를 갖지 않도록 하고 자식 요소에 폰트 크기 지정해서 해결하기도 함

### CSS nesting

- 내용 참고 MDN 링크
  https://developer.mozilla.org/ko/docs/Web/CSS/CSS_nesting/Using_CSS_nesting
- BEM방식(벰방식)-> `ㅇㅇ**ㅇㅇ` 요렇게 쓰는 거 (SASS 방식)에서 많이 씀
  네스팅 시 부모요소 생략하고 `&**list` -> 컴파일하면 `부모\_\_list`일케 되는 것

### CSS Position

- `position`속성 : 기본값은 모두 static
- 개발자도구 computed 에서 확인했을 때 기울어진 글자로 표시되는 속성
  -> 내가 설정 안했는데 적용된 사항  
  똑바로 선 글자로 표시되는 속성 -> 내가 설정한 사항

- position:absolute 하는 순간 블록 요소로 인식 됨
- **BFC** : Block formatting context

  > CSS에서 블록 레벨 요소가 레이아웃을 결정하는 독립적인 영역을 형성하는 개념 -> 특정 요소 내부에서 블록 레벨의 배치 규칙이 독립적으로 적용되는 "상자"를 만드는 것

  https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_display/Block_formatting_context

<br />
<br />

---

---

# 2025-02-24

**CSS // CSS 변수, CSS 배경**

## 수업 내용

### 3주차 과제 피드백

- 수업 시간에는 절대경로 쓰고 있지만 gitHub 배포 시 상대경로 사용해야 함
  과제 파일은 상대경로로 고쳐두도록 권유
- 버셀(Vercel) : 서버리스 플랫폼(react용)

### CSS 변수

- https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_cascading_variables/Using_CSS_custom_properties
- 예전에는 CSS에 변수라는 개념이 없었음. Sass(전처리)는 지원해서 인기 많았음(@mixin)
  -> Sass에 비해 사용패턴이 어렵지만 이제는 CSS도 변수 사용 가능
  - Sass는 $~~ 형태로 변수 선언, CSS는 $가 아닌 --를 사용
  - CSS 변수 사용 시 JS를 통해 동적으로 값을 변경 가능
- 기재하는 모양이 속성(property) 같아서 Custom Property라고도 부름
- 형태 : var(--변수명) 요렇게 부른다 var함수 없이 못부름
- ```css
  /* 전역 변수 정의(global variable) */
  /* at 규칙(@) 사용해서 porperty 정의 */
  /* 내가 설정하는 커스텀 프로퍼티의 상속여부 결정(inherit) */
  @property --text-color {
    syntax: '<color>';
    inherits: false;
    initial-value: orange;
  }

  /* 커스텀 프로퍼티 : --로 시작 */
  /* root에 색상 크기 등 정의해놓고 불러서 쓰는 방식 많이 사용 */
  :root {
    --orange: rgb(255, 204, 108);
  }
  /* ※ 전역 변수보다 지역 변수가 우선순위가 높음 */
  .text-card {
    --bg-color: var(--orange);
    /* 만약 변수가 없을 시 적용 될 2순위 색 지정 가능 -> fallback */
    p {
      background-color: var(--bg-color, #2ecc71);
    }
  }
  ```

- 폴백 : var(--~~,대체할 속성값) 요렇게 하면 플랜B. 즉 대안을 지정해둘 수 있음
- class 안에서 정의한 경우 지역 변수: 그 안에서만 쓸 수 있음
- sass는 중간에 루트를 다시 선언하면 그 위는 최상위 루트대로, 그 아래는 바뀐 걸로 적용되지만 CSS는 나중에 선언된 값으로 통일해서 적용됨

### CSS 배경

**※ hsl : hue(색상/0~360), saturation(채도/%), lightness(밝기/%)**
ㄴ 채도랑 밝기는 .6 이런 식으로도 기재 가능

- background-image: 선택자의 사이즈를 계산한 후 해당 영역에 반복해서 이미지를 출력함.
  영역이 이미지보다 작은 경우 원본 이미지의 일부만 보이고 반복출력X
  -> 영역에 맞춰서 1개만 딱 나오는 img(컨텐츠이미지)와는 다르다
  // background-repeat 속성으로 반복여부 결정 가능

- background-attachment 속성으로 스크롤을 따라올 지, 고정되어 있을 지 결정

  - 스크롤 참고 링크
    1.  https://blog.logrocket.com/create-parallax-scrolling-css/
        parallax scrolling
    2.  https://www.w3schools.com/howto/howto_css_parallax.asp

- 사용 예시, 관련 속성
  ```CSS
  body {
  /* 배경 색상 */
  background-color: hsl(180, 50%, 80%);
  /* 배경 이미지 */
  background-image: url(/src/assets/images/rabbit.png);
  /* 배경이미지 반복 설정 가능. 이니셜 값은 repeat */
  background-repeat: no-repeat;
  /* 배경 이미지 위치 (일반 position이랑은 상관 없음)_ 단축표기법(shorthand) 사용)*/
  /* px,rem 등의 단위를 썼을 때는 왼쪽 상단 꼭지점 기준으로 맞춰지고 %로 지정 시 상자의 해당 지정과 이미지의 해당지점을 기준으로 맞춰짐 */
  background-position: 50% 0;
  /* body 요소의 최소 높이 지정 */
  min-height: 100vh;
  /* 스크롤했을 때 따라올 지, 고정되어있을 지 */
  background-attachment: fixed;
  /* cover(가로 보존)/contain(세로 보존) 바로 사이즈 지정할 수도 있음 가로 세로*/
  background-size: 200px 300px;
  /* 단축표기법으로 줄여서 선언 */
  /* 배경이미지는 먼저 선언한 게 앞으로 나옴. 나중에 선언할 수록 밑에(뒤에) 쌓임. - 본문 position이랑은 반대 */
  background:
    url(/src/assets/images/cloud.png) no-repeat 0 100px fixed,
    url(/src/assets/images/sun.png) no-repeat 150px 50px /150px 150px fixed,
    url(/src/test_img/precious.png) no-repeat 500px 300px /200px 200px,
    url(/src/test_img/surprised_y.png) no-repeat 500px 300px /200px 200px fixed,
    url(/src/test_img/precious.png) no-repeat 100px 300px /200px 200px fixed,
    url(/src/test_img/smile_y.png) no-repeat 100px 300px /200px 200px fixed,
    linear-gradient(red, green),
    pink;
  }
  ```
  **※ 대부분 요소의 이니셜 box-siziing 은 content-box인데 버튼은 border-box임**

## 수업시간에 언급된, 찾아볼 내용

- : 가상 클래스 (pseud-class=슈도 클래스=의사 클래스) // :: 가상 요소
- 린트 (Lint: 오래된 스웨터의 보푸라기 같은 것을 부르는 말)
  :보푸라기를 제거하는 린트 롤러(Lint roller)처럼 코드의 오류나 버그, 스타일 따위를 점검하는 것을 린트(Lint) 혹은 린터(Linter)라고 부름. 이를 통해 문법 오류를 잡아내고 규칙(코딩컨벤션)에 맞게 수정도 가능
  -> 코드의 가독성을 높이는 것 뿐만 아니라 동적 언어의 특성인 런타임 버그를 예방하는 역할을 함

<br />
<br />

---

---

# 2025-02-25

**CSS // CSS Float**

## 수업 내용

### Notification = toast UI = 스낵바 (카톡처럼 뿅 나왔다 사라지는 알림)

- WAI-ARIA 실무 적용 사례 참고 링크
  https://aoa.gitbook.io/skymimo/aoa-2023/ui-aria-2022-2024/snack-bar
- 브라우저별 적용 가능 여부 확인 링크 (can I use)
  https://caniuse.com/

### CSS Float

- Float을 실무에서 좋아하진 않나봄 flex 쓰지 float 안 쓴다는 사람이 많은가봉가
- 텍스트의 공간

  - 인라인에서 텍스트 배치영역의 위아래 공백을 하프리딩(half-leading)이라고 부름
  - top line / base line(※text가 맞춰지는 부분) / bottom line
  - descender/ascender (위아래여백) 글꼴에 따라 다르고 요 부분 때문에 여백이 살작 뜨기도 함

- Float 이해를 돕는 영상
  https://www.youtube.com/watch?v=xara4Z1b18I&t=83s
- CSS로 심슨 그려둔 사이트
  https://pattle.github.io/simpsons-in-css/
- 다양한 CSS 활용 볼 수 있는 사이트
  https://freefrontend.com/css-shape-outside-examples/

- 실습 // 04
  **HTML에서 태그에 hidden속성 = CSS의 display:none 요소를 보이지 않게 설정(DOM Tree에서도 보이지 않게 됨)**
  - overflow
    컨텐츠의 크기가 부모보다 클 때 어떻게 할 것인가?
    - 기본값은 visible(부모 요소 밖까지 넘어가서 보임)
    - hidden(넘어가면 안 보임) scroll(스크롤 생김) auto(컨텐츠 양에 따라 스크롤 유무 결정)
  - display: flow-root 하면 자식 요소에 float가 들어가더라도 normal flow에 자식 요소의 width값과 height값이 남아있는 것처럼 보이게 함
  - img{vertical-align}
    -> 요소들의 정렬 기준 지정. baseline/top/middle/bottom/% 줄 수 있음. 이 속성은 인라인이나 인라인 블록에만 먹힘. 자식요소한테 직접 주면 됨
  - clear: both -> float의 효과를 해제하기 위해 사용할 수 있음. block요소에만 사용 가능

**※em은 해당 요소의 글자크기를 1em으로 지정 <- 상속 이슈 있어서 font size 안 주면 혼란할 수 있음. 참고로 rem는 root 기준**

**※border-radius 각각의 각도(4군데)를 지정할 수도 있음**

```CSS
  border-radius: 0 50px 0 50px / 0 20px 0 20px;
```

**※특정 클래스에서 lang이 en인 것만 잡기**

```CSS
  .subject {
      &[lang='en'] {
        font-size: 0.5em;
      }
    }
```

## 수업시간에 언급된, 찾아본 내용

- **shape-outside** : 이미지 모양 다듬을 수 있음. Float 개체에만 적용 가능
  ```CSS
  .float-shape {
    float: left; /* 반드시 float을 설정해야 함 */
    width: 150px;
    height: 150px;
    shape-outside: circle(); /* 원형 모양으로 텍스트 흐름 조정 */
    clip-path: circle(); /* 요소 자체도 원형으로 자름 */
  }
  ```
- **aspect-ratio** : 가로 세로 비율 1대 1로 맞춰줌. 이미지에 직접 주는 속성
- **object-fit** : 영역 안에 이미지를 표시하는 방식 정의.
  - fill(초기값)은 비율을 무시하고 꽉 채움
  - contain은 이미지를 깨뜨리지 않으면서 전체가 보이게 표시하고 /
  - cover는 이미지가 깨지지는 않으나 한쪽 축에 꽉맞게 확대되어 보임 /
  - none은 이미지의 원래 크기로 나옴
  - scale-down은 contain과 none 중 더 작은 크기로 나타남

<br />
<br />

---

---

# 2025-02-26

**CSS // 미디어쿼리, 반응형 레이아웃**

## 수업 내용

### UI 실습 : 아바타 프로젝트/아바타 리스트

- `a11y.css` 생성해서 `sr-only` 클래스 등록, `@import`해서 사용
- 반응형 레이아웃 구현 시, inherit보다는 `%`를 주로 사용
- 큰 글자와 작은 글자를 한 줄에 쓸 때 align 안 맞으면 `line-height`를 숫자로 고정시켜서 정리 가능
- 요소를 `inline-block`으로 정렬하는 것과 요소에 `float:left`를 주고 부모에 `display:flow-root`를 주는 건 보기에 동일한 효과

### CSS 미디어 쿼리

> - 전체 뷰포트(Viewport) 크기를 기준으로 스타일을 적용
> - 화면의 가로/세로 크기, 해상도, 색상 모드 등의 속성을 기반으로 스타일을 변경
> - 반응형 디자인(Responsive Design)을 구현할 때 주로 사용
> - 컨테이너 쿼리는 부모 요소(컨테이너)의 크기를 기준으로 스타일을 적용

**-> 미디어 쿼리는 전체 페이지의 레이아웃을 변경해야 할 때 유용하고,**  
&nbsp;&nbsp;&nbsp; **컨테이너 쿼리는 개별 컴포넌트의 크기에 따라 스타일을 조정할 때 유용함**

- 유연한 반응형 디자인을 할 수 있게 해주는 기능
- `<style>` 태그에 `media` 속성값은 `screen`과`print` 2가지로 각각 스타일을 넣어서 2벌 만들면 프린트용 스타일 따로 지정해줄 수 있다
- html에서 `<link>`태그로 부르는 것과 css에서 `@import`로 연결하는 것의 차이
  - **`<link>`** : 병렬로 한 번에 요청, 먼저 오는 게 먼저 보여짐
  - **`@import`**: 직렬로 요청, 하나 요청-로딩 되면 다음 거 요청-로딩하는 방식  
    -> 여러개 부르면 요청이 많아져서 효율 좋지 않다  
    **=> 하나의 CSS 안에 다 몰아넣는 것이 효율적**

**※ Sass에서는 `*`가 파일명 앞에 붙어있는 파일은 컴파일하지 않음=CSS파일로 만들지 않음**

> 다만 scss파일 안에서 @user를 통해 \*가 붙은 파일을 불러서 씀  
> => 컴파일하면 css안에 전부 다 들어와있는 결과물 받게 됨

- `<meta>` 태그 // 반응형이 작동하려면 `viewport`가 명시된 `<meta>` 태그가 반드시 필요 함.
  - **viewport**: 서비스를 표시하고 있는 화면(device) 사이즈
- 반응형 구현 시, px 등 고정형 단위를 사용하지 않고 `em``rem``%`` vw` 등의 비율형 사이즈 단위를 쓰는 것을 권장
- 디자인 순서는 `모바일 -> 타블렛 -> 웹` 으로 하는 것이 보편적  
  마크업 할 때는 위에서 아래로~ 왼쪽에서 오른쪽으로 접근
- 여러가지 함수들

  - min & max 함수

    - `min()` 함수: 여러 값 중 가장 작은 값 선택
    - `max()` 함수: 여러 값 중 가장 큰 값 선택

      |  비교 항목  |                        `min()`                        |                     `max()`                     |
      | :---------: | :---------------------------------------------------: | :---------------------------------------------: |
      |    역할     |                   가장 작은 값 선택                   |                 가장 큰 값 선택                 |
      |  적용 예시  | `width: min(50%, 600px);`<br> → 최대 600px까지만 설정 | `width: max(50%, 300px);`<br> → 최소 300px 유지 |
      | 주요 사용처 |                    최대 크기 제한                     |                 최소 크기 보장                  |

    - 사용 예시

    ```CSS
      /* 조건에 and 연산자도 사용 가능 */
      @media (min-width: 600px) and (max-width: 800px) {
      }
    ```

- `clamp(min, preferred, max)` 함수
  - 최소값, 기본값, 최대값을 조합해서 더 유연하게 크기를 조정 // min과 max를 조합한 형태
    https://developer.mozilla.org/en-US/docs/Web/CSS/clamp
- `calc()` 함수 : 나누기 더하기 등 연산 필요할 때 사용

### 반응형 레이아웃 (Responsive-Layout)

- 모바일/태블릿/데스크탑 각각의 환경에 맞는 레이아웃 구현

**※ 포트포워딩으로 외부 접속포인트 만들기**

1. vsc에서 ports 탭 open
2. `Forward a port` 클릭하고 원하는 포트(3000) 등록
3. 제공되는 주소로 모바일에서/ 혹은 외부에서 접속 가능

**※ 이미지 변환 패키지**

1. npm 사이트에서 simple-webp-converter 등 검색, 명령어로 패키지 설치
   `npm i simple-webp-converter --save-dev`
2. package.json에 명령어 등록 (파일 선택 옵션 포함)
   https://www.npmjs.com/package/simple-webp-converter
3. 실행 후 파일 용량 확인

## 수업시간에 언급된, 찾아본 내용

- **적응형 웹디자인(AWD)과 반응형 웹 디자인(RWD)**
  - Adaptive Web Design (AWD) → 여러 개의 고정된 레이아웃 중 하나를 선택하여 제공
  - Responsive Web Design (RWD) → 하나의 유동적인 레이아웃을 CSS로 조정

<br />
<br />

---

---

# 2025-02-27

**CSS // Logical Properties, FlexBox, Table**
**Git tag**

## 수업 내용

### Logical Properties (논리속성)

> CSS의 논리 속성은 물리적 방향(예: left, right, top, bottom) 대신 문서의 글쓰기 방향(writing mode) 을 기반으로 요소의 스타일을 지정할 수 있도록 해주는 속성  
> 다국어 지원 및 다양한 레이아웃을 고려할 때 유용  
> CSS 논리 속성에서는 요소의 배치를 블록(Block) 과 인라인(Inline) 방향으로 나눔
>
> - **Block 방향**: 문서의 주요 흐름(수직 방향, 예: top → bottom)
> - **Inline 방향**: 텍스트가 흐르는 방향(수평 방향, 예: left → right)

```CSS
  writing-mode: vertical-lr;

/* float: left 속성을 논리 속성으로 지정 */
float: inline-start;

/* 가로 크기를 width 속성이 아닌 논리 속성으로 지정 */
inline-size: 400px;
/* 세로 크기를 height 속성이 아닌 논리 속성으로 지정 */
block-size: 100px;
overflow: auto;
/* padding-left, padding-right 속성을 논리 속성으로 지정 */
padding-inline-start: 20px;
padding-inline-end: 50px;

/* 상하, 좌우를 한 번에 논리 속성으로 지정 */
padding-inline: 20px;
padding-block: 10px;
margin-inline: 30px;
margin-block: 50px;

/* position의 offset을 지정할 때 논리 속성을 사용한 경우 */
.example {
  position: absolute; /* 변경 없음 */
  inset-block-start: 0; /* top: 0; */
  inset-inline-start: 0; /* left: 0; */
  inset-inline-end: 0; /* right: 0; */
  inset-block-end: 0; /* bottom: 0; */
}

/* position의 offset을 지정할 때 논리 속성 중 단축 표기법을 사용한 경우 */
.example {
  position: absolute; /* 변경 없음 */
  inset: 0;
}
```

- `currentColor` 속성값 : 현재 글자색과 같은 색
  : outline/ghost button(=fill 없이 테두리와 글자만 있는 버튼) 만들 때 사용하기 좋다

- `writing-mode`

  > `writing-mode`는 텍스트의 **쓰기 방향(글자 흐름)**을 결정하는 CSS 속성으로 가로쓰기(LTR, RTL) 또는 세로쓰기(수직, 혼합) 를 제어함

  - https://developer.mozilla.org/en-US/docs/Web/CSS/writing-mode

  ```CSS
  /* Keyword values */
  writing-mode: horizontal-tb;
  writing-mode: vertical-rl;
  writing-mode: vertical-lr;
  writing-mode: sideways-rl;
  writing-mode: sideways-lr;

  /* Global values */
  writing-mode: inherit;
  writing-mode: initial;
  writing-mode: revert;
  writing-mode: revert-layer;
  writing-mode: unset;
  ```

### FlexBox(플렉스박스)

> `Flexbox`는 CSS에서 요소들을 효율적으로 정렬하고 배치할 수 있도록 도와주는 1차원 레이아웃 시스템으로, 부모 요소를 flex container(플렉스 컨테이너)로 설정하면 자식 요소인 flex items(플렉스 아이템)들이 유연하게 배치 됨

- `display`: `flex` or `inline-flex`
- 연관 속성들 참고 링크
  https://css-tricks.com/snippets/css/a-guide-to-flexbox/
- `flex-direction`는 4가지 속성값 가짐
  - `column` / `column-reverse` / `row`(default) / `row-reverse`
    <img src="src/test_img/flex_axis.svg">
- `flex-flow`: `flex-direction` + `flex-wrap` 숏핸드 표기
- `flex-wrap: nowrap;` // 줄바꿈 설정-shrink 동작 여부 결정 (nowrap->줄바꿈 ㄴㄴ)
- `justify-content` 속성값 중 사이공백 관련 값 3개 정리
  1. space-between(바깥에는 여백x 안쪽 동일 여백)
  2. space-around(안쪽 여백의 반만큼 양 바깥쪽에 여백 줌)
  3. space-evenly(안쪽 여백만큼 양 바깥쪽에 여백 줌)
- `align-items` initial value: `stretch`(=박스에 맞게 늘어남)
- `align-content` // 세로 가운데 정렬  
  작년에 생긴 기능! flex안에서 뿐만 아니라 normal 컨텐트에서도 사용 가능.

- flex 컨테이너는 `"직계 자식"`에만 영향을 줄 수 있음!
- 중간에 낀 컨테이너에`display: contents;`를 주면 **contents**로 인식되면서 조부모가 직계를 무시하고 조손에 영향을 줌

- `flex-flow` : `flex-direction`: + `flex-wrap` **숏핸드 표기**
  ※ 선생님은 `display flex 할 떄 꼭 같이 써준다 함 (개인자유)
- **justify contents**: 주축 방향 정렬
- **align-items**: 교차축 방향 정렬
  => flex-direction 에 따라 x축/y축이 바뀔 수 있기 때문에 가로/세로 아님

- flex box를 사용해서 만들 수 있는 디자인들 링크
  https://d2.naver.com/helloworld/8540176

- ` order` 속성으로 아이템의 순서 변경 가능!

```CSS
    /* odd(홀수), even(짝수) 값을 줘서 일부만 부르고 앞당기기*/
    /* 모든 flex 아이템의 기본 order는 0번.
    내 자리: 0인 것// 같은 0번일 때는 마크업 순서대로 나오고, 하나가 -1이 되면 맨앞으로 가는 것! */
  &:nth-child(even) {
    order: -1;
    }
```

- `flex-grow`(자동커짐)/ `flex-shrink`(자동줄임) / `flex-basis`(원래크기) 3가지 같이 공부해야 이해 됨
  https://developer.mozilla.org/ko/docs/Web/CSS/flex-basis

```CSS
    /* flex-box의 기본 크기 */
    /* flex-flow가 row일 떄는 width, inline-size처럼 작용하고
    columns일 때는 height, block-size처럼 작용함 */
    /* ※ auto 값을 가지지 않은 flex-basis와 width(flex-direction: column인 경우 height) 값을 동시에 적용한 경우, flex-basis가 우선함!!
      -> flex-basis는 강하다. 일찐이다 */
    /* flex-basis가 content일때: 내용물만큼의 폭을 가짐*/
    flex-basis: 200px;
    /* flex-grow에 1을 주면 전체 부모공간을 꽉 채움. 디폴트는 0 */
    flex-grow: 0;
    /* 공간이 모자르면 알아서 줄이는 것. 디폴트는 1 */
    flex-shrink: 1;

    /* grow, shrink, basis 단축표기 */
    flex: 0 1 200px;

```

※ spandml initial display는 inline, initial position은 static
**※ Emmet 사용해서 여러 요소 한 번에 생성하기 예시**

- div.item$\*3{자식요소}
- .item$\*4{자식요소$} ()

**※ CSS 문법 : 포함 요소**

- ` [class*='item'] {}` -> class명에 item 포함하는 요소
- ` [class^='item'] {}` -> class명이 item으로 시작하는 요소

### Table 테이블 // Position:sticky

- 백분율은 항상 자신의 컨테이닝 블록 기준으로 적용
- 테이블 deprecatied된 html design이 많다. css에서 적용할 것을 권장
  참고링크 : https://developer.mozilla.org/en-US/docs/Web/HTML/Element/table
- 테이블 테두리 합치는 속성 ` border-collapse: collapse;`
- 테이블 테두리 간격 없애는 속성 `border-spacing: 0;`
- `position: fixed;`는 뷰포트 기준으로 작동
- `position: sticky;` 는 부모기준으로 작동

### Git 실습 // git tag

**local 관련 명령어**

- `git tag v1.0.0` // 마지막 커밋에 버전 추가!
- `git tag` // 명령어로 현재 버전을 볼 수 있음
- `git tag -d v1.0.0` // 해당 버전 태그를 삭제
- `git tag -a v1.0.0 -m "첫 번째 릴리즈 버전" HEAD~2` // 특정 커밋에 버전을 부여
- `git show v1.0.0` // 태그 세부사항 보여줌
- `git checkout v1.0.0` // 그 버전으로 바로 갈 수 있음

**remote 관련 명령어**

- `git push origin 태그이름` // 특정 태그만 리모트 저장소로 전송
- `git push origin --tags` // 모든 태그를 리모트 저장소로 전송
- `git push --delete origin 태그이름` // 리모트 저장소의 특정 태그를 삭제
- `git push origin --delete $(git tag -l)` // 리모트 저장소의 모든 태그를 삭제

<br />
<br />

---

---

# 2025-02-28

**CSS // Position:sticky 실습, Stacking Context, Searchbar 실습**
**Git Stash**

## 수업 내용

### UI실습 // 부트캠프 13기 명단(feat.sticky, z-index)

- `z-index`
  > HTML 요소의 쌓임 순서(z축 방향)를 정의하는 CSS 속성. 웹 페이지에서 요소들이 겹칠 때, 어떤 요소가 다른 요소 위에 표시될지를 결정함
  - `position: static`이 아닌 요소들(`relative`, `absolute`, `fixed`, `sticky`)은 모두 `z-index`를 가질 수 있음
- 값이 클수록 요소는 더 위쪽에 쌓이고, 값이 작을수록 아래에 쌓임
- `z-index는` **stacking context** 내부에서만 영향을 발휘함

- **기술부채**
  > 소프트웨어 개발에서 더 나은 솔루션을 사용하지 않고 쉬운 솔루션을 선택함으로써 발생하는 추가 비용  
  > 예시 : inline- 속성일 때 요소 사이에 생기는 공백을 없애려고 font-size:0 트릭을 사용
           -> 자식 요소가 생겼을 때 해당 속성값이 내려가면서 문제가 생길 수 있음.
              (※ 이런 편법 대신 display:flex로 없애는 것이 좋다.)
- transform 요소
  https://developer.mozilla.org/ko/docs/Web/CSS/transform

### Stacking Context(쌓임 맥락)

> HTML 요소가 화면 상에서 쌓이는 순서(z축 방향)를 결정하는 개념으로 웹 페이지에서 요소들이 겹칠 때, 어떤 요소가 다른 요소 위에 표시될지를 결정하는 데 중요한 역할을 함

- 참고 링크
  https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_positioned_layout/Understanding_z-index/Stacking_context
  https://developer.mozilla.org/ko/docs/Web/CSS/transform

- `filter` 속성

  - 속성값: blur, brightness, contrast, hue-rotate,drop-shadow, gayscale, sepia, invert, opacity, saturate 등등...
  - 아래와 같이 함수 조합도 가능
    ```CSS
      filter: contrast(175%) brightness(103%);
    ```
  - 참고 링크
    https://developer.mozilla.org/ko/docs/Web/CSS/filter

- `transition` 속성

  > shorthand property for transition-property, transition-duration, transition-timing-function, transition-delay, and transition-behavior

  - 트랜지션으로 변화를 시작할 property와 시간은 해당 요소에 주고 가상요소에 변화 후의 속성값을 부여해서 시간에 따른 요소 모양의 변화 정의
  - https://developer.mozilla.org/ko/docs/Web/CSS/transition
  - transition-timing-function 시간 그래프 볼 수 있는 사이트
    https://cubic-bezier.com/#.17,.67,.83,.67
  - 개발자도구에서 그래프 확인, 값 조정해볼 수도 있음

- `transform` 속성

  > The transform CSS property lets you rotate(회전), scale(크기 변경), skew(찌그러뜨리기), or translate(이동) an element. It modifies the coordinate space of the CSS visual formatting model.

- **`Stacking Context`** (`z-index`, `transform`, `transition`)코드 예시

  ```CSS
  .case-01 {
    display: flex;
    flex-flow: row nowrap;

    .button-avatar {
      margin-right: -20px; /* 음수 마진을 넣으면 박스가 좁아져서 요소끼리 겹침 발생 */
      position: static;
      filter: grayscale(100%);

      /* 트랜지션의 시작점은 여기, 도착점은 hover에 */
      transition: rotate 500ms;
      /*변화를시작할property이름 시간, */

      &:hover,
      &:focus {
        filter: none;
        /* 아바타의 겹치는 순서를 제어하기 위해 0보다 큰 값 지정  */
        /* position이 static이 아닌 경우에만 z-index 적용됨 */
        z-index: 10;
        transform: scale(1.2);
        /* transform: translate(0, 20px); */
        /* translate는 ▼요렇게도 쓸 수 있음. 아래 쪽이 모던한 코드 형식임 */
        /* translate: 0 -20px; */

        /* opacity: 0.8; */
        rotate: 20deg; /* turn or deg로 지정. 음수값 부여 시 왼쪽으로 회전 */
      }
    }
  }

  /* Transition */
  .case-02 {
    margin-block-start: 20px;
    display: flex;
    gap: 20px;

    [class^='area'] {
      /* 시간은 normal이 0.4s */
      /* 앞에꺼 끝나면 시작되도록 딜레이 넣음 */
      transition-property: background, border-radius;
      transition-duration: 0.2s, 1s;
      transition-delay: 0s, 0.2s;
      transition-timing-function: ease;

      /* 줄여쓰기: `효과 발동시간 지연시작 타이밍` */
      transition:
        background 0.2s 0s ease,
        border-radius 1s 0.2s ease;

      /* 전체에 동일한 시간 줄 때 all로 기재 */
      transition: all 200ms;

      &:hover {
        background: var(--pastel-orange);
        border-radius: 50%;
        rotate: 2turn;
      }
    }
  }
  ```

### UI실습 // 서치바

- 마크업// 가장 작은 컴포넌트(원자 or 분자단위)부터 만들어서 합치는 방식으로 구현
- 원래 CSS에서는 자식 요소를 선택했을 떄 부모요소를 부를 수는 없어서 js를 썼지만, focus-within이라는 새로운 선택자가 나오면서 CSS에서 바로 부를 수 있게 됨
  ->  
   focus-widthin mdn

### 기타 스몰팁

※ `<fieldset>`태그로 선택자 지정 시 `flex`됐을 때 에러 케이스 존재. 가급적 사용x -> 따로 그룹핑해서 class 등으로 선택할 것을 권장

※ `:focus` 시 어떤 서식이 선택되었는지 시각적으로 구분할 수 있는 다른 대안(디자인 수단)이 있는 경우엔 outline을 제거해도 좋지만, 그렇지 않을 경우 절대절대절대 outline 을 없애서는 안됨

※ 원래 버튼은 손가락 안 보이는 게 기본스타일(근본) `a(link)`만 손가락 나오는 게 근본이다

### Git 실습 // `git stash`

> `git stash`는 Git에서 변경된 파일을 임시로 보관하고 나중에 다시 적용할 수 있는 기능  
> 아직 커밋하지 않은 변경 사항이 있지만 다른 브랜치로 이동하거나, 다른 작업을 하고자 할 때 주로 사용  
> 이 명령을 사용하면 변경 사항을 임시로 "stash"(숨기기)할 수 있으며, 나중에 필요할 때 다시 불러올 수 있음

**stash 관련 명령어**

- `git switch -c ui` // ui라는 브랜치를 만들고 체크아웃하거라
- `git stash` // 현재까지의 변경내용을 stash에 임시 저장
- `git stash list` // 임시 stash 목록 확인
- `git stash show` // 임시저장한 변경사항의 내용 조회
- `git stash apply` // 변경사항 다시 적용
- `git stash drop` // 임시저장 이력 삭제
- `git stash pop` // 임시로 숨겨놓은 변경 사항 브랜치에 적용 + 숨겨놓은 이력 삭제
  : apply는 이력 남기고 가져오기, pop은 이력도 삭제한다는 차이 있음

- `git restore .` 전부 되돌리기
- `git branch -d ui` // 브랜치 삭제. 해당 브랜치로 작성한 코드 병합 전에 삭제 강제할 시 `-D` 옵션으로 명령해야 수행

## 과제 관련

- home-work 폴더>login 폴더에 과제 있음
  : figma에 피그마 시안 있음
  : pages에 이미지, 파일요소

// login.md에는 회고 적을 것 -> 학습한 내용X. 나의 한 주를 돌아보는 내용

- 차주부터는 과제 피드백에 코드 레벨의 내용은 없을 예정. 수업 시간에 정리해주시는 코드랑 스스로 비교해보면 됨
  과제 코멘트는 회고 내용에 대한 피드백으로 구성될 것임

- 화요일 오전 -> 과제 리뷰

- 신경 쓸 부분
  - 키보드로 컨트롤되는 체크박스 까다로울 것
  - 스위치 디자인 어려울 것
  - 모바일.데스크탑 마다 다르게 보이는 요소

<br />
<br />

---

---

# 2025-03-04

**CSS // 컴포넌트화 (feat. Login 과제풀이)**

## 수업 내용

### 같이 해보는 반응형 로그인 화면(Login)

- 컴포넌트(부품)을 만들 때는 **바깥쪽 여백을 넣으면 안됨** 배치할 때 넣자
- `inline`요소는 `width` 속성 줄 수 없음. 기본적으로 `content`값을 가지며, 값을 부여해도 무시함  
  -> `display: inline-flex;` 로 바꾸면 width 줄 수 있음
- **키보드 접근 시 표시되는 테두리** : `포커스 링`이라고 부름
- `:has()` <- 특정 조건을 만족하는 자식 또는 하위요소를 포함하는 부모 요소를 선택할 수 있음 // 과거에는 없어서 js 사용했음
- `checked` 로 불러서 쓰려면 `input`요소 뒤에 `label`이 있어야 함 (형제 레벨 이여야함)
  그에 반해 `has`는 비교적 제한이 적음
- `inline`은 `padding` 줘도 영역이 커지지 않음. 부모 요소한테 `display: inline-flex;` 주면 부모상자와 함께 영역이 커지게 할 수 있음
  (자식이 `flex-item`이 되면서 영역 가지게 되는 것)
- `text-indent` <-텍스트의 첫 줄 들여쓰기 설정. `clear:both;`처럼 블록 요소에만 사용 가능함
- 이미지 여러개를 png 하나로 합치고 배경으로 운용 -> called `CSS Sprite` :: 성능적으로 좋음
  https://www.toptal.com/developers/css/sprite-generator
- `filedset` 태그에는 아무것도 안 하는 게 좋다
  혹시 모르니 border/margin/padding도 다 0으로 설정해서 없애버려
- 성능 측면에서 봤을 때는 `img` 부르는 것보다 마크업 안에 `svg`가 바로 있는 게 좋음
- outline 디자인은 둥글게 안 됨. 각진 형태만 줄 수 있음
  -> 둥근 효과를 주기 위해, outline 0 주고 box-shadow+border-radius를 줌
  ```CSS
     &:focus {
     outline: 0;
     box-shadow: 0 0 0 1px;
     border-radius: var(--rounded-xs);
     }
  ```

**접근성 관련**

- `:focus`는 마우스로 접근해도 적용되지만 `:focus-visible` 쓰면 **키보드 접근 시에만** 적용 됨
- `aria-live` : js 등으로 동적 업데이트된 데이터가 있을 때, 읽어주는 방식 선택할 수 있음
  - `polite` (읽던 거 마저 일고 말함)
  - `assertive` (말하다 끊고 바로 말함)
- `aria-errormessage` : 접근성(A11Y) 관련 속성으로,
  스크린 리더(Screen Reader) 사용자에게 에러 메시지를 연결해서 읽어주기 위한 용도로 사용

  - https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Attributes/aria-errormessage
  - 사용 예시 (aria-invalid/aria-describedby/role="alert" 이 세 가지를 꼭 함께 써야 함)
    ```html
    <label for="email">이메일</label>
    <input
      type="email"
      id="email"
      aria-errormessage="emailError"
      aria-invalid="true"
    />
    <span id="emailError" role="alert">올바른 이메일 주소를 입력해주세요.</span>
    ```

<br />
<br />

---

---

# 2025-03-05

**CSS // Grid System**

## 수업 내용

### 같이 해보는 반응형 로그인 화면(Login)// 이어서

- `order` 속성
  > Flex 컨테이너 안에 있는 각 Flex 아이템의 순서를 결정할 때 사용.  
  > 기본적으로는 HTML에 작성된 순서대로 화면에 표시되지만, order 값을 조정하면 시각적 순서를 변경할 수 있음  
  > **시각적 순서만** 변경하기 때문에 HTML의 문서 흐름(코드 순서) 자체가 바뀌는 것 아님 : 접근성이나 키보드 네비게이션 같은 요소에서는 여전히 원래 순서를 따름
  - 기본값은 0. 숫자가 작을수록 앞에 배치되고, 숫자가 클수록 뒤로 밀려남
  - Flexbox 레이아웃에서만 사용 가능
  -
- `:invalid`,`:valid` vs `:user-valid`, `:user-invalid`

  - 폼 요소의 값에 대한 유효성 검사 결과에 따라 적용 여부 결정
  - `:invalid`,`:valid`는 빈 값도 유효하지 않다고 판정
  - `:user-valid`, `:user-invalid`는 유저가 `입력한 값`만 확인함. 빈값일 땐 valid로 판정

- 정규식 표현
  - `.{6,10}` -> `.`(모든 문자) `6`(최소길이)`10`(최대길이)
  - 정규식 학습 및 테스트 사이트  
    https://regexr.com/
    - `\d` : 숫자, `\w`: 문자, `\W`: 특수문자
- `readonly` : 폼 요소에서 사용자가 값을 수정하지 못하게 막는 역할을 하는, `'읽기전용'` 속성

  ```CSS
  /* 읽기 전용 */
  &:read-only {
  --text-color: var(--blue-300);

      cursor: default;
      pointer-events: none;
      }
  ```

- `disabled` : 비활성화

  ```CSS
  &:disabled {
    --fill-color: var(--gray-200);

    cursor: not-allowed;
    opacity: 0.7;
  }
  ```

### Grid Layout

> **CSS Grid Layout**은 2차원(행과 열) 레이아웃을 설계하기 위한 강력한 도구로, **가로(행)**와 **세로(열)**를 동시에 제어할 수 있는 레이아웃 방식  
> Flexbox는 주로 "한 방향(1차원)" 정렬에 강한 반면, Grid는 "행과 열을 동시에" 다룰 수 있어서 2차원 레이아웃에 특화

1. **Grid Container**(부모)
   `display: grid`를 설정한 요소가 그리드 컨테이너가 됨
2. **Grid Item**(자식들)
   그리드 컨테이너 안의 **직계** 자식 요소들이 그리드 아이템이 됨

- 주요 속성
  | 속성 | 설명 |
  |:--------------------:|:--------------------------|
  |grid-template-columns |열(컬럼)의 너비 설정|
  |grid-template-rows |행(로우)의 높이 설정|
  |grid-column |아이템이 차지할 열 범위 설정|
  |grid-row |아이템이 차지할 행 범위 설정|
  |gap |아이템 사이 간격 설정 (row-gap, column-gap)|
  |justify-items |가로축 정렬 (아이템 개별 정렬)|
  |align-items |세로축 정렬 (아이템 개별 정렬)|
  |justify-content |가로축 정렬 (그리드 전체 정렬)|
  |align-content |세로축 정렬 (그리드 전체 정렬)|

- Grid system의 예시 볼 수 있는 사이트  
  https://960.gs/  
  _(※ 여기서 Grid는 CSS Grid 기능과는 다른, 디자인시스템 의미의 grid)_
  https://www.heropy.dev/p/c6ROLZ

- 정렬 shorthand 표기들☆★
  - **place-items** : `align-items` & `justify-items` 의 shorthand 표기법
    // 부모가 사용하는 속성 `=` 컨테이너 전체에 `아이템 전체`의 정렬 위치를 지정하는 속성
  - **place-self** : `align-self` & `justify-self`의 shorthand 표기법
    // 자식이 사용하는 속성 `=` `개별 아이템의 정렬 위치`를 지정하는 속성

## 수업시간에 언급된, 찾아볼 내용

-cursor, traee

- floating lable 해보렴
- dvh

<br />
<br />

---

---

# 2025-03-06

**CSS // Grid Layout, Multi Column, Masonry Layout, Select UI**

## 수업 내용

### Grid Layout

- grid Layout 생성 시, 각 라인에 이름 줘서 네임을 사용할 수 있음  
  https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_grid_layout/Grid_layout_using_named_grid_lines

  - `[ㅇㅇ-start] [ㅇㅇ-end]` 이렇게 이름 주면 `ㅇㅇ` 라는 이름으로 영역 지정해줄 수도 있음
  - 예시 코드

  ```CSS
  .container {
  min-height: 100vh;
  min-block-size: 100vh;

  display: grid;

  grid-template-columns:
    [full-start] minmax(1rem, 1fr) [content-start] repeat(12, minmax(5.3125rem, 1fr))
    [content-end] minmax(1rem, 1fr) [full-end];
  grid-auto-flow: dense;
  }
  ```

- gird / flex 모두 직계 자식만 아이템으로 취급 가능
- **subgrid**

  > 부모 그리드 컨테이너의 트랙 정의(행/열 크기)를 자식 그리드 컨테이너에서 그대로 상속받아 사용하는 방식  
  > 보통은 그리드 컨테이너 안의 요소들이 자기만의 독립적인 그리드를 가질 수 있지만, subgrid를 사용하면 부모의 그리드 시스템을 그대로 따라가도록 강제할 수 있음

- `grid-auto-flow` :`row | column | row dense | column dense`
  > 그리드 아이템이 배치되지 않았을 때, 자동으로 어떻게 흐를지를 결정하는 속성
  - https://developer.mozilla.org/en-US/docs/Web/CSS/grid-auto-flow
- `auto-fit`과 `grid`를 쓰면 `@media` 쿼리 없이도 **반응형 웹 구현 가능**

### Multi Column

- 참고 링크
  https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_multicol_layout
  - `columns`: 열 너비 및 개수 `(column-width & column-count)`
    - `column-width` // 지정한 너비만큼 단이 나눠짐 `->` 뷰포트 크기에 따라 갯수 적어지거나 많아질 수 있음
    - `column-count` // 지정한 개수만큼 단이 나눠짐
      ※ 블록 컨테이너에만 적용 가능
      ※ Flex나 Grid처럼 요소별 배치가 아니라, **텍스트 흐름을 나누는 용도**
  - `column-rule`: 다단 레이아웃에서 각 컬럼 사이에 그려지는 선을 설정하는 속성
  - `column-span`: 특정 요소가 여러 컬럼을 가로질러(span) 차지할 수 있게 하는 속성
  - `column-fill`: 다단 레이아웃에서 콘텐츠를 각 컬럼에 어떻게 채울지 결정하는 속성
    ※ `balance` or `auto` 속성값 지님. `balance`가 기본값이며 모든 컬럼 높이를 균등하게 맞춤. `auto`는 한 컬럼 다 채우고 나서 다음 컬럼으로 넘어감
    ※ 부모 컨테이너의 height가 정해져 있어야 효과적임
  - `break-after`: 줄바꿈  
    ※ 다단 레이아웃, 인쇄 미디어 쪽에 특화된 속성
    -> 일반적인 웹 화면에서는 영향이 거의 없을 때도 있음.  
    메뉴 내렸을 떄 나오는 구획 나눠진 메뉴 그런 늑김 : 단 나누기로 구현 가능

### Masonry Layout // 실습

- 인스타그램/핀터레스트같이 화면을 꽉 채우는 다양한 이미지들이 반응형으로 바뀌는 레이아웃
  이미지 위에 캡션 올리는 방법
- 1/1짜리 grid 만들고 figcaption에 place-self 주는 것

### Select UI // 실습

- 이미지는 svg 사용

<br />
<br />

---

---

# 2025-03-07

**CSS // 라이트.다크 모드, 애니메이션, 컨테이너 쿼리, Git rebase**

## 수업 내용

### 라이트/다크모드

- 미디어 쿼리 : 화면 너비뿐만 아니라 다크/라이트 모드에도 사용가능
- `svg`태그에 접근해서 `fill` 색깔 바꿀 수 있음 / `currentColor` 넣고 `style` 태그 넣어서 **라이트/다크모드에 따라 색 바뀌게** 할 수 있음

  ※ `color` 쓸 거면 `svg`의 `color: currentColor;`로 해야 하고 `fill` 쓸 꺼면 `g`안에 속성을 `fill="none"`로 해놔야 적용 됨

  ```CSS
    <style>
      g{
        fill: #000;

        @media (prefers-color-scheme: dark) {
          fill: #fff;
        }
      }
    </style>
    <rect width="100%" height="100%" fill="#F3792D"/>
    <g transform="translate(0.000000,64.000000) scale(0.100000,-0.100000)"
      fill="none" stroke="none">
  ```

- 2개의 파비콘 이미지를 등록해서 모드에 따라 다른 파비콘 보여줄 수 있음
- `light-dark()` 함수 - makes easy to make 2type-color mode
  -> 아직 일부 모바일 환경에서는 사용 못할 수 있음 주의

  ```CSS
    :root {
      color-scheme: light dark;
      }

    h1 {
      color: light-dark(black, white);
    }
  ```

### 애니메이션

- `@keyframes`: `from`과 `to`로 애니메이션의 단계별 스타일 정의

```CSS
  /* keyframe에 적용하려는 효과 정의 */
  @keyframes fade {
    0%, 100% { opacity: 1; }
    50% { opacity: 0; }
  }
  /* 정의해둔 애니메이션 사용. name/duration 2개는 필수 */
  .case-02 .target-animation {
    animation-name: fade;  /* 애니메이션 이름 */
    animation-duration: 2s;  /* 애니메이션 작동 시간 */
  }

  /* 다양한 옵션들 */
    animation-iteration-count: infinite;  /* 애니메이션 반복 횟수 : 숫자 혹은 infinite(계속실행) */
    animation-delay: 3s;  /* 시작시간 지연 */
    animation-timing-function: linear; /* 실행시간 가속.감속 조정(극적 효과) :  linear, ease-in-out.. 속성값 매우 많음 필요할 때 찾아볼 것*/
    animation-fill-mode: forwards;  /* 애니메이션이 끝나도 그 스타일을 유지할지, 시작 전에 미리 적용할지를 정하는 옵션 : none(initial) / forwards / backwards both */
    animation-play-state: paused; /* 애니메이션의 재생 및 정지를 제어 : paused or running */

  /* shorthand 표기 */
    animation: shrink 2s infinite ease-in-out both paused;
```

- `transform: perspective(400px) rotateY(0);`  
  : perspective가 원근감 더해줌. 숫자가 클수록 멀리 있는 것! 보통 400~600 많이 사용
- `margin`, `height` 등 크기 관련 속성은 reflow를 유발하는 대표적인 속성 -> 변경 지양
- `transform-style: preserve-3d;` <- 요거 넣어서 **자식 요소도 함께 움직이게** 할 수 있음
- https://animista.net/play/text/tracking-in/tracking-in-contract-bck-bottom

### 컨테이너 쿼리(Container Query)

> 특정 요소(컨테이너)의 크기나 속성을 기준으로 스타일을 적용할 수 있게 해주는 CSS 기능
> 이는 요소의 **부모 컨테이너 크기**에 따라 스타일을 변경할 수 있도록 하며, **컴포넌트 기반 디자인**에서 매우 유용
> 요소가 화면 전체 크기가 아닌 **자신이 속한 컨테이너의 크기**에 따라 동작하도록 함

- 컴포넌트는 컨테이너 쿼리로 만들고, 가져가서 배치할 때는 미디어 쿼리로 하는 걸 추천
- 요소의 부모 컨테이너 크기에 따라 스타일을 변경할 수 있도록 함
- 기준 삼고싶은 선택자에 `container(container-type의 숏핸드): inline-size;` 지정. (세로는 size 인데 거의 안 씀)  
  ※ 필수는 아니지만 컨테이너의 이름도 지정할 수 있음 `container-name: hihi;`

### Git rebase

> 현재 브랜치의 변경 사항을 다른 브랜치의 최신 커밋 위로 옮기는 작업  
> -> 다른 베이스의 변경사항을 현재 작업 중인 브랜치에 적용
> Merge와는 다르게 중간에 병합 커밋(merge commit)을 남기지 않고, 히스토리를 한 줄로 쭉 이어서 깔끔하게 만듦
> 이미 원격 저장소에 푸시된 브랜치를 rebase하면, 히스토리가 꼬일 위험이 있음

- 커밋을 다시 하는 거라서 전체 해시 다 바뀜
- `git config --global --edit` // git config 파일 수정! 여기서 mergetool 지정 가능
- `git rebase main` // (다른 브랜치에서) main 브랜치 리베이스하겠노라 = commit의 베이스를 main branch의 최신 commit으로 조정
- `git mergetool` // 머지툴 열어서 충돌내용 조정
- `git rebase --continue` // 충돌 해결 완료 후 리베이스 계속

<br />
<br />

---

---

# 2025-03-10

**CSS // @layer, Tailwind**

## 수업 내용

### @layer 규칙

> CSS는 모든 게 다 글로벌이다보니 외부 라이브러리 등 쓰면 우선순위 주기가 어려움  
> => 레이어를 사용함으로써 우선순위를 정해주게 됨

- https://developer.mozilla.org/ko/docs/Web/CSS/@layer
- 적용 우선순위
  **[제일 강함]** `Nolayer(=글로벌)` -> `@layer named` -> `@layer unnamed` **[제일 약함]**  
  ※ `named`끼리는 정의한 순서가 뒤에 올수록 강함  
  ※ `!important`는 **반대 방향으로**적용 됨
- 다양한 @ 규칙들

### **📌 주요 `@` 규칙들**

| 규칙             | 설명                                                                     | 용법                                                                                  |
| ---------------- | ------------------------------------------------------------------------ | ------------------------------------------------------------------------------------- |
| **`@import`**    | 외부 CSS 파일을 불러올 때 사용                                           | `@import url("styles.css");`                                                          |
| **`@property`**  | CSS 사용자 정의 속성을 애니메이션 가능하게 만들 때 사용                  | `@property --main-color { syntax: "<color>"; initial-value: blue; inherits: false; }` |
| **`@font-face`** | 웹 폰트를 정의하여 사용할 때 사용                                        | `@font-face { font-family: "MyFont"; src: url("myfont.woff2") format("woff2"); }`     |
| **`@media`**     | 반응형 디자인을 적용할 때 사용                                           | `@media (max-width: 768px) { body { background: lightgray; } }`                       |
| **`@container`** | 요소 크기에 따라 스타일을 적용할 때 사용 (CSS 컨테이너 쿼리)             | `@container (min-width: 500px) { .box { color: red; } }`                              |
| **`@keyframes`** | CSS 애니메이션을 정의할 때 사용                                          | `@keyframes fadeIn { from { opacity: 0; } to { opacity: 1; } }`                       |
| **`@supports`**  | 특정 CSS 기능이 브라우저에서 지원되는지 확인하고 스타일을 적용할 때 사용 | `@supports (display: grid) { .container { display: grid; } }`                         |

---

### **📌 기타 `@` 규칙들**

| 규칙                 | 설명                                       | 용법                                                                  |
| -------------------- | ------------------------------------------ | --------------------------------------------------------------------- |
| **`@layer`**         | 스타일 우선순위를 제어할 때 사용           | `@layer base { h1 { color: blue; } }`                                 |
| **`@namespace`**     | XML 네임스페이스를 지정할 때 사용          | `@namespace svg "http://www.w3.org/2000/svg";`                        |
| **`@page`**          | 프린트할 때 페이지 스타일을 정의할 때 사용 | `@page { size: A4; margin: 20mm; }`                                   |
| **`@counter-style`** | 사용자 정의 리스트 스타일을 만들 때 사용   | `@counter-style my-style { system: cyclic; symbols: ➜ ➝ ➞; }`         |
| **`@scope`**         | 특정 영역에만 스타일을 적용할 때 사용      | `@scope (.wrapper) { p { color: red; } }` (현재 일부 브라우저만 지원) |

---

### **📌 정리**

1. **외부 리소스 로드** → `@import`, `@font-face`
2. **반응형 디자인 & 지원 확인** → `@media`, `@container`, `@supports`
3. **애니메이션 & 효과** → `@keyframes`, `@property`
4. **우선순위 & 범위 지정** → `@layer`, `@scope`
5. **특수 기능** → `@namespace`, `@counter-style`, `@page`

### Tailwind CSS

> Bootstrap같은 Pre Built-in 컴포넌트 방식과 달리 tailwind는 Utility-first 개발 방식을 제공
> html 마크업에서 클래스만으로 스타일링 가능

- JS 모듈 시스템에는 mjs와 cjs 두 가지 있음. mjs가 더 최신 인 듯
- tailwid.config.js 테일윈드 설정파일

**※ git init 이후에는 항상 gitignore를 해두자**

#### 프로젝트 세팅

- pnpm 글로벌 설치 및 확인

  - Pnpm: npm보다 빠르고 효율적, pnpm 사용 시 명령어에서 run 생략 가능  
     https://pnpm.io/ko/  
    `$npm install -g pnpm@latest-10`  
    `$npm list -g`

- git & gitignore 세팅  
   `$git init`  
   `$npx add-gitignore node windows osx visualstudiocode`  
   gitignore파일에 .DS*Store 등록 후 `add` & `commit` *(: Initial Commit)\_

- npm으로 테일윈드CSS 패키지 설치  
  `$npm install tailwindcss @tailwindcss/cli --save-dev`  
  **`<`실습 목적`>`** pnpm으로 설치하기 위해 삭제 // node_modules 폴더도 삭제  
  `$npm remove tailwindcss @tailwidcss/cli`
- pnpm으로 패키지 설치 / 업데이트 -> pnpm이 메세지도 깔끔하게 뜨고 빠르고 폴더도 깔끔!  
  `$pnpm add tailwindcss @tailwindcss/cli --save-dev`  
  `$pnpm add -g pnpm`  
  **====> pnpm-lock.yaml 생김**

- `add` & `commit` _(: Install wailwind package)_
- .html에는 `output.css` 연결 & .css에는 `@import "tailwindcss"` 선언: 패키지가 알아서 연결해줌
-
- (json에 미등록 상태라) 명령어로 output 파일 생성  
  `npx tailwindcss -i ./src/styles/input.css -o ./src/styles/output.css`

- node_modules 폴더 보이기/안보이기 토글 생기게 하는 익스텐션  
  https://marketplace.visualstudio.com/items?itemName=chrisbibby.hide-node-modules  
  : .vscode 폴더 안의 `settings.json` 도 만들어줌. 여기서 프로젝트의 세팅 설정 가능

- `settings.json`에 설정 넣음 / settings에서 `tailwind hover`/`tailwind emmet`/`tailwind suggestions` 체크
- 서버설정
  - html에 만든 내용은 build를 해야 out.css에 가서 반영이 됨  
    -> 매번 빌드해줘야 하기 때문에 번거로움 : `--watch` 옵션을 줘서 빌드할 때 바뀐 걸 계속 반영하게 함  
     서버 실행: ctrl+c 하기 전까지 왓치모드로 지켜보고 있다가 계속 재빌드해줌
  - 테일윈드 빌드, 왓치, 서버를 한 번에 다 해야해서 npm-run-all 패키지 설치, script에 명령어 추가  
    `$ npm i -D live-server npm-run-all`

===> `$pnpm dev` 혹은 `$npm run dev` 로 서버 실행 가능

#### tailwind CSS 활용

- `@theme` -> 레이어 안에 들어감. `:root`는 레이어 안X. tailwind에서는 `@theme`에 정의할 것을 권장  
  **[제일 낮음]** theme(선언), base(reset), components,utils **[제일 강함]**  
  테일윈드에서는 이런 규칙이 있음

  - 배경색: bg- ~
  - 텍스트: text- ~
  - 테두리: border- ~
    @theme에서 색상만 재정의하면 그렇게 부를 수 있는 클래스들의 색상이 다 재정의됨

  `--color-\*: initial;` 요걸 주면 **정의되어있던 걸 싹 무시하고** 내가 정의한 것만 쓰게 됨

- breakpoint 넣은 반응형 화면도 도 간단히 구현 가능
- css 작성하면 tailwind로 바꿔주는 익스텐션도 존재: EX: convert CSS to Tailwindcss
- https://flowbite.com/tools/tailwind-cheat-sheet/ 클래스명 확인 가능 (공식 아니라 업데이트 늦기도)

- `size-`클래스는 1:1비율로 사이즈 줌
- **`space-y-N`**: 가장 바깥쪽을 제외한 안쪽에 gap 줌. flex나 grid아니여도 요소 사이사이 마진 줄 수 있는 속성!

**※ tailwind.config.js <- 이제 없는 거. AI가 고치라하면 헛소리임**

## 수업시간에 언급된, 찾아볼 내용

- 드림코딩 유튜브 클론코딩
- @support // 찾아보기 grid일때만실행됨
- tree shaking : 쓸모없는 거 없애버림

<br />
<br />

---

---

# 2025-03-11

**tailwind CSS // Layout, iframe, priority, animation 등등**

## 수업 내용

### taiwind: index 페이지 실습

- Arbitrary value 쓸 떄 공백은 \_로 표기

### taiwind: iframe -반응형 영상 페이지 실습

- `iframe`은 가로만 늘어나고 세로는 늘어나지 않음
  비율 관련 유틸리티: `aspect-auto`(자동) / `aspect-squeare`(1:1) / `aspect-video`(16:9)

- `overflow: hidden;`& `text-overflow: ellipsis;` & `white-space: nowrap` 3개 콤보 // 글 길면 말줄임표... 나오는 거  
  -> `truncate` 유틸리티 1개로 해결 가능(부모에 min-w-0 넣어야 함)

- 컴포넌트로 재활용하려고 만든 클래스는 `@layer components` 안에 넣어야 함  
  밖에 있으면 우선순위 밀려서 적용 안됨 // 재사용성을 위해 컴포넌트 레이어 안에 기본 스타일을 정의하고 그 다음에 스타일 수정이 필요하면 유틸리티 스타일을 사용해서 변화를 주기

- 모달
  `opacity-0` (기본) `open:opacity-100`(오픈하면 100으로 바꿔줘)

- 디자인 가져다 써서 페이지 만든 경우 '교육 목적으로 만들었다'라는 내용의 모달창을 넣을 것!
- 컨테이너 쿼리도 바로 사용 가능 `@container w-[300px]` 이런 식으루

**※ 캐시 지우는 방법**
`$rm -rf ~/.degit`

## 수업시간에 언급된, 찾아볼 내용

- Arbitrary value

  > CSS나 Tailwind CSS 같은 유틸리티 기반 스타일 시스템에서 특정 값이 미리 정의되지 않은 경우, 개발자가 직접 원하는 값을 넣을 수 있도록 허용하는 기능
  > **-> 프레임워크에서 제공하는 기본 값이 아니라 개발자가 자유롭게 지정할 수 있는 값**

  - 예시
    ```HTML
      <div class="bg-[#1e293b]">임의의 색상</div>
      <div class="p-[22px]">임의의 패딩</div>
    ```

  <br />
  <br />

---

---

# 2025-03-12

**CSS // tailwindCSS & vite**

## 수업 내용

### vite

- https://ko.vite.dev/guide/
- `webpack` // 자바스크립트 애플리케이션을 위한 모듈 번들러(Module Bundler). 설정 복잡하고 속도 느리다는 단점
- Tailwind 구조  
   => CLI 사용 시, **index.html이 꼭 src 안에 있어야 함**.  
   (`tailwind.config.js`의 content 배열에 지정된 파일이 있는 곳을 루트로 인식)  
   : 기본세팅에서는 `index.html`이 있는 곳을 루트로 인식함(= src가 root)
  - vite는 **index파일을 기준으로 프로젝트의 경로를 잡음**
    : index가 루트에 있어야 함
    (build.rollupOptions.input 설정을 통해 위치를 변경할 수 있음)
- build하면 매번 dist 폴더를 만들어냄: 캐싱 방지를 위해 지우는 게 좋음
  -> 지우라는 명령 clean으로 등록
- vite는 js만 연결하면 js가 styles갖고있다가 output이랑 다 연결해줌
- Vite는 자원을 `public/` 폴더와 `src/` 폴더로 나누어 관리

  1.  `public/` 폴더

      - Vite가 변환하지 않는 정적 파일을 넣는 곳
      - HTML, 이미지, 폰트, JSON 등 그대로 사용해야 하는 자원 저장
      - `public/` 폴더 안의 파일은 빌드 시 변형 없이 `dist/`로 **그대로 복사됨**
      - **절대경로(/assets/image.png)**를 사용하여 접근 가능 → public 폴더명을 생략하고 사용
      - 명시 예

      ```CSS
        <img src="/logo.png" alt="Logo" />
      ```

  2.  `src/` 폴더

      - Vite가 변환(번들링, 최적화)하는 파일을 넣는 곳
      - JavaScript, TypeScript, CSS, SCSS, 이미지 파일 등 해시값이 붙는 파일 저장
      - 상대경로(`./assets/logo.png`)로 참조하여 import 가능
      - 명시 예

      ```CSS
        import logo from'./assets/logo.png';
      ```

      이렇게 하면 Vite가 `logo.png`를 빌드 시 최적화하고, 최종적으로 dist/에서 해시가 붙은 파일명으로 변환됨

      => `build`하면 `dist/`폴더 생기면서, `public/`의 파일은 그대로 복사됨
      `src/`의 자원들은 최적화되면서 **해시**가 붙음 → `index.html`에서 해시가 붙은 파일을 참조

- 폰트는 CSS에서 연결ㄴㄴ HTML에서 연결해서 쓰기!
  // CSS에 해두면 시스템이 불필요한 최적화 시도함
- `preload`:: webfont blonking 방지.
  안 하면 폰트 받아서 그릴 때 화면이 깜빡하는 현상 발생하기도 함
- 네트워크 체크
  https://developers-kr.googleblog.com/2020/05/Introducing-Web-Vitals.html

- **npm-run-all** 설치 및 명령어 세팅

  1. `$ npm install npm-run-all --save-dev` 로 패키지 설치
  2. `package.json`파일 `scripts에 하기 내용 추가
`"compile":"run-s clean build preview"`
     **===> 한 방에 클린-빌드-미리보기 할 수 있도록 세팅 가능**

- 여러 개의 이미지 사용 시, `@theme` 안에 `image-set`으로 경로를 2개 세트씩 묶어놓고 부르면 깔끔함 // 강사님 apple 코드 참고
- **버튼 내 가운데 정렬** // `inline-flex justify-center items-center`

#### 환경구성

- dev = 개발환경에서 실시간 확인
  build + preview = 실제 서비스 올리기전(push 전) 최종 검토

## 수업시간에 언급된, 찾아볼 내용

- SPA / MPA

<br />
<br />

---

---

# 2025-03-13

**UI프로젝트 // 프로젝트 세팅 및 준비**

## 수업 내용

### 프로젝트 안내

- 프로젝트 관련 질문은 질문방에, 음성 도움 필요한 경우 SOS 말머리로 올릴 것
- PT, 자료 정리 등에 시간 쓰지 않도록 이번에는 따로 발표 안 시킬 예정!
  -> 대신 index page에 문서, 컴포넌트, 프로젝트 페이지 연결해서 팀 당 5~10분(최대) 내외로 소개하는 시간 있을 것
- gitHub 데일리스크럼 / 마일스톤 사용 권장
- scaffolding(스캐폴딩) : 기본적인 골격/구조를 잡는 것 ※`비계(높은 곳에서 공사할 수 있도록 임시로 설치한 가설물)`라는 뜻

### 프로젝트 세팅 실습: GitHub

**<스크럼 마스터가 해야할 일>**

1. **gitHub** 조직-> `create a new repository` // name, description 고민해서 넣을 것. `public` 선택
   ※ `Netrify`는 무료이용자에게 Private 저장소 배포 서비스는 제공X. 버셀은 가능
2. 생성한 Repository `git clone`으로 로컬에 가져옴
3. tailwind 사용 여부 팀끼리 협의해서 결정. 슬비쌤 git에 스캐폴딩 끝난 기본 구성 프로젝트 준비해둠: `degit`으로 가져와서 폴더에 넣기-
   : ※ degit으로 가져왔기 때문에 기존 remote가 살아있음. history도 그대로 남음
4. 업데이트 된 내용을 `add/commit/push`
5. gitHub에서 GUI로 브랜치 생성 // `view all branches -> New branch 버튼 -> develop` 입력 **항상 develop에서 작업!**
   -> 팀원들도 develop 받아서 작업하게할 것임 >>> `Settings`에서 `Genera`l 가서 `Default branch`를 `develop`으로 전환
6. 로컬에서 develop 브랜치를 가져옴 `$git switch -c develop origin/develop`
7. 실수하지 않도록 로컬에 있는 main 브랜치 삭제 `$git branch -d main`
8. PR템플릿 사용하기 위해 `.guthub폴더`+그 안에 `PULL-REQUEST-TEMPLATE.md `파일 생성 **※ fetch+merge=pull**, pull request의 규칙 정의
   **※ PR: 내 이슈 완료했어 다들 퍼가요 하세요~ 라는 뜻**
   => 기능 완성, 버그 픽스 후 등등 <U>문제없이 동작하는것이 확인된 상태에서</U> PR 올림. 코드에 문제가 있다면 PR도 거절당할 수 있음
   ※ guthub폴더에는 ISSUE template, PR template 등 깃헙에서 사용할 파일들 저장
9. main/develop 브랜치 보호를 위한 규칙 추가
   : gitHub `Settings`-`Branches`-`Branch Protection rules`에서 `Add branch ruleset` 선택하고 규칙 설정
   : Ruleset Name `main-develop-protections`으로 지정(다른 이름 해도 됨) 상태 Active로 설정
   : 특정 멤버에게만 예외로 적용할 경우 Bypass 항목에 추가 [실습 시 요건 할 필요 ㄴㄴ]
   : 브랜치 삭제 제한, **강제(-force) Push 할 수 없도록 설정**
   : 병합 시 팀 멤버의 승인을 거치도록 설정하고 승인이 필요한 멤버의 수 지정 // 최소 1명 이상 넣을 것
10. 멤버 초대 // `Settings -> Collaborators and teams -> Add people` // `Role`도 지정 가능

**<멤버가 할 일>**

1. 초대 수락
2. local로 `clone` 한 후 `npm install`로 패키지 설치
3. PR 생성

- ISSUE/MILESTONE/태그 등등 미리 해보기
  ※ ISSUE에서 바로 브랜치 딸 수 있음 // 팀 멤버가 ISSUE 딸 수도 있음.
  bugfix/issuename 이런 식으로 만들면 좋음/ 개인 브랜치 말고 이슈 브랜치를 쓸 것!

- 브랜치 따서 ISSUE update, add commit push해서 연결

- gitHub에서 Open a pull request -> 가면 미리 등록한 PR템플릿 있음. 유형 중 push 건에 해당 부분만 x체크 후 나머지 항목을은 지워버뤼귀
  체크리스트체크, PR 상세에는 의견 남기고싶은 분 작성

- 프로젝트 - Create new issue에서Repository 선택 후 blank issue에서 title/description 입력해서 발행 가능.

- 추천 진행 방식: 아침에 SCRUM 하고 마스터 화면 같이 보면서 ISSUE 생성/배정하기

- gitHub에서 `프로필-your organizations-new organization` // `setup`할 때 `organization name` 겹치면 안됨.
  like-lion-$ 이메일주소 입력 / My personal account 선택

- 디스코드 알림 연결 가능: merge 할 때마다 알림

### 프로젝트 세팅 실습: 컨벤션 및 위키

- 커밋 메세지에 이슈 넘버 붙이면 푸시했을 떄 자동으로 이슈 컴플리트 됨!
- gitHubwiki : 깃헙 저장소랑은 별도임! 따로 운영되는 위키..
  안되면 대문에 멤버 소개 요런 거라도 해주면 좋겠다고 하심

### 프로젝트 배포 실습: vite+Github+Netlify

https://wholesale-snipe-50a.notion.site/Vite-Github-Netlify-1eb209e59e364c0ba4ceba71a15a0ad6

#### 초기 배포 세팅

- gitHub에 소스 `push`, develop에 `merge` -> main에 `merge` ※ dist 없는 상태
- Netrify 접속
  1. 조직 계정 선택 -`selected repository` - `branch` main으로 설정
  2. `Build settings`에서 `Base directory` -> `dist` 라고 입력 (: 배포될 디렉토리가 dist야)
  3. `Build command`에 `npm run build` 라는 명령어 입력 -> Netrify가 `package.json` 보고 필요한 거 깔아서 이 명령어로 빌드/배포하겠다는 의미
  4. `Deploy UI project` 버튼 클릭
  5. `Deploy log` 에 전부 compelete 떴나 확인
- Site overview에서 주소 확인 가능 // site name 바꿀 수 있음

#### 업데이트 내용 반영

1. 로컬에서 `npm run dev` // `npm run build` // `npm run preview` // `npm run clean` 으로 확인 및 정리
2. `git add/commit/push` 해서 브랜치 내용 보내기
3. gitHub에서 `Compare & pull reques`t 누르고 `base/compare` 설정 (base가 반영 되는 쪽!(main))
   => 요청 후 `merge` 진행
4. `merge` 끝나면 netrify bot 뜨면서 배포 확인/미리보기/QR 뜸

- 내일 테스트페이지 미리 배포해둘 것
- 2~3일에 한 번 씩 메인에 merge해서 배포결과 확인

## 수업시간에 언급된, 찾아볼 내용

- 애자일 스크럼
- **백로그** : 주로 애자일(Agile) 개발 방식에서 사용되는 용어로, 앞으로 해야 할 작업들의 목록을 의미

  1. 제품 백로그(Product Backlog) // 전체 프로젝트에 필요한 모든 기능, 요구사항, 개선사항, 버그 수정 항목 등을 정리한 목록
     - 제품 책임자(Product Owner)가 관리
     - 항목은 우선순위가 매겨지며, 높은 우선순위의 항목부터 개발에 들어감
     - 항목들은 일반적으로 에픽(Epic), 유저 스토리(User Story), 태스크(Task) 등의 형태로 표현
  2. 스프린트 백로그(Sprint Backlog) // 현재 스프린트(짧은 개발 주기) 동안 개발팀이 작업할 항목들만 따로 모아놓은 목록
     - 개발팀이 직접 작업 범위와 목표를 정하고 관리
     - 각 항목은 더 세부적인 작업 단위(흔히 issue 또는 task)로 나뉘어 실행 됨

- 문서 정리를 잘 할 것. troubleshooting 경험 정리하는 거 좋음

<br />
<br />

---

---

# 2025-03-14

**UI프로젝트 // 시안 확정, 개발환경 및 프로젝트 세팅**

## 수업 내용

### UI프로젝트 시안 배포

https://drive.google.com/drive/folders/1QBYEoGPMd4M-TJoM8LevonP8qYrZ3j1D?usp=drive_link

- figma에서 plugins -> export styles to CSS variavles 기능 -> 원하는 옵션 선택 후 Generate
  -> CSS 변수로 뽑아줌 // 유료에서만 가능한 기능

- Magic Patterns -> 특정 서비스에서 원하는 UI뽑아서 가져올 수 있음 (figma/React Component)
  1.  html to React & Figma by Magic Patterns 라는 크롬 확장 프로그램 설치
      https://chromewebstore.google.com/detail/html-to-react-figma-by-ma/chgehghmhgihgmpmdjpolhkcnhkokdfp?hl=ko
  2.  원하는 웹서비스 화면에서 select HTML 버튼 클릭하고 원하는 요소 덩어리를 클릭(파랗게 보임)
  3.  magicpatterns 사이트로 이동 되며 react 코드/html/figma 로 export할 수 있게 됨
  4.  figma로 export : Layer ID값 줌
      figma Plugins->Magic Patterns 설치하고 선택하면 Layer ID 입력창 뜸
  5.  ID 입력하면 figma에 디자인 들어옴
      ----html.to.design -> 페이지 단위로도 가져올 수 있는 플러그인

https://frontendfoc.us/issues/683

- prettierrc.cjs
  mjs만 되는 기기도 있고, cjs만 되는 기기도 있고, mjs문법 방식을 cjs에 넣어야 되는 경우도 있음

<br />
<br />

---

---

# 2025-03-25

**UI프로젝트 // 프로젝트 종료 : 강사님 피드백**

## 수업 내용

### 프로젝트 진행 시 주의사항

- SEO 관점/검색 최적화 관점에서 검토해볼 것
- 중간배포를 통해 미리 검수하고 개선할 것
- 프로젝트 공간에 평가보고서 등의 문서 추가 // 발표 시 해당 내용도 발표할 것
- 검수도구 및 피드백 링크  
  https://www.notion.so/UI-1c073873401a8089bbd5e5c92a261db3

### 공통 피드백

- `commit message` 통일성 지킬 것 // 큰 프로젝트 깃허브의 커밋메세지 참고
- `README.md`에 배포사이트 넣어두니 좋다 // 참고 사이트도 넣으면 완벽
  README 잘 한 팀 : 8팀, 11팀, 16팀
- `명도대비` 3 이상, 4.5 정도 권장 // `비즈버그`라는 확장 프로그램 사용하면 쉽게 확인 가능
- 스크롤해야 나오는 디자인은 **사용자 입장에서** 좋은 UI는 아님
- 장식용 이미지는 `alt=""`로 하는 것을 권장. `aria-hidden`은 '화면에 보이지만 읽지 마세요'라는 의미일 때 사용
- 마우스로 사용할 수 있는 기능은 키보드로도 똑같이 사용 가능해야 함
  -> hover하면 보이거나, hover하면 뒤집혀서 내용 나오는 기능 지양할 것

- `label`/`placeholder`/`aria-label` 비슷해보여도 다름. 사용 시 주의
  - `<button>`이나 `<a>` 같은 인터랙티브 요소가 비어있어서 **읽을 내용이 없을 때** `aria-label` 사용. label 있으면 굳이 쓸 필요X
  - ARIA in HTML (W3C) 글 읽어보이면 좋을 듯

-애니메이션 너무 많이 쓰지 말 것. 광과민성 발작 등을 유발할 수 있는 요소이니 정지시키는 버튼 있어야 함

- `prefers-reduced-motion` : 동작 줄이기 옵션. 기본 애니메이션에 별도로 dissolve된 효과를 적용하거나 애니메이션을 제거 하고 보여줌

  ```CSS
    @media (prefers-reduced-motion) {
      /* 여기 줄어든 효과의 애니메이션을 정의 */
    }
  ```

- CSS 배경으로 처리한 아이템 이미지 js 로 하려면 `<img>` 태그를 사용하는 것이 좋을 것(경로만 바꿔치기 할 수 있게)
- apple 사이트
  `<a>`태그로 전체 카드영역 클릭할 수 있지만, 탭 이용 시 글만 접근할 수 있음
  // `event-bubbling`, `event-capturing` 사용한 것
- 컬러를 선택할 수 있게 하려면 색깔에 해당하는 text도 제공할 것

## 수업시간에 언급된, 찾아볼 내용

- CSR(ex_React) 과 SSR(ex_Next)

  - **CSR (Client-Side Rendering = 클라이언트 사이드 렌더링)**

    - 웹 페이지의 대부분을 브라우저(클라이언트) 에서 렌더링하는 방식
    - 사용자가 페이지에 접근하면, 서버는 빈 HTML과 JavaScript 파일을 보내고 브라우저가 JavaScript를 실행해서 필요한 데이터를 받아와 화면을 구성 함
    - 장점
      1. 사용자 경험이 부드러움 (페이지 전환 시 새로고침이 없음)
      2. 서버 부담이 적음
    - 단점
      1. 초기 로딩 속도가 느림
      2. 검색 엔진(SEO)에 불리할 수 있음
    - 대표 프레임워크: `React`, `Vue` 등 대부분의 SPA 프레임워크

  - **SSR (Server-Side Rendering = 서버 사이드 렌더링)**
    - 웹 페이지를 서버에서 미리 렌더링해서 HTML로 만든 뒤, 사용자에게 보내는 방식
    - 사용자가 페이지에 접근하면, 서버가 데이터를 가져와서 완성된 HTML을 만들어 보내고 브라우저는 그 HTML을 바로 화면에 보여줌
    - 장점
      1. 초기 로딩 속도가 빠름
      2. 검색 엔진 최적화(SEO)에 유리함
    - 단점
      1. 서버 부하가 큼
      2. 사용자와의 인터랙션이 많을 경우 제한적일 수 있음
    - 대표 프레임워크: `Next.js`, `Nuxt.js` 등

- 비교표
  | 항목 | CSR (Client-Side Rendering) | SSR (Server-Side Rendering) |
  | ----------- | --------------------------- | --------------------------- |
  | 렌더링 위치 | 브라우저 | 서버 |
  | 초기 속도 | 느림 | 빠름 |
  | SEO | 불리함 | 유리함 |
  | 서버 부하 | 적음 | 많음 |
  | 사용 예 | React 앱 | Next.js 앱 |

<br />
<br />

---

---
