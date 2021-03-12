![header](https://capsule-render.vercel.app/api?type=slice&color=79b8ff&height=200&text=Portfolio&fontAlign=70&rotate=13&fontAlignY=25)


# 목차
- [목차](#목차)
- [1. 프로젝트 소개](#1-프로젝트-소개)
  - [1.1. 프로젝트 명](#11-프로젝트-명)
  - [1.2. 주제 선정 이유](#12-주제-선정-이유)
  - [1.3. 프로젝트 목표](#13-프로젝트-목표)
  - [1.4. 수행기간](#14-수행기간)
  - [1.5. 사용 기술](#15-사용-기술)
  - [1.4. ERD](#14-erd)
  - [1.5. 멤버별 기능 구현](#15-멤버별-기능-구현)
  - [1.6. 담당 역할](#16-담당-역할)
- [2. 기능 구현 상세 설명](#2-기능-구현-상세-설명)
  - [2.1. 전체 선택](#21-전체-선택)
    - [2.1.1. 코드 링크](#211-코드-링크)
  - [2.2 스팸차단](#22-스팸차단)
    - [2.2.1 코드 링크](#221-코드-링크)
  - [2.3. 답장하기](#23-답장하기)
    - [2.3.1 코드 링크](#231-코드-링크)
  - [2.4. 삭제하기](#24-삭제하기)
  - [2.1. 로그인/로그아웃](#21-로그인로그아웃)
    - [2.1.1 코드 링크](#211-코드-링크-1)


# 1. 프로젝트 소개

## 1.1. 프로젝트 명
- `Double U`

[목차로 이동하기](#목차)
## 1.2. 주제 선정 이유

파이널 프로젝트에서는 CRUD 게시판을 기본으로 추가적인 다양한 기능을 구현 하고 싶었다. 마침 팀원 한 분께서 그룹웨어를 추천했다. 내가 전에 일했던 곳에서 다우 오피스의 그룹웨어를 사용했었고, UI가 깔끔하고 색감이 예뻐 마음에 들었다. 그래서 다우 오피스를 참고사이트로 의견을 냈다.

- 참고 사이트 : `다우오피스`, `더존ICT그룹`

[목차로 이동하기](#목차)

## 1.3. 프로젝트 목표
- 다양한 기능들을 갖춘 그룹웨어 개발

[목차로 이동하기](#목차)

## 1.4. 수행기간
- 2021년 01월 21일 ~ 2021년 03월 04일

[목차로 이동하기](#목차)

## 1.5. 사용 기술 

구분|종류|적용부분
|:-:|:-:|:-:|
|OS|window 10|공통|
|언어|Java, HTML, CSS, JavaScript|　|
|Database|Oracle Database 11gXE|공통|
|형상관리|git, sourceTree|공통|
|Editor tools |VSC|front-end|
|　|Eclipse EE, Spring Tool Suite|back-end 공통|
|　|Oracle SQL Developer |공통|
|Framework|ajax|공통|
|　|spring boot|공통|
|　|mybatis|공통
|　|bootstrap|front-end
|Library|jQuery, OJDBC, COS, JSTL|CRUD|
|Server|Tomcat Apache 9.0 |　|
|외부 API| daum 우편 API|사원 정보|
|　|Editor API| 게시판

[목차로 이동하기](#목차)

## 1.4. ERD 

![](assets/DoubleU.jpg)
[목차로 이동하기](#목차)

## 1.5. 멤버별 기능 구현
> 프로젝트 인원 : 6명

- 사내 공지 게시판
- 중고 게시판
- 메일함
- 조직도, 출퇴근
- 캘린더
- 전자결재

![](assets/Member.JPG)

[목차로 이동하기](#목차)

## 1.6. 담당 역할

- 회의록 작성
- 로그인/로그아웃
- 메일함

[목차로 이동하기](#목차)

# 2. 기능 구현 상세 설명
> 메일함 구성
- 받은 메일함
- 중요 메일함
- 임시 보관함
- 보낸 메일함
- 스팸 메일함
- 휴지통
- 내 메일함

> 메일함 공통적 요소
- 왼쪽 사이드바 count 이용하여 받은 메일함의 갯수를 표시하였다.
- 메일함을 클릭하면 전체선택, 스팸차단, 답장하기, 삭제하기, 전달하기, 읽음표시, 이동하기 버튼이 있다.
- 검색창을 이용하여 검색할 수 있다.
- 페이징 처리

`공통 코드`
- [sidebar.jsp `왼쪽 사이드바`](https://github.com/withColinSong/DoubleU/blob/main/doubleu/src/main/webapp/WEB-INF/jsp/email/commonsCode/emailSidebarLink.jsp)


[목차로 이동하기](#목차)

## 2.1. 전체 선택

![](assets/SelectChkBox.gif)

- 스크립트를 이용하여 `onclick` 이벤트시 `selectChkBox(this)` function을 주어, 체크박스의 `name`을 가지고 있는 체크박스를 체크하게 된다.

### 2.1.1. 코드 링크
`view`
- [email_index.jsp](https://github.com/withColinSong/DoubleU/blob/main/doubleu/src/main/webapp/WEB-INF/jsp/email/email_index.jsp)
- [email_commons.js](https://github.com/withColinSong/DoubleU/blob/main/doubleu/src/main/resources/static/js/email/email_commons.js)


[목차로 이동하기](#목차)

## 2.2 스팸차단

![](assets/SendEmailBoxSpam.gif)

- 해당 체크박스를 클릭 후 스팸 차단 버튼을 누르면 모달창이 뜨고, 차단하기 버튼을 누르면 해당 메일이 스팸 메일함으로 이동된다.

### 2.2.1 코드 링크
`view`
- [email_index.jsp](https://github.com/withColinSong/DoubleU/blob/main/doubleu/src/main/webapp/WEB-INF/jsp/email/email_index.jsp)
- [email_spam.jsp](https://github.com/withColinSong/DoubleU/blob/main/doubleu/src/main/webapp/WEB-INF/jsp/email/email_spam.jsp)
- [email_spam_modal.jsp](https://github.com/withColinSong/DoubleU/blob/main/doubleu/src/main/webapp/WEB-INF/jsp/email/modal/spamModal.jsp)
- [email_commons.js](https://github.com/withColinSong/DoubleU/blob/main/doubleu/src/main/resources/static/js/email/email_commons.js) 
- [email_main.css](https://github.com/withColinSong/DoubleU/blob/main/doubleu/src/main/resources/static/css/email/email_main.css)


`controller`
- [EmailMainController](https://github.com/withColinSong/DoubleU/blob/main/doubleu/src/main/java/com/doubleu/email/contorller/EmailMainController.java)
    - Ctrl+F -> `// 스팸 차단 모달`

`vo`
- [EmailVo](https://github.com/withColinSong/DoubleU/blob/main/doubleu/src/main/java/com/doubleu/email/vo/EmailMainVo.java)

`business logic`
- [EmailDao `Dao`](https://github.com/withColinSong/DoubleU/blob/main/doubleu/src/main/java/com/doubleu/email/mybatis/EmailDao.java)
  -  Ctrl+F -> `// 삭제하기`
- [EmailMapper `Mapper`](https://github.com/withColinSong/DoubleU/blob/3690e8823b4bec1da302f558812bdfc57182ce21/doubleu/src/main/java/com/doubleu/email/mybatis/EmailMapper.java)
  - Ctrl+F -> `// 삭제하기 , 이동하기`
- [MyBatis `쿼리문`](https://github.com/withColinSong/DoubleU/blob/main/doubleu/src/main/resources/static/mapper/email_mapper.xml)


[목차로 이동하기](#목차)


## 2.3. 답장하기

![](assets/SelectReply.gif)

- 해당 체크박스를 클릭 후 답장하기 버튼을 누르면 메일 쓰기로 이동하며 해당 메일 주소가 받는 사람 목록에 추가된다.

### 2.3.1 코드 링크
`view`
- [email_index.jsp](https://github.com/withColinSong/DoubleU/blob/main/doubleu/src/main/webapp/WEB-INF/jsp/email/email_index.jsp)
- [email_commons.js](https://github.com/withColinSong/DoubleU/blob/main/doubleu/src/main/resources/static/js/email/email_commons.js) 
- [email_main.css](https://github.com/withColinSong/DoubleU/blob/main/doubleu/src/main/resources/static/css/email/email_main.css)


`controller`
- [EmailSelectController](https://github.com/withColinSong/DoubleU/blob/3690e8823b/doubleu/src/main/java/com/doubleu/email/contorller/EmailSelectController.java)
    - Ctrl+F -> `// 답장하기`

`vo`
- [EmailVo](https://github.com/withColinSong/DoubleU/blob/main/doubleu/src/main/java/com/doubleu/email/vo/EmailMainVo.java)

`business logic`
- [EmailDao `Dao`](https://github.com/withColinSong/DoubleU/blob/main/doubleu/src/main/java/com/doubleu/email/mybatis/EmailDao.java)
  -  Ctrl+F -> `replyWriteMail`
- [EmailMapper `Mapper`](https://github.com/withColinSong/DoubleU/blob/3690e8823b4bec1da302f558812bdfc57182ce21/doubleu/src/main/java/com/doubleu/email/mybatis/EmailMapper.java)
  - Ctrl+F -> `replyWriteMail`
- [MyBatis `쿼리문`](https://github.com/withColinSong/DoubleU/blob/main/doubleu/src/main/resources/static/mapper/email_mapper.xml)

[목차로 이동하기](#목차)

## 2.4. 삭제하기
![](assets/SendEmailBoxDelete.gif)
- 해당 체크박스를 클릭 후 삭제하기를 누르면 해당 메일은 영구적으로 삭제된다.

`view`
- [email_index.jsp](https://github.com/withColinSong/DoubleU/blob/main/doubleu/src/main/webapp/WEB-INF/jsp/email/email_index.jsp)
- [email_delete_modal.jsp](https://github.com/withColinSong/DoubleU/blob/main/doubleu/src/main/webapp/WEB-INF/jsp/email/modal/deleteModal.jsp)
- [email_commons.js](https://github.com/withColinSong/DoubleU/blob/main/doubleu/src/main/resources/static/js/email/email_commons.js)
  - Ctrl+F -> `var DeleteBtn` 
- [email_main.css](https://github.com/withColinSong/DoubleU/blob/main/doubleu/src/main/resources/static/css/email/email_main.css)


`controller`
- [EmailMainController](https://github.com/withColinSong/DoubleU/blob/3690e8823b/doubleu/src/main/java/com/doubleu/email/contorller/EmailSelectController.java)
    - Ctrl+F -> `DeleteSendTrash`

`vo`
- [EmailVo](https://github.com/withColinSong/DoubleU/blob/main/doubleu/src/main/java/com/doubleu/email/vo/EmailMainVo.java)

`business logic`
- [EmailDao `Dao`](https://github.com/withColinSong/DoubleU/blob/main/doubleu/src/main/java/com/doubleu/email/mybatis/EmailDao.java)
  -  Ctrl+F -> `// 삭제하기`
- [EmailMapper `Mapper`](https://github.com/withColinSong/DoubleU/blob/3690e8823b4bec1da302f558812bdfc57182ce21/doubleu/src/main/java/com/doubleu/email/mybatis/EmailMapper.java)
  - Ctrl+F -> `updateSendTrash`
- [MyBatis `쿼리문`](https://github.com/withColinSong/DoubleU/blob/main/doubleu/src/main/resources/static/mapper/email_mapper.xml)

[목차로 이동하기](#목차)
<hr>

## 2.1. 로그인/로그아웃

![](assets/Login.gif)

- member 테이블의 데이터가 일치하지 않을 시에 `alert`창을 띄어 재로그인 하도록 만들었다.
  - `alert`창은 SweetAlert을 기본으로 사용하였으나 해당 프로젝트의 색감과 일치하도록 css를 수정하여 적용하였다.
  - [SweetAlert 사이트](https://sweetalert.js.org/guides/)
- 로그인 성공 시 `HttpSession`에 해당 멤버의 데이터를 저장한다.
- 로그아웃 시 해당 세션을 `invalidate()` 초기화한다.

### 2.1.1 코드 링크

`view`
- [login.jsp](https://github.com/withColinSong/DoubleU/blob/main/doubleu/src/main/webapp/WEB-INF/jsp/MainPage/login.jsp)
- [loginPost.jsp `로그인 실패 view 와 스크립트`](https://github.com/withColinSong/DoubleU/blob/main/doubleu/src/main/webapp/WEB-INF/jsp/MainPage/loginPost.jsp)
- [login.js `아이디/비밀번호을 입력하지 않았을 때 스크립트`](https://github.com/withColinSong/DoubleU/blob/main/doubleu/src/main/resources/static/js/login/login.js) 
- [login.css](https://github.com/withColinSong/DoubleU/blob/main/doubleu/src/main/resources/static/css/email/login.css)


`controller`
- [LoginURLController](https://github.com/withColinSong/DoubleU/blob/main/doubleu/src/main/java/com/doubleu/login/controller/loginURLController.java)
- [LoginMainController](https://github.com/withColinSong/DoubleU/blob/main/doubleu/src/main/java/com/doubleu/login/controller/loginMainController.java)

`vo`
- [LoginVo](https://github.com/withColinSong/DoubleU/blob/main/doubleu/src/main/java/com/doubleu/login/vo/LoginVo.java)

`business logic`
- [LoginDao `Dao`](https://github.com/withColinSong/DoubleU/blob/main/doubleu/src/main/java/com/doubleu/login/mybatis/LoginDao.java)
- [LoginService `Service`](https://github.com/withColinSong/DoubleU/blob/main/doubleu/src/main/java/com/doubleu/login/service/LoginService.java)
- [LoginMapper `Mapper`](https://github.com/withColinSong/DoubleU/blob/main/doubleu/src/main/java/com/doubleu/login/mybatis/LoginMapper.java)
- [MyBatis `쿼리문`](https://github.com/withColinSong/DoubleU/blob/main/doubleu/src/main/resources/static/mapper/login_mapper.xml)

[목차로 이동하기](#목차)





