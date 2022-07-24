## 오늘 공부한 것
   * 공부일: 2022.07.25
<br>

## 1. CSS와 박스모델   
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

#### (1) 콘텐츠 영역   
#### ◆ 콘텐츠 영역의 크기를 지정하는 width, height   
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

#### ◆ 박스 모델의 크기를 계산하는 box-sizing   
* 기본 태그: __```box-sizing: 속성값```__   

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

#### ◆ 박스 모델 그림자 효과 box-shadow   
* 기본 태그: __```box-shadow: <수평거리> <수직거리> <흐림정도> <번짐정도> <색상> inset```__   

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

#### (2) 테두리   
#### ◆ 박스 모델 값 지정 방향   
* __시계 방향__: top → right → bottom → left   

