<br/><h1 align="center">학생 관리 시스템</h1>
MySQL과 spring 프레임워크를 사용하여 구축한 학생 관리 시스템이다.<br/>
학생 정보 관리 시스템의 주요 기능으로는 회원가입, 로그인, 공지사항 확인, 수강신청 등이 있다.<br/>
Mybatis, JSP(with Java) 사용<br/>
프로젝트 시연 영상 링크: [학생관리시스템-YouTube](https://www.youtube.com/watch?v=h9YNuLTT2PE&t=3s)<br/><br/><br/>

## 주요 기능 페이지


### 로그인 및 회원가입
![image](https://user-images.githubusercontent.com/45943080/103730623-9db81b80-5026-11eb-9cd4-9c43a11db279.png)<br/>
회원가입 정보를 입력하고 아래의 초록색 회원가입 버튼을 클릭하면 회원가입이 완료된다. <br/>
회원 가입 된 학생의 데이터는 테이블은 “create_stu에 삽입된다. <br/>
회원가입을 클릭하면 화면은 다시 맨 처음 로그인 화면인 홈 화면으로 이동한다.<br/><br/>
![image](https://user-images.githubusercontent.com/45943080/103730632-a4df2980-5026-11eb-96e2-db6491f832fd.png)<br/>
처음 주소를 입력하면 위처럼 로그인 창이 뜬다. <br/>
회원가입을 하기 전에는 로그인에 학생 ID와 비밀 번호를 입력하면 로그인 실패라는 메시지가 뜨도록 했다. <br/><br/>
![image](https://user-images.githubusercontent.com/45943080/103730634-a7418380-5026-11eb-8429-74d8f0411ecd.png)<br/>
회원으로 등록된 학생이 로그인을 하면 아래의 이미지와 같이 화면이 나타난다. <br/>
이때 확인을 클릭하면 바로 시스템의 공지사항 화면으로 url이 넘어간다. <br/><br/><br/>

### 공지사항
![image](https://user-images.githubusercontent.com/45943080/103730686-c4765200-5026-11eb-8cfd-f218765eae57.png)<br/>
![image](https://user-images.githubusercontent.com/45943080/103730694-c7714280-5026-11eb-9c05-cba574639938.png)<br/>
MySQL의 “notice” 테이블에 저장된 데이터를 출력하는 공지사항 페이지이다.<br/><br/><br/>

### 수강신청 
![image](https://user-images.githubusercontent.com/45943080/103730724-d8ba4f00-5026-11eb-8706-e1ac53fc0286.png)<br/>
과목별 정보를 해당 화면에 lectureVO를 값을 나열하여 출력하였다.<br/>
수강신청을 하면 학번인 student.id와 “applist” 테이블에 필요한 lectureVO 데이터가 “applist” 테이블에 추가된다.<br/><br/><br/>

### 개인정보 조회
![image](https://user-images.githubusercontent.com/45943080/103730753-ea035b80-5026-11eb-8501-756fbda58f42.png)<br/>
학생이 처음 회원가입을 할 때 입력했던 정보를 보여주는 개인 정보 조회 페이지이다. <br/>
이름, 학번, 학부, 그리고 이메일 주소가 출력된다. <br/>
해당 데이터는 MySQL의 “create_stu” 테이블에서 불러온다.<br/><br/><br/>

### 강의 시간표 출력
![image](https://user-images.githubusercontent.com/45943080/103730781-f982a480-5026-11eb-90f2-67cc927e8abe.png)<br/>
이번 학기 신청 과목의 시간표를 출력하는 페이지이다. <br/>
수강신청에서 강의를 신청하고 다시 해당 페이지를 클릭하면 <br/>
비동기식 웹 페이지이므로 신청한 과목이 추가되어 시간표에 출력된다. <br/><br/><br/>

### 성적 조회
![image](https://user-images.githubusercontent.com/45943080/103730810-0acbb100-5027-11eb-9310-4f678f971ad9.png)<br/>
학기마다 받은 전공과 교양 그리고 두개를 합친 전체 평점을 그래프를 통해 확인할 수 있다. <br/>
Sem을 기준으로 그룹화하여 MySQL의 “applist” 테이블의 id와 major를 받아와 과목의 평점을 계산한다. <br/>
연산 된 결과를 불러와 dataRow의 형식에 맞게 담아서 구글 차트에 적용시켜 출력했다.<br/><br/>
![image](https://user-images.githubusercontent.com/45943080/103730874-2d5dca00-5027-11eb-8da2-c20f08e19f80.png)<br/>
학점 추이 그래프는 이미지 내부 하단의 도표를 통해 확대할 수 있는 기능을 추가했다. <br/>
하단의 도표 중 양 옆의 바를 확대하고 싶은 곳을 선택하도록 드래그 하면 위의 도표가 확대된다. <br/><br/><br/>

### 질문 등록
![image](https://user-images.githubusercontent.com/45943080/103730851-21720800-5027-11eb-8df1-ce57918628bc.png)<br/>
질문을 할 수 있는 페이지이다. <br/>
내가 등록한 질문 리스트가 출력되고 상단의 [새로운 질문 등록하기] 버튼을 통해 새로운 질문을 직접 등록할 수 있다. <br/><br/>
![image](https://user-images.githubusercontent.com/45943080/103730860-23d46200-5027-11eb-8a1a-dc6c5a7986d7.png)<br/>
[새로운 질문 등록하기]을 클릭하면 다음과 같은 url로 이동한다. <br/>
양식을 채우고 하단에 위치한 [질문 등록]을 클릭하면 질문이 등록된다. [양식 초기화]을 클릭하면 입력했던 글자가 지워진다. <br/><br/><br/>
