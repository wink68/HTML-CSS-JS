## 오늘 공부한 것
   * 공부일: 2022.07.20
<br>

### ◇ 참고 자료   
- 마크 다운 기초 문법 : https://naver.me/F5u0mRdo
- 표 만들기: https://poorman.tistory.com/352
- ★ Html, Css, Javascript 참고 예시(태그): www.w3schools.com
<br>

## 1. html
* VS코드 사용법
  * extensions → live server  (chrome창에서 만든 화면 구현)
  * 오른쪽 키 → open with live server
  <br>
  
## 2. html 구조
* 한글 웹 문서   
```<html lang="ko">```

### 1) head 태그 : 웹 문서를 해석하는 데 필요한 내용
   * ```<meta charset="UTF-8">``` : 한글이 깨지지 않고 나오도록
   * ```<title> 내용 </title>``` : 문서 제목
<br>
  
### 2) body 태그 : 화면에 나타나는 내용
```
<body>
  <h1>웹 문서 만들기</h1>
</body>
```

### (1) 내용 태그
* 제목 태그 : ```<hn> 제목 </hn>```   
: n의 숫자가 작을수록 작아짐

* 단락 만들기 : ```<p> 내용 </p>```
* 엔터 (브레이크) : ```<br>```
* 굵게 강조 : ```<strong> 내용 </strong>```   
   → ```<b> </b>```와 다르게 화면 낭독기에서 강조해줌
* 진하게 (볼드) : ```<b> 내용 </b>```
* 기울기 (강조) : ```<em> 내용 </em>```
* 가로줄 : ```<hr>```
<br>
<hr>

### (2) 리스트
* odered list : ```<ol> 순서가 있는 목록 </ol>```
   * ```<ol type="a"> 내용 </ol>``` : a, b, c 리스트
   * 순서가 없는 목록 : ``` <ul> 내용 </ul>```
   * ol 안의 항목 : ```<li> 내용 </li>```
<br>
<hr>
   
### (3) 표 만들기
* 표 : ```<table> 내용 </table>```
* 표 제목: ```<caption> 제목 </caption>```
* 행(줄) : ```<tr> </tr>```
* 셀(칸) : ```<td> </td>```, ```<th> </th>```

```
  <table>
    <caption>표 제목</caption>
    <tr>
        <th>1행 1열</th>
        <th>1행 2열</th>
    </tr>
    <tr>
        <td>2행 1열</td>
        <td>2행 2열</td>
    </tr>
  </table>
```

* 표 테두리
```
<style>
    table {
        border:1px solid #ccc;
        border-collapse: collapse;
    }
    td, th{
        border:1px solid #ccc;
        padding:10px;
    }
```
<br>
<hr>

### (4-1) 이미지 삽입
* 기본 태그   
__```<img src="이미지 파일 경로" alt="대체용 텍스트">```__   
: 대체용 텍스트 : 시각 장애인용 텍스트   

* 하위 폴더에 있는 이미지   
```<img src="하위폴더명/이미지 파일 경로" alt="대체용 텍스트">```   
<br>

* 크기 조절 (width, height)

| 종류 | 설명 | 예시 |
| -------- | :------: | -------- |
| %  | 웹브라우저 창을 기준으로 결정 | width="50%" |
|px  | 픽셀 크기만큼 표시 | width="150" |

<br>

### (4-2) 오디오 삽입
* 기본 태그   
__```<audio src="오디오 파일 경로"></audio>```__   

* 재생 막대 (controls)   
```<audio src="오디오 파일 경로" controls></audio>```   
* 크기 조절 (width, height)
<br>

### (4-3) 비디오 삽입
* 기본 태그   
__```<video src="오디오 파일 경로"></video>```__   

* 재생 막대 (controls)   
* 크기 조절 (width, height)
<br>

* audio, video 태그

| 종류 | 설명 |
| -------- | -------- |
| autoplay | 자동 재생 |
| loop | 반복 재생 |
| muted | 소리 제거 |
| poster="파일 이름" | 비디오 썸네일 사진 |

```
ex>
<audio src="파일 경로" autoplay loop poster="파일 이름"></audio>
```
<br>

### (4-4) embed
: 오디오, 비디오, 이미지 등 다양한 멀티미디어 삽입   
__```<embed src="파일 경로" width="너비" height="높이">```__   

ex>
```
<embed src="medias/salad.mp4" controls width="700" height="500">
```
<br>
<hr>

### (5) 하이퍼링크
* 기본 태그   
__```<a href="링크할 주소">텍스트 or 이미지</a>```__
<br>

* 텍스트 링크   
```
<div>
  <p><a href="링크">텍스트</a></p>
</div>
```

* 이미지 링크
```
<a href="링크"<img src="이미지 주소" alt="대체 텍스트"></a>
```

* ex>   
```
<div id="container">
  <a href="index.html"><img src="images/tangerines.jpg" alt="레드향" width="300"></a>
  <p><a href="embed.html">멀티미디어 삽입하기</a></p>
</div>
```

* 새 탭에서 열리기   
: __```target="_blank"```__
```
<div>
  <p><a href="링크" target="_blank">텍스트</a></p>
```
