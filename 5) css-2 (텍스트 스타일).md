## 오늘 공부한 것
   * 공부일: 2022.07.23-24
<br>

## 1. CSS   
### 4) 텍스트를 표현하는 스타일   
### (1) 글꼴 스타일   
| 종류 | 설명 |
| -------- | -------- |
| font-family | 글꼴 종류 지정 |
| font-size | 글자 크기 지정 |
| font-style | 글자를 이탤릭체로 표시할지 지정 |
| font-weight | 글자 굵기 지정 |
<br>

① __font-family__   
* 기본 태그: __```font-family: 글꼴 이름```__   

__ex1>__
```
<style>
  h1 {
    font-family: 바탕;
  }
</style>
```

* 2개 이상 글꼴 설정: __```font_family: 글꼴 이름, 글꼴 이름```__   
   * 앞에 글꼴이 없다면 뒤에 글꼴이 적용됨
   * "맑은 고딕" : 2개 이상 단어로 구성된 글꼴일 때 큰 따옴표 사용
<br>

__ex2>__   
```body { font-family: "맑은 고딕", 돋움, 굴림 }```   
<br>
<hr>

② __font-size__   
* 기본 태그: __```font-size: 글자 크기```__   

| 단위 | 설명 |
| -------- | -------- |
| px | 1 픽셀 |
| pt | 1 포인트 |
| em | 알파벳 M의 폭(너비) = 1em = 16px |

__ex>__ : ```font-size: 16px```   
<br>
<br>

③ __font-style__   
* 기본 태그: __```font-style: 글자 스타일명```__   

| 글자 속성 | 설명 |
| -------- | -------- |
| normal | 기본값 |
| italic | 이텔릭체, 주로 사용 |
| oblique | 이텔릭체 |

__ex>__ : ```font-style: italic```   
<br>
<br>

④ __font-weight__   
* 기본 태그: __```font-weight: 글자 크기```__   
* 100~900 사이의 굵기로 표현
* 400이 기본 굵기, 400보다 작으면 가늘게 굵게, 700정도면 적당히 굵게

| 종류 | 설명 |
| -------- | -------- |
| normal | 보통 굵기, 400 |
| bold | 굵게, 700 |
| bolder | 원래보다 더 굵게 |
| lighter | 원래보다 더 가늘게 |
| 숫자 값 | 100~900 사이의 굵기 값 |

__ex>__: ```font-weight: 400```   

<br>
<hr>

### (2) 웹 폰트   
* 웹 폰트를 많이 사용할수록 웹 사이트 로딩이 느릴 수 있음   

#### ① 기본 태그:   
```
@font-face {
  font-family: 글꼴 이름;
  src: 글꼴 파일;
}
```

__② 구글 폰트__ - 언어 선택 - 폰트 선택 - select this style - ```<link>``` 또는 @import   
   * @import링크 복사 - ```<style>``` 태그 바로 다음에 붙여넣기   
   * font-family 부분도 복사/붙여넣기   

__ex>__   
```
<head>
  <style>
    @import url('https://fonts.googleapis.com/css2?family=Nanum+Brush+Script&display=swap');
    
    h1 {
      font-family: 'Nanum Brush Script', 바탕;   → 웹 폰트가 적용 안 될 수 있기에 대체 글꼴
  </style>
</head>
<body>
  <h1>레드향</h1>
  <p>껍질에 붉은 빛이 돌아</p>
</body>
```

<br>
<hr>

### (3-1) 웹 색상   
#### ① color 속성   
* 기본 태그: __```color: 색상;```__   
<br>

#### ② 16진수 표기법   
* #6자리   
* 앞에서부터 두 자리씩 묶어 빨강(R), 초록(G), 파랑(B)의 양으로 표기   
* 하나도 섞이지 않았다면 00, 가득 섞였을 때는 ff로 표시   
   * 000000(검은색) ~ ffffff(흰색)
* 두 자리씩 중복될 경우, 줄여 사용 가능   
   * #ffff00 → #ff0,  #cccccc → #ccc   
<br>

#### ③ hsl / hsla 표기법   
* 3자리 수
* 색상(hue), 채도(saturation), 밝기(light)의 양으로 표기
* 끝의 알파(a) 값으로 투명도 조절 가능
   * hsla(240, 100%, 500% 0.3)
   * 0~1값 : 1은 불투평, 0은 완전 투명
