## 오늘 공부한 것
   * 공부일: 2022.07.25-26
<br>

## 2. CSS와 박스모델   
### 1) 블록 레벨 요소 vs 인라인 레벨 요소   
#### ① 블록 레벨 요소   
* 한 줄 전체를 차지하는 태그   

__ex>__   
```<div>내일 죽을 것 처럼 <p class="accent">오늘</p>을 살고</div>```   
<br>

#### ② 인라인 레벨 요소   
* 한 줄의 일부분만 차지하는 태그   
* 그 줄에 다른 요소가 들어올 수 있음   

__ex>__   
```<div>내일 죽을 것 처럼 <span class="accent">오늘</span>을 살고</div>```   
<br>
<br>
<hr>

### 2) 박스 모델   
* 콘텐츠 영역 < 패딩(padding) < 박스 테두리(border) < 마진(margin)   
* 확인방법: F12키 → Computed   

__① 콘텐츠 영역__: 실제 내용이 들어가는 부분   
__② 패딩(padding)__: 콘텐츠 영역과 박스 사이의 여백   
__③ 박스 테두리(border)__: 박스의 테두리 두께   
__④ 마진(margin)__: 여러 박스 모델 사이의 여백   

<a href="#"><img src=https://user-images.githubusercontent.com/108077414/180662223-7223a23e-9c1b-47d5-a5d6-6bd97e1636cb.png width="400px" alt="box model"></a>   
<br>
<br>

### (1) 콘텐츠 영역   
#### ◆ ① 콘텐츠 영역의 크기를 지정하는 width, height   
| 종류 | 설명 |
| -------- | -------- |
| 크기 | px나 em 값으로 지정 |
| 백분율 | 부모 요소를 기준으로 백분율(%) 지정 |
| auto | 자동 결정, 기본값 |

__ex>__   
```
  .box1 {
    width: 200px;
    height: 100px;
    padding: 20px;
    border: 10px solid #ccc;  → 실제 총 크기는 200+20+10 = 230
  }
```
<br>

#### ◆ ② 박스 모델의 크기를 계산하는 box-sizing   
* 기본 태그: __```box-sizing: 속성값;```__   

| 종류 | 설명 |
| -------- | -------- |
| border-box | 테두리, 패딩까지 포함해서 총 너빗값 지정 |
| content-box | 콘텐츠 너빗값 지정, 기본값 |

__ex>__   
```
  .box1 {
    box-sizing: border-box;
    width: 200px;             → 실제 총 크기는 200
    height: 100px;
    padding: 20px;
    border: 10px solid #ccc;
  }
```
<br>

#### ◆ ③ 박스 모델 그림자 효과 box-shadow   
* 기본 태그: __```box-shadow: <수평거리> <수직거리> <흐림정도> <번짐정도> <색상> inset;```__   

| 종류 | 설명 |
| -------- | -------- |
| 수평 거리 | 그림자가 가로로 얼마나 떨어져 있는지 / '양수(+) = 오른쪽' |
| 수직 거리 | 그림자가 세로로 얼마나 떨어져 있는지 / '양수(+) = 아래쪽' |
| 흐림 정도 | 생략할 경우 0을 기본값으로 진한 그림자 / 음수 X, 값이 클수록 부드러운 그림자 |
| 번짐 정도 | 기본값 O, 값이 클수록 그림자가 퍼짐 |
| 색상 | 기본값 검정, 1가지 or 공백으로 구분해서 여러개 색상 지정 가능 |
| inset | 안쪽 그림자 생성 |

__ex>__   
```
  .box1 { box-shadow: 2px -2px 5px 0px; }  → 흐림
  .box2 { box-shadow: 5px 5px 15px 5px blue; }  → 흐림, 번짐, 색상까지 지정
```

<br>
<hr>

### (2) 테두리   
#### ◆ 박스 모델 값 지정 방향   
* __시계 방향__: top → right → bottom → left   
<br>

#### ◆ ① 테두리 스타일 ```border-style```   
* 기본 태그: __```border-style: 속성값;```__   

