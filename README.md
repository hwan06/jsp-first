## jsp 첫걸음
## 지역변수와 전역변수
![image](https://github.com/hwan06/jsp-first/assets/114748934/fed1f861-dab6-4ccf-a6a3-0b19c5330f15)     
**<%!...%>** 안에서 선언하면 전역변수, **<%...%>** 안에서 선언하면 지역변수이다.     

**지역변수** : 함수 **안**에서 선언, **정의된 블럭내에서만 사용**할 수 있는 변수.    
<b>전역변수</b> : 함수 **밖**에서 선언, 문서 내 **어느 곳에서든 호출 가능**한 변수.      

![image](https://github.com/hwan06/jsp-first/assets/114748934/cc1ff69f-460f-431e-a21f-6eb05448d07b)   
페이지를 새로고침하면 전역변수의 수는 증가하지만 지역변수의 수는 증가하지않는다.   

**이유**: 전역변수는 함수 밖에서 선언 되기 때문에 함수를 호출해도 변수의 초기화가 일어나지 않지만    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; 지역변수는 함수내에서 선언 되었기 때문에 함수가 호출될때마다 초기화 된다.

## for문 사용 예제

1. 두 사람의 시험점수 총합과 평균을 각각 배열방에 저장.
``` jsp
<% // 스크립틀릿

 String name[] = {"김미영", "김민성"};
 int score[][] = {{80,90,70},{50,25,30}};
 float avg[] = new float[2];
 int total[] = new int[2];
 
 for(int i = 0; i < 2; i++){
	 for(int j = 0; j < 3; j++){
		 total[i] += score[i][j];
	 }
	 avg[i] = total[i]/3;
 }
  
%>
```
2. 출력해주기
``` jsp
 <h1>성적처리</h1>
 <b>김미영의 국어점수: </b><%=score[0][0]+"점"%><br> 
 <b>김미영의 영어점수: </b><%=score[0][1]+"점"%><br>
 <b>김미영의 수학점수: </b><%=score[0][2]+"점"%><br>	
 <b>김미영의 총점: </b><%=total[0]+"점"%><br>
 <b>김미영의 평균: </b><%=avg[0]+"점"%><br><br>
 
 <b>김민성의 국어점수: </b><%=score[1][0]+"점"%><br> 
 <b>김민성의 영어점수: </b><%=score[1][1]+"점"%><br>
 <b>김민성의 수학점수: </b><%=score[1][2]+"점"%><br>	
 <b>김민성의 총점: </b><%=total[1]+"점"%><br>
 <b>김민성의 평균: </b><%=avg[1]+"점"%><br>
```
![image](https://github.com/hwan06/jsp-first/assets/114748934/f8c9f676-6a96-4432-a851-0fda36d93a78)


## if문 사용 예제
``` jsp
<%
	String input_id = "abc";
	String input_pw = "1234";
	
	String id = "abc";	
	String pw = "1234";
	
	String answer = "";
	
	if(input_id.equals(id)){
		if(input_pw.equals(pw)){
			answer = "방문을 환영합니다.";
		}else{
			answer = "비밀번호가 틀렸습니다.";
		}
	}else{
		answer = "회원 가입을 해주세요.";
	}
%>
```
사용자 입력 id, pw를 정하여 if문을 통해 출력값 출력하기
``` js
<b>로그인 메시지: </b>&nbsp;<%=answer %>
```
![image](https://github.com/hwan06/jsp-first/assets/114748934/1e1b9f63-8860-44f8-ba15-0eb83f65b252)
## switch문 사용 예제
대학교의 학년을 저장할 배열방을 만들고 if문을 통해 최대 4까지만 값을 받을 수 있도록 함.
``` jsp
<%
	String year[] = {"fresh man", "sophomore", "junior", "senior"};
	int n = 4;
	
	if(n < 5){
	switch(n){
		case 1:
		out.print(year[0] + " 입니다");
		break;
		case 2:
		out.print(year[1] + " 입니다");
		break;
		case 3:
		out.print(year[2] + " 입니다");
		break;
		case 4:
		out.print(year[3] + " 입니다");
		break;
		}
	}else{
		out.print("잘못된 학년");
	}
%>
```
![image](https://github.com/hwan06/jsp-first/assets/114748934/b80de9b9-2d8a-43a1-a72f-c55eb718cd7f)
