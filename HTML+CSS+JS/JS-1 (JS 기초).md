## 1. 자바스크립트(JS) 기초      
### 1) 자바스크립트의 역할   
* 웹 요소를 제어   
* 웹 애플리케이션을 제작   
* 다양한 라이브러리 사용   
* 서버 개발   
<br>

### 2) 웹 브라우저가 자바스크립트를 만났을 때   
### (1) 웹 문서 안에 자바스크립트 작성   
* ```<script> </script>``` 태그 사이에 자바스크립트 소스 작성   

* __주로 ```</body>``` 태그__ 앞에 작성


__ex>__   
```
   <body>
	<h1 id="heading">자바스크립트</h1>
	<p id="text">위 텍스트를 클릭해 보세요</p>

	<script>
	  var heading = document.querySelector('#heading');
	  heading.onclick = function() {
	  heading.style.color = "red";
	  }
	</script>
   </body>
```

### (2) 외부 스크립트 파일 연결해서 작성하기   
* 기본 태그 : __```<script src="외부 스크립트 파일 경로"></script>```__   
* __```확장자 *.js```__ 로 저장   

__ex>__   
```
   <body>
	<h1 id="heading">자바스크립트</h1>
	<p id="text">위 텍스트를 클릭해 보세요</p>
	
	<script src="js/change-color.js"></script>
   </body>
```
<br>
<hr>

### 3) 기본 입출력 방법   
### (1) 알림창 출력 (alert)   
* 기본 태그 : __```alert("메세지" or 변수명)```__   

* __확인 버튼__ 만 출력   
<br>

__ex> 변수명__   
```
   <script>
     var toDay = new Date();
     alert(toDay);
   </script>
```
<br>

### (2) 확인 창 출력 (confirm)   
* 기본 태그 : __```confirm("메세지")```__ 
  
* __확인 버튼 & 취소 버튼__ 출력 → 선택 여지 제공   

__ex>__   
```
   <script>
	  var reply = confirm("정말 배경 이미지를 바꾸겠습니까?");
   </script>
```
<br>

### (3) 입력받는 창   
* 기본 태그 : __```prompt(메세지)```__ 또는 __```prompt(메시지, 기본값)```__   

__ex>__   
```
   <script>
	  var name=prompt("이름을 입력하세요.", "아무개");
   </script>
```
<a href="#"><img src=https://user-images.githubusercontent.com/108077414/183266933-eb44ffe8-8d16-45b9-a308-55f53ed1d7b8.jpg width="400px" alt="box model"></a>   

<br>

### (4) 웹 브라우저 화면에 출력   
* 기본 태그 : __```document.write("메시지");```__   

* 단순히 브라우저 화면에서 결과값을 확인하는 용도로 많이 사용   
<br>

__ex> 제목 표시하기__   
```
   <script>
	  document.write("<h1>어서오세요</h1>");
   </script>
```
<br>

__ex> 이름 받아서 표시하기__   
```
   <script>
	  var name = prompt("이름을 입력하세요.");   // 프롬프트 창에서 입력 → name 변수에 저장
	  document.write("<b><big>" + name + "</big></b>님, 환영합니다.");
   </script>
```
<a href="#"><img src=https://user-images.githubusercontent.com/108077414/183267240-88c3f5e5-99c3-4427-81ea-f3c41f284580.jpg width="300px" alt="box model"></a>   

<br>

### (5) 콘솔 창에 출력하는 __```console.log()문```__   
* 기본 태그 : __```console.log(내용);```__   
* 웹 개발자 도구창에 있는 콘솔 창에 표시됨   
* 콘솔창 단축키 : __```ctrl + shift + j```__   

__ex>__
```
   <script>
	  var name = prompt("이름을 입력하세요.");   // 프롬프트 창에서 입력 → name 변수에 저장
	  console.log(name + "님, 환영합니다.");
   </script>
```

<br>
<hr>

### 4) 자바스크립트 가이드   
* 자바스크립트 코딩 규칙 = 스타일 가이드 = 코딩 컨벤션 = 코딩 스타일 = 표준 스타일    

#### (1) 코드 들여쓰기   
#### (2) 문장 끝에 세미콜론(;)으로 끝내기   
* 한 문장에 하나의 소스만 작성   
#### (3) 공백 넣기   
* 공백을 넣어 가독성을 좋게 만들기   
#### (4) 주석 작성   
* 한 줄 주석 : ``//```   
* 여러 줄 주석 : ```/* */```   
#### (5) 식별자 규칙   
* 식별자 = 변수, 함수, 속성 등을 구별하려고 붙인 이름   

* 영문자나 언더스코어(_), 달러 기호($)로 시작   
   * 숫자로 시작 X

* 단어 사이의 공백 X
   * 하이픈(-)이나 언더바(_)로 연결   
   * 두 번째 단어를 대문자 설정   
   * 예약어 사용 X
