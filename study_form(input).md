# 📌 HTML5 `<input>` 태그의 모든 속성과 타입 정리

<br />

## ✅ 1. `<input>` 태그의 모든 속성

| 속성명           | 설명                                                                                                                       |
| ---------------- | -------------------------------------------------------------------------------------------------------------------------- |
| `accept`         | 파일 업로드 시 허용하는 파일 타입 지정 (`image/*, .pdf` 등)                                                                |
| `alt`            | `type="image"`일 때 대체 텍스트 제공                                                                                       |
| `autocomplete`   | 자동완성 기능 활성화 (`on`, `off`, `name`, `email` 등)                                                                     |
| `autofocus`      | 페이지 로드 시 자동으로 포커스 설정                                                                                        |
| `checked`        | `type="checkbox"`, `type="radio"`일 때 기본 선택 상태                                                                      |
| `dirname`        | 입력 방향(`ltr`, `rtl`) 정보를 서버에 전달 (`name.dir` 형식)                                                               |
| `disabled`       | 입력 필드 비활성화 (사용자가 입력 불가)                                                                                    |
| `form`           | `<form>`과 연결 (`form`의 `id`를 값으로 지정)                                                                              |
| `formaction`     | `type="submit"` 또는 `type="image"`에서 제출할 URL 지정                                                                    |
| `formenctype`    | `type="submit"` 또는 `type="image"`에서 데이터 인코딩 방식 (`application/x-www-form-urlencoded`, `multipart/form-data` 등) |
| `formmethod`     | `GET`, `POST` 등 폼 전송 방식 지정                                                                                         |
| `formnovalidate` | `type="submit"` 또는 `type="image"`에서 폼 유효성 검사 비활성화                                                            |
| `formtarget`     | `type="submit"` 또는 `type="image"`에서 제출 후 열릴 창 지정 (`_blank`, `_self` 등)                                        |
| `height`         | `type="image"`에서 이미지 높이 지정                                                                                        |
| `id`             | 요소의 고유 식별자                                                                                                         |
| `list`           | `<datalist>`와 연결하여 자동완성 목록 제공                                                                                 |
| `max`            | 숫자, 날짜 등의 최대값 제한                                                                                                |
| `maxlength`      | 입력 가능한 최대 문자 수 지정                                                                                              |
| `min`            | 숫자, 날짜 등의 최소값 제한                                                                                                |
| `minlength`      | 입력 가능한 최소 문자 수 지정                                                                                              |
| `multiple`       | `type="file"`에서 다중 파일 선택 허용                                                                                      |
| `name`           | 폼 제출 시 서버에 전달될 이름                                                                                              |
| `pattern`        | 정규 표현식을 사용한 입력 패턴 제한                                                                                        |
| `placeholder`    | 입력 필드의 가이드 텍스트 제공                                                                                             |
| `readonly`       | 읽기 전용 필드로 설정 (값 변경 불가)                                                                                       |
| `required`       | 필수 입력 필드 지정                                                                                                        |
| `size`           | 입력 필드의 크기 (표시되는 문자 수 기준)                                                                                   |
| `src`            | `type="image"`에서 이미지 경로 지정                                                                                        |
| `step`           | 숫자 또는 날짜 입력 시 증가/감소 단위 지정                                                                                 |
| `tabindex`       | 요소의 키보드 탐색 순서 지정                                                                                               |
| `title`          | 입력 필드의 추가 정보 제공 (마우스 오버 시 표시)                                                                           |
| `type`           | 입력 필드의 유형 설정                                                                                                      |
| `value`          | 입력 필드의 초기값 지정                                                                                                    |
| `width`          | `type="image"`에서 이미지 너비 지정                                                                                        |

---

## ✅ 2. `<input>` 태그의 모든 타입

| 타입             | 설명                                                 |
| ---------------- | ---------------------------------------------------- |
| `text`           | 일반적인 단일 줄 텍스트 입력                         |
| `password`       | 비밀번호 입력 (입력값이 마스킹됨)                    |
| `email`          | 이메일 형식 입력 (`@` 포함 필수)                     |
| `search`         | 검색 필드 스타일의 입력 창                           |
| `tel`            | 전화번호 입력 (패턴 검증 가능)                       |
| `url`            | URL 입력 (유효한 형식인지 검증됨)                    |
| `number`         | 숫자 입력 (최소/최대값 설정 가능)                    |
| `range`          | 슬라이더 형태의 숫자 입력                            |
| `date`           | 날짜 선택 입력 (YYYY-MM-DD)                          |
| `month`          | 연-월 선택 입력 (YYYY-MM)                            |
| `week`           | 연-주 선택 입력 (YYYY-Wnn)                           |
| `time`           | 시간 선택 입력 (HH:MM)                               |
| `datetime-local` | 날짜와 시간 입력 (YYYY-MM-DDTHH:MM)                  |
| `color`          | 색상 선택 입력 (컬러 피커 제공)                      |
| `file`           | 파일 업로드 입력 (다중 선택 가능)                    |
| `image`          | 이미지를 버튼처럼 사용하여 폼 제출 가능 (`src` 필요) |
| `checkbox`       | 다중 선택 가능 체크박스                              |
| `radio`          | 그룹 내 단일 선택 가능 라디오 버튼                   |
| `hidden`         | 보이지 않는 숨김 입력 필드                           |
| `submit`         | 폼 제출 버튼                                         |
| `reset`          | 입력 내용을 초기화하는 버튼                          |
| `button`         | 일반 버튼 (스크립트와 함께 사용)                     |

---

📢 **추가 설명**

- `email`, `url`, `number` 등의 타입은 자동으로 유효성 검사가 적용됨.
- `range`, `date`, `color` 같은 입력 타입은 브라우저마다 UI가 다를 수 있음.
- `hidden` 타입은 보이지 않지만 데이터 전송에 활용됨.