| 종류 | 설명 |
| -------- | -------- |
| none | 테두리가 없다 |
| hidden | 테두리를 감춘다 |
| solid | 실선 테두리 |
| dotted | 점선 테두리 |
| dashed | (점선 같은) 짧은 직선 테두리 |
| double | 이중선 테두리, border-width값 = 두 선 사이의 간격 |
| groove | 창에 조각한 것처럼 표시, 홈이 파인듯한 입체 느낌 테두리 |
| inset | border-collapse: seperate일 경우 창에 박혀있는 것처럼 표시되고, collapse일 경우 groove와 똑같이 표시 |
| outset | border-collapse: seperate일 경우 창에서 튀어나온 것처럼 표시되고, collapse일 경우 ridge와 똑같이 표시 |
| ridge | 창에서 튀어나온 것처럼 표시 |
<br>

#### ◆ ② 테두리 두께 ```border-width```   
* 기본 태그: __```border-width: 속성값;```__   

| 종류 | 설명 |
| -------- | -------- |
| thin, medium, thick | 테두리 두께 지정 |
| px(픽셀) | 픽셀값으로 두께 지정 |

__ex>__   
```
<style>
#box1 { border-width: 2px; }   → 모든 방향
#box2 { border-width: thick thin; }   → thick (위, 아래) / thin (좌우)
#box3 { border-width: thick thin 2px; }   → thick (위) / thin (우 - 왼쪽에도 적용) / 2px (아래)
</style>
```
<br>

#### ◆ ③ 테두리 색상 ```border-color```   
* 기본 태그: __```border-color: 속성값;```__   
* 색상이름, 16진수, rgb 등

__ex>__: border 내에 한꺼번에 사용   
```
p {
  padding: 10px;
  border: 3px dotted blue;
}
```
<br>

#### ◆ ④ 둥근 테두리 ```border-radius```   
* 기본 태그: __```border-radius: 속성값;```__   

| 종류 | 설명 |
| -------- | -------- |
| 크기 | 반지름 크기를 px, em 단위로 설정 |
| 백분율(%) | 현재 요소(가로/세로 너비)의 크기를 기준으로 비율(%) 설정 |
<br>

#### ◇ 이미지의 둥근 테두리   
```
<head>
  <style>
    .circle { border-radius: 50% }
  </style>
</head>
<body>
  <img class="circle" src="images/photo.jpg(이미지 링크)">
</body>
```

#### ◇ 특정 꼭짓점만 둥글게   
* 기본 태그: __```border-특정 위치-radius: 속성값;```__   
* 타원 꼭지점: __```border-특정 위치-radius: <가로 반지름> <세로 반지름>;```__   

__ex1>__   
```
#round1 {
  border: 2px solid blue;
  border-top-left-radius: 20px;    → 왼쪽 위 둥글게
  border-top-right-radius: 20px;   → 오른쪽 위 둥글게
}
```

__ex2>__   
```
.round2 {
  border-bottom-right-radius : 50% 30%;   → 오른쪽 아래 꼭짓점을 가로 50%, 세로 30% 크기로 라운딩
}
```

<br>
<hr>

### (3) 여백 속성   
#### ◆ ① margin 속성   
* 기본 태그: __```margin: 속성값;```__   
* 특정 방향: __```margin-특정 위치: 속성값;```__

| 종류 | 설명 | 예시 |
| -------- | -------- | -------- |
| 크기 | 너비와 높이 → px, em 단위로 설정 | margin: 50px; |
| 백분율(%) | 부모 요소를 기준으로 비율(%) 설정 | margin: 0.1%; |
| auto | display속성에 지정한 값에 맞게 자동 지정 |  |
<br>

#### ◇ margin 중첩 현상   
* 요소를 세로로 배치할 경우, 마진과 미진이 만날 때 큰 쪽 값으로 겹쳐지는 것
   * 50px + 30 px = 50px   

__ex>__: 08\margin-overlap.html 참조   
```
   div {
      width: 200px;
      height: 100px;
      margin: 30px;      → 마진 설정
    }
    #box1 { background: rgb(0, 77, 243); }
    #box2 { background: rgb(255, 72, 0); }
    #box3 { background: rgb(18, 219, 0); }
    
  <div id="box1"></div>   → box1의 아래 마진 30px와 box2의 위 마진 30px이 중첩되어 총 60px이 아닌 30px
  <div id="box2"></div>
  <div id="box3"></div>
```
<br>

