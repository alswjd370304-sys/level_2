# HTML+CSS 26/06/22~
## HTML. CSS로 웹&앱 문서 제작하는 순서
1. 제작 문서에 맞게 의미 있는 HTML 태그 구성하기
2. CSS 파일을 styles폴더에 별도로 생성하기
3. 1번에서 제작한 태그 중 디자인하려는 대상확인하기
4. 3번 대상을 선택자로 작성하고 다지안 목적에 맞게 속성:값 작성하기
## 선택자 {속성:값;}
### 선택자 {속성:값; 속성:값;}
# 선택자종류
## 태그 선택자
* 태그명을 선택자로 사용하는 선택자
* `<h1></h1>` -> `h1 {속성:값;}`
## 클래스 선택자
* 반복되는 클래스명을 사용하는 선택자
* `<h1 class="title"></h1>` -> `.title {속성:값;}`
## 자식 선택자
*특정 부모 안 자식을 사용하는 선택자
* `<h1><span></span></h1>` -> `h1 > span {속성:값;}`
## 형제선택자 + 와 ~
* `<div> <a>1</a> <em>2</em> <del>3</del> </div>`
* `div > a+em {}` 해석) 부모div의 자식 a의 인접형제
* `div > a~del {}` 해석) 부모div의 자식 a의 형제 del 선택
* `+`는 바로 옆에 있는 형제태그만 인식한다
* `~`은 바로 옆 형제 포함 그 뒤에 있는 모든 형제태그들을 인식한다
# 자주쓰는 웹 글꼴 주소
## Noto Sans KR
* <link href="https://fonts.googleapis.com/css2?family=Noto+Sans+KR:wght@100..900&display=swap" rel="stylesheet">
## pretendard
* <link rel="stylesheet" as="style" crossorigin href="https://cdn.jsdelivr.net/gh/orioncactus/pretendard@v1.3.9/dist/web/static/pretendard-dynamic-subset.min.css" />
# CSS 속성과 값, 활용 방법
## background
* `background-color`:배경색상, 실제 배경색이 없어도 영역구분용으로 사용
* `background-img:url()`: 배경이미지, url() 안에는 상대경로 작성하기
* `background-repeat`: 배경이미지반복설정, 배경이미지가 **작은 경우**에만 체크
* `background-size`: 배경이미지크기설정, 배경이미지가 들어간 요소보다 이미지가 작거나 클경우
* `background-position`: 배경이미지위치설정, **size와 함꼐 무조건 사용하기, x,y순서로 작성**
* `background-attachment`: 배경이미지스크롤속성, 스크롤 이동 시 이미지 고정시키고 싶을 때만 사용
* (위) 작성시 주의사항, 배경이미지는 일반 이미지태그과 다르게 요소의 크기가 자동으로 연장되지 않으므로 **반드시 width, hright 크기를 함꼐 작성!**
## font
* `font-famliy`: 글꼴설정, 2개 이상 글꼴 작성하기
* `font-size`: 글자크기, px->em으로 전환해서 작성
* `font-weight`: 글자굵기, 보통(400) +-100설정
* `letter-spacing`:자간, -2% -> -0.02em
* `line-height`: 행간, 100% 0-> 1, 150%->1.5
* `color`: 글자색상
## box
* `border`: **두께, 모양 색상** 순서로 작성 예) 1px solid #000;
* `padding`: 피그마의 오토레이아웃 패딩과 동일, **부모와 자식 사이의 안쪽여백**
* `margin`: 피그마의 오토레이아웃 간격과 동일, **형제와 형제 사이의 바깥쪽 여백**
* `width`: 가로크기(px, %, vW)
    * 피그마 w 내용에 맞추기 설정 예시) width: max-content;
    * 피그마 w 채우기 설정 시 예시) width:100%
    * 피그마 w 고정값 설정예시) width: 500px (직접)
* `height`: 세로크기 (width와 설명 같음)
* `border-radius`: 모서리 둥글기(피그마의 모서리 반경이랑 같음), px단위
## layout
### 수평, 수직 정렬하기
* `text-align`: 수평정렬(left, conter, rigint, justify)
* `line-height`:  글자가 한 줄이고 높이가 고정일 때 높이값 px를 넣어 수직 중앙정렬설정