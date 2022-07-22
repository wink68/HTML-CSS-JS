## 오늘 공부한 것
   * 공부일: 2022.07.21-22
<br>

### ◇ 참고 자료   
- [caniuse.com](https://caniuse.com/)   
: 브라우저마다 사용 가능한 태그   
: index of features 또는 검색   
: 초록 - 지원, 갈색 - 부분 지원, 빨강 - 미지원   
ex> date input type (~ input type)   

- known issues
: 사용자들이 발견한 문제점
<br>

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
https://youtu.be/sFtZdlmgCVY (05:34, 08:48)
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

* __```textarea```__ : 여러 줄 입력   
: ```cols``` : 글자 수   
: ```rows``` : 줄 수   

__ex>__
```
  <label for="memo">메모</label>
  <textarea id="memo" cols="40" rows="4"></textarea>
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

* __```submit```__ : 제출(전송) 버튼   
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
| submit | 전송 버튼 |
| reset | 리셋 버튼 |
| checkbox | 체크 박스 생성 |
| button | 버튼 생성 |
| image | 이미지 버튼 생성 |
| file | 파일 첨부 버튼 생성 |
| hidden | 화면에 보이지 않지만, 서버로 전송되는 정보 |
<br>

#### ① 전송 / 리셋 버튼
__◇ 전송 버튼 submit__   
: 입력한 정보를 서버로 전송하는 버튼   
* 기본 태그 : ```<input type="submit" value="버튼 이름">```   

__◇ 리셋 버튼 reset__   
: 입력한 정보를 리셋하는 버튼   
* 기본 태그 : ```<input type="reset" value="버튼 이름">```   

__ex>__   
```
<div>
  <input type="submit" value="주문하기">
  <input type="reset" value="취소하기">
</div> 
```
<br>   
<hr>   

#### ②-1 체크박스 checkbox
: 선택지 (다수 선택 가능)
```
<label for="color_blue">
  <input id="color_blue" type="checkbox" value="blue">파란색
</label>
<label for="color_red">
  <input id="color_red" type="checkbox" value="red">빨강색
</label>
```

#### ②-2 radio
: 선택지 (1개만 선택 가능)   
: __name__ : 서버로 전송될 이름   
: __value__ : 서버로 전송될 값
```
<p><b>포장 선택</b></p>
<label><input type="radio" name="gift" value="yes">선물 포장</label>
<label><input type="radio" name="gift" value="no">선물 포장 안함</label>
```
#### ◇ 참고 자료   
- name : https://youtu.be/sFtZdlmgCVY (08:30)   
: 서버로 전송할 때, name으로  값이 전송됨
<br>   
<hr>   

#### ③-1 number
: 화살표로 갯수 조절
```
<p><u1>
  <li>
    <label>선물용 3kg <input type="number" min="0" max="5" value="1">개 (최대 5개)</label>
  </li>
</ul></p>
```

#### ③-2 range
: 막대로 갯수 조절
```
<p><u1>
  <li>
    <label>가정용 3kg <input type="range" min="0" max="5" value="1">개 (최대 5개)</label>
  </li>
</ul></p>
```

* __number / range 속성__   

| 속성 | 설명 |
| -------- | -------- |
| min | 갯수 최소값 |
| max | 갯수 최댓값 |
| value | 초기값 |

<br>
<hr>

#### ④ 날짜 / 시간 / 범위
: 사용자 시간

| 속성 | 설명 |
| -------- | -------- |
| date | 날짜 (연, 월, 일) |
| month | 날짜 (연, 월) |
| week | 날짜 (연, 주) |
| time | 시간 (시, 분, 초, 분할 초) |
| datetime | 국제 표준 시간 (연, 월, 일, 시, 분, 초, 분할 초) |
| datetime-local | 시간 (연, 월, 일, 시, 분, 초, 분할 초) |
<br>

* __날짜__

```
<h1>날짜 설정하기</h1>
<input type="date">
<input type="month">
<input type="week">
```

* __시간__

```
<h1>시간 설정하기</h1>
<input type="time">
<input type="datetime-local">
```

* __범위 제한하기__
```
<h1>범위 제한하기</h1>
<input type="date" min="2020-02-01" max="2020-02-15">
<input type="time" min="14:00" max="16:00"
```

<br>
<hr>

#### ⑤ 버튼 생성
* __버튼 생성__   
   * 기본 태그 : ```<input type="button" value="버튼에 표시할 내용">```   
   * 자바스크립트 함수 ```window.open()```   

__ex>__   
```
<form>
  <input type="button" value="공지 창 열기" onclick="window.open('notice.html')">
</form>
```
<br>

* __이미지 버튼 생성__
   * 기본 태그 : ```<input type="image" src="이미지 경로" alt="대체 텍스트">```   

__ex>__   
```
<fieldset>
  <label>아이디: <input type="text" id="user_id" size="10"></label>
  <label>비밀번호: <input type="password" id="user_pw" size="10"></label>
  <input type="image" src="images/login.png" alt="로그인">
</fieldset>
```
<br>

* __파일첨부 버튼 생성__
   * 기본 태그 : ```<input type="file">```   

__ex>__   
```
<fieldset>
  <legend>반품 정보</legend>
  <p>만일 수령한 상품에 문제가 있다면 즉시 <b>반품 신청</b>해 주세요.</p>
  <p>반품 신청시 상품의 상태를 사진으로 첨부해 주세요.</p>
  <hr>
  <input type="file">    
</fieldset>
```

<br>
<hr>

#### ⑥ hidden
: 화면에 보이지 않지만, 서버로 전송되는 정보
ex> 회원가입한 시간, 지역, 들어온 경로 등
<br>

* 기본 태그 : ```<input type="hidden" name="이름" value"서버로 전송할 값">```

__ex>__
```
  <input type="hidden" name="url" id="url" value="사이트를 통한 직접 로그인">
  <label>아이디: <input type="text" id="user_id" size="10"></label>
  <label>비밀번호: <input type="password" id="user_pw" size="10"></label>
  <input type="submit" value="로그인">
```