#### ◆ ② padding 속성   
* 테두리와 콘텐츠 내용이 바짝 붙지 않기 위해 padding 설정   

<br>

__ex>__: 07\table-css1.html 참조   
```
<style>
 table {
   caption-side: bottom;
   border: 1px solid #222;
   border-collapse: collapse;
 }
 td, th {
   border: 1px solid #222;
   padding: 10px;           → 패딩 설정
 }
</style>
```

<br>
<hr>

### (4) 레이아웃 속성   
#### ◆ ① display 속성   
* 배치 방법 결정 → 블록 레벨 요소 / 인라인 레벨 요소   

| 종류 | 설명 |
| -------- | -------- |
| block | 인라인 레벨 요소 → 블록 레벨 요소 |
| inline | 블록 레벨 요소 → 인라인 레벨 요소 |
| inline-block | 전체 형태는 인라인 레벨을 하되, 안의 각 요소는 블록 레벨 요소로 사용 |
| none | 해당 요소를 화면에 미표시 |
<br>

__ex> 수평 내비게이션 만들기__: 08\display.html 참조   
```
<style>
  nav ul {
    list-style: none;  → 리스트 제거
  }
  nav ul li {
    display: inline-block;
    border: 1px solid #222;
    padding: 20px;
    margin: 0 20px;
  }
</style>
```
<br>

#### ◆ ②-1 float 속성   
* 왼쪽 or 오른쪽 배치

| 종류 | 설명 |
| -------- | -------- |
| left | 해당 요소를 문서의 왼쪽에 배치 |
| right | 해당 요소를 문서의 오른쪽에 배치 |
| none | 좌우 어느 쪽에도 배치 X, 기본값 |

__ex>__: 사진을 문서 왼쪽에 배치   
```
<head>
  <style>
    img {
      float:left;  /* 왼쪽에 떠 있게 */
      margin-right:40px;
    }
  </style>
</head>
<body>
  <img src="images/tree.png">
</body>
```
<br>

#### ◆ ②-2 clear 속성
* float 속성 해제   

| 종류 | 설명 |
| -------- | -------- |
| left | float: left를 해제 |
| right | float: right를 해제 |
| both | float: left와 right 둘 다 해제 |
<br>

#### ◇ float로 3단 레이아웃 만들기   
* 08\3column-result.html, 01\css\3column-result.css 참조   
<a href="#"><img src=https://user-images.githubusercontent.com/108077414/180898329-2336d34d-ef62-44d8-a5cb-0d986ea5e6dd.JPG width="600px" alt="box model"></a>   
<br>

```
#container {
  width:1200px;   /* 내용 전체의 너비 */
  margin:20px auto;  /* 내용을 화면 가운데 배치하도록 좌우 마진을 auto로 */
}
#header{
  width:100%;  /* 부모 요소의 너비와 똑같게 */
  height:120px;  /* 헤더의 높이 */
  background-color:#acacac;
}
#left-sidebar {
  width: 250px;   /* 사이드바의 너비 */
  height:600px;  /* 사이드바의 높이 */
  background-color:#e9e9e9;
  float: left;  /* 왼쪽으로 플로팅 */
}
#contents {
  width: 800px;  /* 본문의 너비 */
  height:600px;   /* 본문의 높이 */
  background-color:#f7f7f7;
  float: left;  /* 왼쪽으로 플로팅 */
}
#right-sidebar {
  width: 150px;   /* 사이드바의 너비 */
  height:600px;  /* 사이드바의 높이 */
  float: left;  /* 왼쪽으로 플로팅 */
  background-color:#e9e9e9;
}
#footer {
  width:100%;  /* 부모 요소의 너비와 똑같게  */
  height:100px;  /* 푸터의 높이 */
  background-color:#888888;
  clear:left;		/* 플로팅 해제 */
}
```

<br>
<hr>

### (5) 웹 요소의 위치 지정하기   
#### ◆ ①
