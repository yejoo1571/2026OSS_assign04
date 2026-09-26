## Clone Source
- Clone Coding url : https://getbootstrap.com/docs/5.2/examples/checkout/

## Assignment Goals & Practice Flow
- **과제 목표**: HTML Form을 구성하는 주요 태그와 입력 요소를 익히고, CSS를 적용하여 Form UI를 직접 구성합니다. 또한 HTML Validation과 JavaScript를 이용하여 입력값을 검사하고 Form 제출 이벤트를 처리합니다.
- **Practice Flow**: `HTML Form` → `Form Elements` → `CSS` → `Validation` → `JavaScript` → `GitHub` → `Vercel`

## Weekly Review

### Key Learning
1. **HTML Form Elements & Structure**: `input` (text, email, date, checkbox, radio), `select`, `textarea` 등 10개 이상의 다양한 폼 요소들을 활용하여 웹 폼 구조를 설계했습니다.
2. **CSS Layout & Interactive Styling**: Flexbox 레이아웃(`row`, `col`)을 통해 입력 요소들의 가로 정렬 및 간격을 조정하고, `:focus` 및 `:hover` 클래스를 적용하여 시각적 반응을 구현했습니다.
3. **Form Validation & Event Control**: (`required`, `type="email"`, `minlength`)과 JavaScript의 `submit` 이벤트 제어(`preventDefault()`, `checkValidity()`, `focus()`)를 연결하여 js에서 적용된 결과를 확인하였습니다.

### Form Elements
- `input`: text, email, date, checkbox, radio
- `select` / `option`: Country, State 선택 Dropdown
- `textarea`: 배송 메모(Order Notes) 작성용 다중 행 입력창
- `button`: 제출(Submit) 처리 버튼

### HTML vs CSS
- **form1.html**: 시맨틱 태그 구조 및 다양한 입력 요소 배치에 집중한 순수 HTML 폼입니다.
- **form1_css.html**: Flexbox 정렬, 내부 여백(`padding`), 테두리 라운딩(`border-radius`), 포커스/호버 시 파란색 후광 효과(`box-shadow`, `border-color`)를 추가하여 Bootstrap Checkout과 비슷한 UI 형태를 완성했습니다.

### Validation & JS
- **HTML Validation**: 필수 입력 항목에는 `required`, 이메일 형식 검증에는 `type="email"`, 아이디 및 입력 길이 제한에는 `minlength="4"` 속성을 부여했습니다.
- **JavaScript (`form1_js.html`)**:
  - `form.addEventListener("submit", ...)`을 사용해 제출 이벤트를 감지했습니다.
  - `event.preventDefault()`로 브라우저의 기본 제출 및 페이지 새로고침 동작을 차단했습니다.
  - `checkValidity()`로 입력 요소들을 순차적으로 검사하고, 유효하지 않은 항목이 발견되면 해당 입력창으로 커서(`focus()`)를 이동시킨 후 `return`으로 실행을 즉시 중단하도록 처리했습니다.
  - 모든 조건이 충족되면 `alert("등록이 완료되었습니다.")` 메시지를 출력하도록 구현했습니다.

### Problem & Solution
- **문제점 1**: CSS 적용 시 `label` 태그의 `display: block` 스타일로 인해 Checkbox와 Radio 버튼 옆의 텍스트 라벨이 아래 줄로 떨어지는 현상이 발생했습니다.
  - **해결책**: `.form-check` 컨테이너에 `display: flex; align-items: center;`를 지정하고 라벨의 `display` 속성을 `inline-block`으로 재설정하여 아이콘과 텍스트가 한 줄로 깔끔하게 배치되도록 수정했습니다.
- **문제점 2**: 카드 결제 정보 입력 영역(`Expiration`, `CVV`)이 외부 `div.row`에 잘못 중첩되어 레이아웃 폭이 지나치게 좁아지는 문제가 있었습니다.
  - **해결책**: HTML의 닫는 태그(`</div>`) 위치를 바로잡아 `Name on card` 줄과 `Expiration/CVV` 줄을 독립된 Flex 행(`row` 및 `row-small`)으로 분리하여 정렬을 개선했습니다.

### Reflection
- HTML, CSS, JavaScript만으로 유효성 검사 UI와 로직을 구축해보면서, 웹 폼 제어의 원리와 브라우저의 이벤트 동작 방식을 명확하게 이해할 수 있었습니다.