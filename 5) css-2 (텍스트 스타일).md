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
