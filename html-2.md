## 오늘 공부한 것
   * 공부일: 2022.07.21
## 3. html 입력 양식
### 1) form
* 기본 태그   
```<form [속성="속성값"]>여러 폼 요소</form>```
<br>

* __```form action=""```__   
: 서버로 데이터를 보낼 때
```
ex> 로그인 값을 보낼 때
<form action="http://localhost/login.php">
```
#### ◇ 참고 자료   
https://youtu.be/sFtZdlmgCVY
<br>   
<br>   

### 2) input 태그
: 입력할 때

### (1) 아이디, 비밀번호
* __```text```__ : 한 줄짜리 텍스트 입력
* __```password```__ : 입력된 비밀번호를 감춰줌
```
<form action="">
    <p>아이디 : <input type="text"></p>
    <p>비밀번호 : <input type="password"></p>
</form>
```
<br>

### (2) 레이블 (label)
: 무언가의 __"이름표"__ 라는 걸 나타내기 위해   
→ 아이디나 비밀번호 텍스트를 누르면 커서가 그 곳에 뜨게 된다
```
ex1>
    <label>아이디 : <input type="text"></label>
    <label>비밀번호 : <input type="password"></label>
```
<br>

* label 태그와 form 요소를 따로 쓸 때   
```<label for="id명">레이블명</label>```   
```<input id="id명">```

```
ex1>
    <label> for="user-id">아이디 : </label>
    <input id="user-id" type="text">
```
<br>

* __```submit```__ : 제출 버튼   
```<input type="submit" value="버튼 이름">```
<br>

#### ◇ 참고 자료   
https://youtu.be/_4upG-03td8
<br>
<br>
<hr>

### (3) 다양한 input 태그
| 종류 | 설명 |
| -------- | -------- |
| email | 이메일 주소 입력 |
| tel | 전화번호 입력 |
| required | 입력되지 않았을 때 상태창 표시 |
| pattern | 정해진 패턴에 맞게 입력하도록 패턴 설정 |
| checkbox | 체크 박스 생성 |
<br>

#### ① required
: 값이 입력되지 않고 제출되었을 때, 상태창 표시
```
<p>
  <label>비밀번호 : <input type="password" required></label>
  <input type="submit" value="로그인">
</p>
```

#### ② pattern
: 형식에 맞지 않는 값이 입력되었을 때, 오류 메시지 창 표시
```
<p>
  <label for="phone">연락처 : </label>
  <input id="phone" type="tel" pattern="[0-9]{3}-[0-9]{4}-[0-9]{4}">
</p>
```
#### ◇ 참고 자료   
https://youtu.be/CPB0jYTjujk   
<br>   

#### ③-1 체크박스 checkbox
: 선택지 (다수 선택 가능)
```
<label for="color_blue">
  <input id="color_blue" type="checkbox" value="blue">파란색
</label>
<label for="color_red">
  <input id="color_red" type="checkbox" value="red">빨강색
</label>
```

#### ③-2 radio
: 선택지 (1개만 선택 가능)   
: __name__ : 서버로 전송될 이름   
: __value__ : 서버로 전송될 값
```
<p><b>포장 선택</b></p>
<label><input type="radio" name="gift" value="yes">선물 포장</label>
<label><input type="radio" name="gift" value="no">선물 포장 안함</label>
```
