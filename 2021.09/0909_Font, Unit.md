## 폰트 관련 속성

#### 1. font-size, font-style, font-weight

##### font-size
px이나 em, %를 사용해서 폰트의 크기 설정
기본적으로 웹 브라우저마다 다르지만 CSS가 적용되지 않았을 때에는 16px을 기본으로 한다.

##### font-style
기울임을 준다고 생각하면 쉽다. 폰트의 스타일을 지정해주는 기능을 한다.
italic와 oblique는 미세한 차이가 있으나 거의 동일하다고 생각하면 된다.

##### font-weight
폰트의 굵기 설정. 기본값은 nomal. bold가 속성값의 하나이다.
폰트에 따라서 굵기값 설정의 값, 간격이 달라진다. 

#### 2. font-family
- 글꼴 자체를 변경하기 위해 사용. 지정을 하게 되면 지정한 글꼴로 보여지게 되는데 사용자의 컴퓨터 유무를 모르기 때문에, 여러 개의 폰트를 쉼표로 구분하여 작성한다.
- 첫번째 폰트가 없으면, 그 다음 꺼, 그 다음 꺼 순차적으로 넘어가면서 사용가능한 폰트를 찾아 적용한다.
- 많은 사람들이 사용하지 않는 폰트는 가급적 사용하지 않는 것이 좋다.
- 폰트 이름에 스페이스가 있으면 ''로 감싸주는 것을 권장한다.
- 마지막에 generic-name을 작성해주는 것이 좋다.

#### 3. line-height
- 폰트 사이즈 위 아래로 여백을 포함한 줄 높이
- 폰트 디자이너가 line-height를 지정하기 때문에 폰트 디자인에 따라 그 값이 다르다.
- 숫자, px, em, % 등 사용 가능

#### 4. font와 단축속성(shorthand)
<img src ="https://t1.daumcdn.net/cfile/tistory/231478335869B3A028">

- 여러 개의 property들을 한 줄로 표현할 수 있는 방법

>**Q. attribute 와 property의 차이는 무엇인가?**
A. Attributes는 HTML 텍스트 문서에 존재하지만, property는 HTML DOM 트리에 있는 것이다. 즉, property sns  attribute에 대한 HTML DOM 트리안 에서의 표현이다. attribute는 변하지 않고 default값을 전달한다는 것을 의미한다고 할 수 있다. 반면에 property는 변할 수 있다. 예를 들어 사용자가 체크박스를 체크했거나 input 박스에 텍스트를 넣었거나 JavaScript로 값을 변경하면 property의 값은 변한다.
(추후에 ETC에 별도로 작성)

- font-size, font-family 속성값은 필수
- font-style, font-weight, line-height 추가로 작성 가능
- font-style과 font-weight는 size 앞에 작성해야 한다.
- font-family는 맨 뒤에 작성
```css
.text {
  font-style : italic;
  font-weight : 800;
  font-size : 25px;
  font-family : Georgia, 'Times New Roman', Times, serif;
}

.text{
  color : red;
  font: italic 800 25px Georgia, 'Times New Roman', Times, serif;
}
```
- 위 아래 코드가 동일한 기능을 한다.
- font shorthand에 값을 지정해주지 않은 속성은 initial 값으로 설정되기 때문에 이 점을 숙지하고 조심해야 한다.

#### 5. letter-spacing, word-spacing
- letter-spacing은 글자 간격, word-spacing은 단어 간격을 조정해주는 역할을 한다.
- 기본값(normal)에 지정해주는 값을 더해 글 간격 조정.
- normal값은 폰트를 디자인한 사람이 지정을 한 값
- 음수 지정도 가능하나 많이 사용하지 않는 것을 추천
- 될 수 있으면 가독성 측면에서 필요하지 않을 시에는 사용하지 않는 것이 좋다.
- 숫자, px, em, % 등 사용 가능

#### 6. text-align
- 해당 요소 범위의 정렬 상태를 지정해주는 역할이라고 생각하면 쉬우나, 블럭 요소에 적용이 가능하므로 인라인 요소에는 적용이 안 된다.
- 인라인 요소에 text-align을 적용하고 싶다면, 인라인 요소를 감싸고 있는 상위 요소에 text-align을 지정해준다.

#### 7. text-indent
- 쉽게, 들여쓰기를 해주는 속성.
- 상속이 가능하지만, 별도로 영역에 text-indent를 주었다면 이 영역을 제외하고 상속된다.(예시 Font.html 참고)
- 블럭 요소에만 적용 가능
- px, % 등 사용 가능

