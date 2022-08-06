## 1. 자바스크립트(JS) 기초      
### 1) 자바스크립트의 역할   
* 웹 요소를 제어   
* 웹 애플리케이션을 제작   
* 다양한 라이브러리 사용   
* 서버 개발   
<br>

### 2) 웹 브라우저가 자바스크립트를 만났을 때   
#### (1) 웹 문서 안에 자바스크립트 작성   
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

#### (2) 외부 스크립트 파일 연결해서 작성하기   
