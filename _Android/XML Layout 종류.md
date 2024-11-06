## 선형으로 배치 ( LinearLayout )

LinearLayout 배치 규칙

- 가로나 세로 방향으로 나열하는 레이아웃 클래스이다
- `orientation`의 속성에 horizontal이나 vertical 값으로 방향 지정

layout_weight로 여백 채우기

- view에 가중치로 여백을 채울 수 있음
- 같은 영역에 있는 뷰끼리만 여백을 나눈다

뷰 정렬하기 gravity, layout_gravity 속성

- gravity와 layout_gravity 모두 정렬을 하지만, 정렬의 대상이 다름
- gravity의 정렬 대상은 콘텐츠(뷰)

  → TextView의 문자열이 정렬됨

- layout_gravity의 정렬 대상은 뷰 자체

  → TextView 자체가 정렬됨

## 상대 위치로 배치 ( RelativeLayout )

RelativeLayout 배치 규칙

- 상대 뷰의 위치를 기준으로 정렬하는 레이아웃 클래스
- 뷰의 id 값으로 기준을 찾음

ex) android: layout_toRightOf=”@id/testImage”

## 겹처서 배치 ( FrameLayout )

FrameLayout 배치 규칙

- 카드를 쌓듯이 뷰를 추가한 순서대로 위에 겹처서 출력하는 레이아웃 클래스
- 똑같은 위치에 여러 뷰를 겹쳐놓고, visibility 속성을 사용하여 하나의 뷰만 출력할 때 유용함

## 표 형태로 배치 ( GridLayout )

GridLayout 배치 규칙

- 행과 열로 구성된 테이블 화면을 만드는 레이아웃 클래스
- LinearLayout처럼 orientation 속성으로 뷰를 나열하는데, 차이점은 자동으로 줄바꿈을 해줌
- rowCount, columnCount로 나열할 뷰의 개수 지정
- 추가한 뷰의 크기는 기본으로 wrap_content로 지정

> TableLayout과의 차이점?
>

⇒ TableRow에 뷰의 개수를 고정해야함

⇒ 동적으로 셀의 개수가 변하면, 행을 계산해서 TableRow를 지정해줘야 함 , Grid는 방향과 개수만 설정해주면 알아서 행이 결정됨

## 계층 구조로 배치 ( ConstraintLayout )

안드로이드 플랫폼이 아니라 androidx에서 제공하는 라이브러리

```kotlin
// build.gradle
implementation 'androidx.constrantlayout:constraintlayout:2.1.4'
```

layout_width, layout_height 이외의 제약조건이 있음

- 다른 뷰를 기준으로 상대 위치를 설정해줘야 함

복잡한 레이아웃을 단순한 계층구조로 표현할 수 있음

RelativeLayout과 비슷하지만 다양한 화면 크기에 대응할 수 있음

ConstraintLayout의 뷰 위치 지정

- bias 속성을 통해서 위치를 지정할 수 있음

  → layout_constrainHorizontal_bias = “0~1”

- guideline 속성을 통해서 위치를 지정할 수 있음 (축을 지정해주고, 위치값 지정)

  → orientation = “vertical” layout_constraintGuide_percent = “0.8”