#### 8. text-decoration
- 대부분 shorthand 형식으로 작성
    - text-decoration-line
        - 기본값 none
        - underline(밑줄), overline(윗줄), line-through(중간선, 취소선)
        - mutiple로 여러개 사용 가능(단, line끼리 붙여서 작성해야 함)
    - text-decoration-color
        - 기본값 폰트 컬러
        - 설정 시, color와 다른 색을 가진 선을 표시
    - text-decoration-style
        - 기본값 soild(실선)
        - double(두줄선), dotted(점선), dashed(긴 점선), wavy(물결선)
    - text-decoration-thickness

#### 9. word-break
텍스트가 자신의 콘텐츠 박스 밖으로 오버플로 할 때 줄을 바꿀 지 지정
    - normal : 기본 줄 바꿈 규칙을 사용
    - break-all : 한중일 텍스트를 제외한 텍스트(예, 영어)는 콘텐츠 박스 바깥으로 오버플로 되는데 이를 깨고 콘텐츠 박스에 텍스트가 모두 자리하도록 줄바꿈 처리
    - keep-all : 한중일(CJK) 텍스트에서는 줄을 바꿀 때 단어를 끊지 않는다. 비 CJK 텍스트에서는 normal과 동일하므로 기본값을 변경하여 단어의 끊김이 생기지 않도록 줄바꿈X, 오버플로로 표시되도록 처리

#### 10. text-transform
- 한국어는 적용이 되지 않는 속성
- 사용자에게 보이는 형태만 바뀜(실제로 변경을 원한다면, JS 필요)
    - capitalize : 그대로
    - uppercase : 소문자를 대문자로
    - lowercase : 대문자를 소문자로

---

## 단위와 값

#### 1. 숫자, 길이 및 백분율
property가 허용가능한 value가 다르기 때문에 이를 확인하고 맞는 속성값을 작성해야 한다.

#### 2. 절대길이-px
- 기준점이 존재하지 않고, 고정값이라고 생각하면 쉽게 이해가 가능하다.
- 보통 px을 사용하고, cm, in 등 다른 값이 있다는 정도만 알아두기
- 절대길이는 사용자 설정을 따르지 않기 때문에 접근성 문제가 유발될 수 있다. -> font-size 혹은 상대길이 em, rem 등을 사용해 문제를 해결

#### 3. 상대길이-em, 
- 부모의 font-size를 기준으로 설정되는 상대적인 개념의 길이 단위 -> 때문에 부모의 크기가 달라지면 쌍으로 em 단위가 붙은 font-size도 달라진다.
        - 1em은 부모의 font-size
        - 2em은 부모의 font-size의 2배의 크기
- rem은 `root+em`이라는 뜻을 가지고 있다.
- rem은 루트 요소인 html의 font-size를 1rem으로 사용한다. 따라서 중첩이 되는 경우에도 em과 달리 기분값이 변하지 않는다.
- em보다 상대적으로 rem이 편리하고 직관적으로 이해하기가 좋다.
        - 1rem은 root의 font-size

---

#### 오늘부터 쓰는 Today's Journal,
HTML 강의까지는 HTML 문서를 따로 작성하지 않고 예제 코드를 MD 문서에 합쳐서 작성했는데, CSS 강의부터는 예제 HTML, CSS 파일을 동시에 작성하며 분리를 하고 있다. 작성된 코드를 단독적으로 보고 헷갈릴 경우, 바로 Live server로 실행해보며 개념을 다시 한번 익히기 좋다. 앞으로 강의의 내용은 예제 파일과 단순 필기본을 분리해 작성할 예정이다.

당일 2회차 정기시험에서 flex, transition, animation에 대한 문제가 비중있게 출제됐는데 이에 대한 개념 숙지가 미비해 풀이에 어려움을 겪었다. 이후 강의 진도를 나갈 때, 해당 개념에 대한 네카라쿠배 강의는 기본으로 유튜브나 책을 통해 단단히 복습해나가야 할 예정이다. 

현재 property와 attribute에 개념 정리가 부족하고, css 선택자 단독 사용에는 익숙하나, 중첩 혹은 하위 선택자 등 좀 더 심화된 선택자 사용에 미숙하니 이 점을 알아두고 실습에 적용하도록 해야겠다.

이번 주 내로 모든 온라인 강의 수강을 마치고 다음 주, 시험 전날까지는 부족한 개념을 복습하고 개인적으로 가지고 있는 책의 예제 문제를 풀면 실습을 반복하도록 계획을 잡았다.

