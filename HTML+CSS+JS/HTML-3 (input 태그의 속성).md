## 오늘 공부한 것

## 3. html 입력 양식
### 1) form
### (4) input 태그의 주요 속성
| 종류 | 설명 |
| -------- | -------- |
| required | 입력되지 않았을 때 상태창 표시 |
| pattern | 정해진 패턴에 맞게 입력하도록 패턴 설정 |
| readonly | 사용자가 텍스트를 읽을 수만 있게 |
| autofocus | 자동으로 커서가 위치하도록 |
| placeholder | 입력란 힌트 내용 표시 |
| select, option | 선택 항목 생성 |

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
: required (01:02)   
: pattern (04:30)   
<br>

#### ③ readonly   
: 사용자가 지울 수 없고 읽을 수만 있는 텍스트 생성   
* 기본 태그 : ```<input type=텍스트-입력-필드 readonly>```

__ex>__   
```
  <label for="prod">주문 상품</label>
  <input type="text" id="prod" value="상품용 3KG" readonly>   
```
<br>

#### ④ autofocus
: 자동으로 커서가 위치하도록   
```
  <label for="user-name">이름 </label>
  <input type="text" id="user-name" required autofocus>
```

#### ⑤ placeholder   
: 입력란 힌트 내용 표시   

```
  <label for="uid">아이디</label>
  <input type="text" id="uid" autofocus placeholder="4~10자 사이, 공백없이" required>
  <label for="pwd1">비밀번호</label>
  <input type="password" id="pwd1" placeholder="문자와 숫자, 특수 기호 포함" required> 
```
<br>
<hr>

#### ⑥-1 선택항목 select / option   
: __```value```__ : 서버로 넘겨줄 값   
: __```slected```__ : 처음 보여지는 옵션   
: __```multiple```__ : 2개 이상 옵션 선택할 때   

__ex1>__   
```
  <select>
    <option value="special_3" selected>선물용 3kg</option>
    <option value="special_5">선물용 5kg</option>
    <option value="family_3">가정용 3kg</option>
  </select>
```

__ex2>__   
```
  <select name="drink" multiple>
    <option value="1" selected>콜라</option>
    <option value="2">사이다</option>
    <option value="3">생수</option>
  </select>
```
<br>

#### ⑥-2 데이터 목록 datalist
* 기본 태그:   
```
  <input type="text" list="데이터 목록 id">
  <datalist id="데이터 목록 id">
    <option value="서버로 넘길 값1">선택 옵션1</option>
    <option value="서버로 넘길 값2">선택 옵션2</option>
  </datalist>
```
<br>

__◆ select와 datalist 차이점__
* 수백개 option중 검색으로 찾을 수 있음   
* option에 없는 잘못된 값을 입력할 위험이 존재   
* 수십개의 select박스보다 메모리를 덜 차지하고 속도도 더 빠름   

#### ◇ 참고자료
https://youtu.be/MZkeA62Fo7U (02:34)   