<br>

#### ④ rgb / rgba 표기법
* 3자리 수
* 빨강(R), 초록(G), 파랑(B)의 양으로 표기
* 끝의 알파(a) 값으로 투명도 조절 가능
   * color.rgba(255,0,0,0.3)
   * 0~1값 : 1은 불투평, 0은 완전 투명
<br>


__ex1>__   
```
<head>
  <style>
    h1 {
      font-size:120px;
      color: orange;
    }
  </style>
</head>
<body>
  <h1>레드향</h1>
</body>
```
<br>

__◇ VS Code 색상 팁__   
* color 사각형을 누르면 rgb값이 나오고, rgb값을 누르면 16진수, hsl표기법이 나타남   
* 세로 막대부분을 누르고 조절하면 투명도가 바뀜   

<br>
<hr>

### (3-2) 텍스트 색상  
#### ◆ 텍스트 스타일 속성   
| 종류 | 설명 |
| -------- | -------- |
| color | 글자색 |
| text-decoration | 밑줄 or 취소선 |
| text-transform | 대문자 (텍스트 전체 or 첫 글자) |
| text-shadow | 그림자 효과 |
| letter-spacing | 글자 간격 |
| word-spacing | 단어 사이 간격 |
| text-align | 텍스트 정렬 방법 |
| line-height | 줄 간격 조절 |
<br>

#### ① text-align : 텍스트 정렬   
* 기본 태그: __```text-align: 속성값;```__   
#### ◇ text-align 속성값
| 종류 | 설명 |
| -------- | -------- |
| start | 현재 텍스트 줄의 시작 위치에 맞춰 정렬 |
| end | 현재 텍스트 줄의 끝 위치에 맞춰 정렬 |
| left | 왼쪽 정렬 |
| right | 오른쪽 정렬 |
| center | 가운데 정렬 |
| justify | 양쪽 정렬 |
| match-parent | 부모 요소를 따라 문단 정렬 |

__ex>__   
```
① head 부분
  <style>
    .tstyle {
      text-align: center;
    }
  </style>

② body 적용
  <p class="tstyle">내용</p>
```
<br>

#### ② line-height : 줄 간격 조절
* 기본 태그: __```line-height: 숫자값;```__   
   * 숫자(몇 배, 2.0), 픽셀(px), 퍼센트(%)

__ex>__   
```
① head 부분
  .tstyle {
    line-height: 30px;
  }
```
<br>

#### ③ text-decoration : 밑줄 or 취소선
* 기본 태그: __```text-decoration: 속성값;```__   

#### ◇ text-decoration 속성값
| 종류 | 설명 |
| -------- | -------- |
| underline | 밑줄 |
| overline | 윗줄 |
| line-through | 취소선 |
| none | url링크 밑줄을 지울 때 |

__ex1>__   
```
① head 부분
  .tstyle-2 {
    text-decoration: underline;
  }
  
② body 적용
  <p>내용<span class="tstyle-2">내용</span></p>
```
<br>

__ex2>__: __```none```__: 텍스트 링크의 밑줄을 지울 때 주로 사용   
```
① head 부분
  .a {
    text-decoration: none;
  }

② body 적용
  <p><a href="링크 주소">내용</a></p>
```
<br>

#### ④ text-shadow : 그림자 추가   
* 기본 태그: __```text-shadow: <가로거리> <세로거리> <번짐 정도> <색상>;```__   
   * 가로거리: 양수(+) = 오른쪽  /  세로거리: 양수(+) = 아래   
   * 색상을 따로 지정하지 않으면 글자색과 동일

__ex>__   
```
① head 부분
  h1 {
    text-shadow: 5px 5px 3px #ccc;
  }
```
<br>
<hr>

### (4) 목록 스타일   
#### ◆ 목록 스타일 속성값
| 종류 | 설명 | 예시 |
| -------- | -------- | -------- |
| disc | 꽉 찬 원 모양 | ● |
| circle | 텅 빈 원 모양 | ○ | 
| square | 꽉 찬 사각형 | ■ |
| decimal | 1부터 시작하는 리스트 | 1, 2, 3... |
| decimal-leading-zero | 앞에 0이 붙는 숫자 리스트 | 01, 02, 03... |
| lower-roman | 로마숫자 소문자 리스트 | ⅰ, ⅱ, ⅲ... |
| upper-roam | 로마숫자 대문자 리스트 | Ⅰ, Ⅱ, Ⅲ... |
| lower-alpha 또는 lower-latin | 알파벳 소문자 | a, b, c... |
| upper-alpha 또는 upper-latin | 알파벳 대문자 | A, B, C... |
| none | 리스트나 숫자를 없앤다 (공백) |  |
<br>

