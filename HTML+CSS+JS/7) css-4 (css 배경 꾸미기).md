## 오늘 공부한 것
   * 공부일: 2022.07.26
<br>

## 3. CSS와 배경 꾸미기   
### 1) 배경색과 배경 범위 지정하기   
#### (1) background-color 속성   
* 기본 태그: __```background-color: 속성값;```__   

__ex>__   
```
<style>
  body { background-color: #fff8dc; }
</style>
```
<br>

#### (2) 배경색의 적용범위 조절 background-clip 속성   
* 기본 태그: __```background-clip: 속성값;```__   

| 종류 | 설명 |
| -------- | -------- |
| border-box | 테두리까지 배경색 지정, 기본값 |
| padding-box | 테두리를 뺀 패딩까지 배경색 지정 |
| content-box | 콘텐츠 영역에만 배경색 지정 |

__ex>__   
```
  <style>
    .desc {
      border:5px dotted #222;
      background-color:#ffd9a0;
      width:350px;
      padding:20px;
      margin-right:20px;
      float:left;
    }
    #clip-border {
      background-clip: border-box;
    }
    #clip-padding {
      background-clip: padding-box;
    }
    #clip-content {
      background-clip: content-box;
    }
  </style>
```

<a href="#"><img src=https://user-images.githubusercontent.com/108077414/180907668-5c1d2a61-790d-45df-814c-7f0aada7ccb2.JPG width="800px" alt="box model"></a>   

<br>
<hr>

### 2) 배경 이미지 지정하기   
#### (1) 배경 이미지 넣는 background-image 속성   
* 기본 태그: __```background-image: url('이미지 파일 경로');```__   
* 반복해서 웹 화면 전체에 가득 채워짐   

__ex>__   
```
<style>
  body {
    background-image :url('images/bg1.jpg');
  }
</style>
```
<br>

#### (2) 배경 이미지 반복 방법   
* 기본 태그: __```background-repeat: 속성값;```__   

| 종류 | 설명 |
| -------- | -------- |
| repeat | 전체 화면에 가득차게 반복, 기본값 |
| repeat-x | 가로로 가득차게 반복 |
| repeat-y | 세로로 가득차게 반복 |
| no-repeat | 한 번만 표시, 반복 X |
<br>

#### (3) 배경 이미지의 위치 조정
* 기본 태그: __```background-position: <수평 위치> <수직 위치>;```__   

__ex>__   
```
<style>
  li {
    background-image:url('images/book-icon.png');  /* 배경 이미지 파일 */
    background-repeat:no-repeat;  /* 배경 이미지 반복 안함 */
    background-position:left center;  /* 배경 이미지 위치 */
    padding-left:50px;  /* 왼쪽 패딩 (박스 모델) */
    line-height:40px;  /* 줄간격 */
  }
</style>
```

<a href="#"><img src=https://user-images.githubusercontent.com/108077414/180910089-6cf99275-ab42-4c05-af8d-13dea0d79a71.JPG width="400px" alt="box model"></a>   

<br>

#### (4) 배경 이미지의 위치 고정
* 기본 태그: __```background-attachment: 속성값;```__   

| 종류 | 설명 |
| -------- | -------- |
| scroll | 스크롤바를 움직이면 배경 이미지도 스크롤 위치에 따라 사라짐, 기본값 |
| fixed | 스크롤바를 내려도 위치 고정 |
<br>

#### ◆ 응용: background 속성 한꺼번에 사용   
__ex>__: 따로 사용   
```
body {
  background-image: url('images/bg4.png');
  background-repeat: no-repeat;               /* 이미지 반복 X */
  background-position: center bottom;         /* 이미지 중앙 아래 배치 */
  background-attachment: fixed;               /* 이미지 고정 */
}
```

__ex>__: 속성 한꺼번에 사용   
```background: url('image/bg4.png') no-repeat center bottom fixed;```   

<br>

#### (5) 배경 이미지 크기 조절 background-size   
* 기본 태그: __```background-size: 속성값;```__   

| 종류 | 설명 |
| -------- | -------- |
| auto | 원래 이미지 크기, 기본값 |
| contain | 요소 안에 배경 이미지가 다 들어오도록 설정 |
| cover | 배경 이미지로 요소 전체를 채우도록 설정 |
| 크기 | 가로, 세로 값을 px(픽셀)로 지정 가능, "값 하나만 할 경우 = 가로" |
| 백분율 (%) | 배경 이미지가 들어갈 요소를 기준으로 설정 |
<br>

__ex>__: 왼쪽 위부터   
① auto, ② 가로 200px, ③ 가로 50%, ④ 가로 세로 100%, ⑤ contain, ⑥ cover   
```
  #bg1 { background-size:auto;}       /* 원래 배경 이미지 크기로 표시 */
  #bg2 { background-size:200px;}      /* 너비는 200px, 높이는 자동 계산 */
  #bg3 { background-size:50%;}        /* 배경 이미지 너비는 요소 너비의 50%, 높이는 자동 계산 */
  #bg4 { background-size:100% 100%;}  /* 배경 이미지 너비와 높이는 요소 너비의 100%, 요소 높이의 100% */ 
  #bg5 { background-size:contain;}    /* 요소 안에 배경 이미지가 다 보이도록 표시 */
  #bg6 { background-size:cover;}      /* 요소를 완전히 덮도록 배경 이미지 표시 */
```

<a href="#"><img src=https://user-images.githubusercontent.com/108077414/181079660-584655e9-dcaa-4906-9397-b32964dacdf7.JPG width=50% alt="box model"></a>   

<br>
<hr>

### 3) 그라데이션 효과      
#### (1) 선형 그라데이션   
* 기본 태그: __```linear-gradient(to <도착방향 또는 각도>, <색상1 색상2>);```__   
* 가로, 세로, 대각선 방향으로 나타나는 그라데이션   
<br>

__ex1>__   
```
.grad {
 	background: blue;
  background: linear-gradient(to right bottom, blue, white);      /* 왼쪽 위에서 오른쪽 아래 방향으로, 파랑에서 흰색으로 */
}
```
<a href="#"><img src=https://user-images.githubusercontent.com/108077414/181079783-0ef46397-654a-4aba-a28f-44e58e226188.JPG width=400 alt="box model"></a>   

<br>

__ex2>__: 선형 그라데이션 (각도)   
* 맨 위를 0도로 시계 방향으로 90도, 180도, 270도   
```
.grad { 
  background: #f00;                                    /* CSS3를 지원하지 않는 브라우저용 */
  background: linear-gradient(45deg, #f00, #fff);      /* 45도 (오른쪽 위)방향으로, 빨간색에서 흰색으로 */
}
```
<a href="#"><img src=https://user-images.githubusercontent.com/108077414/181080636-7e04a798-6e79-4837-804a-f2864be587f0.JPG width=400 alt="box model"></a>   

<br>

#### (2) 원형 그라데이션   
* 기본 태그: __```;```__   
* 원의 중심에서부터 동심원을 그리며 나타나는 그라데이션   


