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
### `flex 레이아웃 속성`
#### 적용방법
1. 정렬하고자 하는 부모-저식 대상을 확인한다.
2. 2개 이상의 자식요소가 수평,수직 어느방향으로 정렬되었는지 확인한다.
3. 부모요소에게 `display-:flex` 속성을 먼저 적용한다.
4. 2번에서 확인한 방향을 메인축으로 지정하고 줄바꿈을 설정한다 ``flex-flow`
5. 메인축 정렬, 교차축정렬 속성을 활용하여 마무리한다.
#### 주요속성과 주의사항, 팁
* `display:flex` :정렬 자식들의 부모에게 설정하는 flex시작값
* `flex-flow`: 메인축의 방향과 줄바꿈을 설정하는 묶음값
    * flex-flow에서 설정된 메인축방향에 따라 정렬을 정하는 속성
    * **메인축 row인 경우**: 왼쪽, 가운데, 오른쪽, 양쪽 끝 군등여백
    * **메인축 column인 경우**: 위, 가운데, 아래, 양쪽 끝, 균등여백
    * 왼쪽, 위(start), 가운데(center) 오른쪽, 아래(end)
    * 양쪽 끝(space-between), 균등여백(space-around)
* `ailgn-content: 교차측 2줄 이상 정렬값` , `ailgn-items:교차축 1줄정렬값`
    * flex-flow의 값이 `nowrap`이면 `ailgn-items`
    * flex-flow의 값이 `wrap`이고 2줄 이상이면 `ailgn-conten`
    * **ailgn-content만 space-between, aronnd 값 사용가능**
    * end, startm cnetar은 **ailgn-content, ailgn-items 모두 사용가능**
    * `flex-flow: row nowrap; ailgn-items:flex-end`
        * 해석) 메인축 수평 정렬, 줄바꿈 없음, 교차축 수직(아래방향으로 자식들 배치)정렬
    * `flex-flow: column wrap; ailgn-content:flex-center`
        * 해석) 메인축 수직 정렬, 즐바꿈 있음, 교차축 수평 방향으로 2줄 이상일 때 가운데 정렬
### position
#### position:absolute;
* 피그마 내에서 **오토레이아웃 무시** 기능으로 **부모 프레임 위치에서 상대적으로 위치를 맞췄을 때** 사용
1. 태그 상의 부모 후보들 중에(부모,조상 모두 포함) 원하는 기준 대상을 `positon` 속성으로 설정
2. 1번 기준 설정 완료 후 실제 움직이고 싶은 대상에 absolute 설정해서 `left, right, top, bottom` 선택 옵션을 통해 위치 이동
#### positon:fixed;
* 피그마에서 **오토레이아웃 무시-> 프로토타입 위치(고정)->좌표설정**한 경우 
1. body 태그의 자식 위치로 원하는 고정 목적 태그를 작성한다.
2. body는 기본 태그구조로 `postion:relative;`설정이 필요없다
3. 1번에서 작성한 태그에 `positon:fixed;`와 가까운 좌표값을 입력한다.
## table
### HTML 작성순서와 주의사항
* `table` -> `tr` -> `td` or `th` 필요시 나머지태그들
* tr 가로 1행 태그, td 내용 1칸 열, th 제목 1열
* 표 태그는 table을 제외하곤 크게 으미ㅣ로 나누지 않아 행, 열에 클래스 또는 아이디면을 설정하지 않음, 개별 디자인 시에는 CSS에서 nht수열 선택자를 사용해서 대상을 디자인해야함.
### 표 CSS 디자인시 주의사항
* 표는 border가 기본값 0으로 구분이 안되니 CSS로 구분값 적용하기
* 제목, 내용 열은 height 보다는 padding 상하값으로 상대적으로 여백 설정
* 1행 전체에 동일한 디자인(테두리, 배경색)이 적용되었을 땐 tr에 적용하기
* th, td 열 적용하고 싶은 디자은 `tr > *` 적용하기