#### ① list-style-type : 리스트 형태 변경   
* 기본 태그: __```.클래스명 { list-style-type: 속성값; }```__
   * 축약: __```.클래스명 { list-style: 속성값; }```__   

__ex>__   
```
① head 부분
  <style>
    .mylist {
      list-style-type: square;
    }
  </style>
  
② body 적용
  <ul class="mylist">
    <li>Do it 시리즈</li>
    <li>된다 시리즈</li>
  </ul>
```
<br>

#### ② list-style-image : 이미지로 리스트 만들기   
* 기본 태그: __```list-style-image: url(이미지 파일 경로);```__   

__ex>__   
```
  ul {
    list-style-image: url('image/dot.png');
  }
```
<br>

#### ③ list-style-position : 리스트 들여쓰기   
* 기본 태그: __```list-style-position: 속성값;```__   

#### ◆ list-style-position 속성값
| 종류 | 설명 |
| -------- | -------- |
| inside | 리스트를 안으로 들여쓰기 |
| outside | 기본값 |
<br>

__ex>__  
```
① head 부분
  <style>
    .inside { list-style-position: inside; }
  </style>

② body 적용
  <ul class="inside">
    <li>1번째 리스트</li>
    <li>2번째 리스트</li>
  </ul>
```
<br>

#### ④ list-style 동시에 사용   
__ex>__: 따로 사용할 때   
```
  ol {
    list-style-type: lower-alpha;
    list-style-position: inside;
  }
```

__ex>__: 동시에 사용할 때   
```
  ol {
    list-style: lower-alpha inside;
  }
```
<br>

#### ★ 응용하기 (07\list-navi-result.html) ★
```
<style>
  a {
    text-decoration:none;
  }
  nav {
    width: 300px;
    margin: 50px 30px;
  }
  ul {
    list-style: none;
  }
  li {
    border: 1px solid #222;
    padding: 20px;
    margin: 5px;
  }
</style>
```
<br>
<hr>

### (5) 표 스타일   
#### ① 표 제목의 위치를 정해주는 ```caption-side```   
* 기본 태그: __```table { caption-side: 속성값; }```__   

#### ◆ caption-side 속성값
| 종류 | 설명 |
| -------- | -------- |
| top | 표 윗부분에 제목 표시, 기본값 |
| bottom | 표 아랫부분에 제목 표시 |
<br>

#### ◇ 표 목록 부분만 색깔 넣기   
```
  td {
    background-cp;pr: #ccc;
  }
```
<br>

__ex>__   
```
① head 부분
  table {
    caption-side: bottom;
    border: 1px solid black;  → 표 전체 테두리
  }
  td, th {
    border: 1px dotted black;  → 셀 내부 테두리 (검정 점선)
    padding: 10px;             → 셀 테두리와 내용 사이 여백
    text-align: center;
  }
  td {
    background-cp;pr: #ccc;    → 표 목록 부분만 색깔 넣기
  }
  
② body 적용
  <table>
    <caption>표 제목</caption>
```
<br>

#### ② 표와 셀 테두리를 합쳐주는 border-collapse   
: 처음에는 표와 셀 테두리가 분리되어 사이에 공간이 생기는데, 이를 합쳐 테두리가 하나뿐인 표로 만들어줌   
* 기본 태그: __```border-collapse: 속성값```__   

#### ◆ caption-side 속성값
| 종류 | 설명 |
| -------- | -------- |
| collapse | 표와 셀 테두리 하나로 합쳐서 표시 |
| seperate | 표와 셀 테두리 따로 표시, 기본값 |
<br>

__ex>__  
```
  table {
    caption-side: bottom;
    border: 1px solid black;
    border-collapse: collapse;
  }
```
<br>
<br>

#### ③ 셀 사이의 여백 지정하는 border-spacing   
* 기본 태그: __```border-spacing: 수평거리 수직거리```__   
