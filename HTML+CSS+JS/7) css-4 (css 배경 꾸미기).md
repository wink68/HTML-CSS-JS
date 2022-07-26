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

__ex>__   
