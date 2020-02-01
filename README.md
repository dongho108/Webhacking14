# Webhacking14
워게임14번문제 풀이 입니다.

# 14번 문제 풀이

Javascript를 해석할 수 있는지 묻는 문제이다.

1. 먼저 아무 값(admin)이나 입력한다.  그러면 “https://webhacking.kr/challenge/js-1/?input_pwd=admin”가 나온다. 
2. 그리고 개발자도구로 소스코드를 확인해 본다.
소스코드

```javascript
function ck(){
  var ul=document.URL;
  ul=ul.indexOf(".kr");
  ul=ul*30;
  if(ul==pw.input_pwd.value) { location.href="?"+ul*pw.input_pwd.value; }
  else { alert("Wrong"); }
}
```
3. 빈칸에 써 넣는 값이 pw.input_pwd.value에 해당하는 것을 알게 되었다.
4. 그리고 패스워드는 ul의 값과 같아야 한다.
5. 개발자도구 console창에 
```javascript
var ul=document.URL;
ul=ul.indexOf(".kr");
ul=ul*30; 
```
를 넣고 실행한다. 그랬더니 ul의 값이 540이 나왔고 540을 입력하니 문제가 풀린다.



