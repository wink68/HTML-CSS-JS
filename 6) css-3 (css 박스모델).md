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
