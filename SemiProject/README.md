![header](https://capsule-render.vercel.app/api?type=slice&color=79b8ff&height=200&text=Portfolio&fontAlign=70&rotate=13&fontAlignY=25)


# 목차
- [목차](#목차)
- [프로젝트명](#프로젝트명)
  - [프로젝트 목표](#프로젝트-목표)
  - [수행기간](#수행기간)
  - [사용 기술](#사용-기술)
  - [ERD](#erd)
  - [구현 기능 사항](#구현-기능-사항)
  - [기능 구현 상세 설명](#기능-구현-상세-설명)
    - [✨1. 로그인 화면 구상하여 만들어보기](#1-로그인-화면-구상하여-만들어보기)
      - [✨1.1 로그인 화면 구상 중 메모 작성](#11-로그인-화면-구상-중-메모-작성)
    - [✨2. `[회원가입]` 서비스 약관](#2-회원가입-서비스-약관)
    - [✨3. `[회원가입]`](#3-회원가입)
    - [✨4. `[회원정보 수정]`](#4-회원정보-수정)
    - [✨5. `[주문/배송조회]` 프론트 작업](#5-주문배송조회-프론트-작업)
    - [✨6. `구매하기`](#6-구매하기)
    - [✨7. `결제하기`](#7-결제하기)
  - [프로젝트 후기](#프로젝트-후기)


# 프로젝트명
- `FineApple`

## 프로젝트 목표
- 다양한 기능을 갖춘 전자 제품 브랜드 사이트 구축

## 수행기간
- 2020년 12월 05일 ~ 2021년 01월 12일

## 사용 기술 

구분|종류|적용부분
|:-:|:-:|:-:|
Language|JAVA|공통|
DBMS|Oracle11g|공통|
Frontend| HTML, CSS, JavaScript, JSP/Servlet|공통|
Library|Jquery, ojdbc, mybatis, JSTL, cos|공통|
Framework|MyBatis|공통|
Server| Apache Tomcat 9.0| 공통
형상관리|GitHub, SourceTree|
IDE | Eclipse, Sql Developer, VSC|


## ERD

![](https://images.velog.io/images/withcolinsong/post/163b4289-3e41-44b3-9c96-374441f766fb/image.png)

## 구현 기능 사항
> 프로젝트 인원 : 6명
- `회원관리` -> 구현 
  - 회원가입, 회원정보 수정
- `결제하기` -> 구현
  - `구매하기`
  - API를 사용하여 결제하기 구현
  
- 리뷰 게시판
- Q/A 게시판
- 장바구니
- 관리자 페이지

## 기능 구현 상세 설명

### ✨1. 로그인 화면 구상하여 만들어보기
> 기능 구현을 나누기 전에 로그인 부분을 구상해보고 실제 프론트 작업을 통해 데모 파일 작성했다.

![](https://images.velog.io/images/withcolinsong/post/5cdc6cfa-7cc7-41b3-a76e-5c075dfa28be/image.png)

#### ✨1.1 로그인 화면 구상 중 메모 작성
> 작성일 : 20.12.09
- 로그인 화면
- 화면 구성
- 회원가입 페이지

> 참고사이트
>  
>[Apple 회원가입 사이트](https://appleid.apple.com/account?localang=KP-KO&app_id=2083&returnURL=https%3A//secure2.store.apple.com/kr/shop/sign_in%3Fc%3DaHR0cHM6Ly93d3cuYXBwbGUuY29tL2tyL3Nob3AvYmFnfDFhb3MzMDQyM2E5M2JmNGU5YzVlYTBiYzY3MTNjN2FiZjQwZThiYzE5ODhk%26r%3DSCDHYHP7CY4H9XK2H%26s%3DaHR0cHM6Ly93d3cuYXBwbGUuY29tL2tyL3Nob3AvYmFnfDFhb3MzMDQyM2E5M2JmNGU5YzVlYTBiYzY3MTNjN2FiZjQwZThiYzE5ODhk) 애플회원 가입도 깔끔함.
>
>[무신사 회원가입](https://my.musinsa.com/member/v2/join)    
    
    
    - 참고사항 : 단순하게, 이메일만 입력했을 시 가입하기도 있다.

1. class명, id명은 어떻게 해야할 지도 고민해보자.
2. 부족한 부분 생각해보기

### ✨2. `[회원가입]` 서비스 약관

![](https://images.velog.io/images/withcolinsong/post/df6fd809-9adf-42e9-ac6b-f64f556d2e84/ezgif.com-gif-maker%20(2).gif)

- `[필수]` 항목을 선택하지 않았을 때 JavaScript을 이용하여 alert창을 띄어주며 다음으로 넘어가지 않도록 스크립트 처리하였다.
- 계정 약관 `>` 버튼을 눌렀을 시 스크립트 모달창을 띄워 약관을 보여준다.

### ✨3. `[회원가입]`

![](https://images.velog.io/images/withcolinsong/post/638c52f8-a0d3-46cd-8263-91cc3481b706/ezgif.com-gif-maker.gif)


- 아이디를 중복체크 시 서블릿으로 DataBase를 처리 후 JSP를 통해 해당 아이디가 null 이라면 `스마일 표시`, null이 아니라면 `중복` 표시    
- JavaScript를 이용하여 이메일, 비밀번호, 아이디 형식을 벗어날 시 정규식 유효성 체크
- Daum 우편 API를 사용하여 스크립트 처리 후 해당 `<input>` 태그에 데이터를 넣어준다.


### ✨4. `[회원정보 수정]`
![](https://images.velog.io/images/withcolinsong/post/19dc1469-780b-4703-94a3-cfdd77ccd491/ezgif.com-gif-maker%20(3).gif)

- 가입한 아이디로 로그인 후 마이룸 -> 회원정보 수정으로 이동하면 가입했을 때 정보를 가져오며, `현재 비밀번호`와 `새로운 비밀번호`가 다를 시 alert창 띄우고 스크립트 처리
- 아이디를 제외한 나머지를 수정할 수 있다.
- 수정하기 버튼을 눌렀을 시 해당 데이터가 Servlet을 이용하여 DataBase를 통해 update 되면서 바뀐다.

### ✨5. `[주문/배송조회]` 프론트 작업

![](https://images.velog.io/images/withcolinsong/post/9a2178de-e871-4eb6-b4a1-104b90b9606a/image.png)

- icon 
> https://iconmonstr.com/party-12-svg/

- `배송 현황` / `배송 정보` HTML Table을 이용하여 작성
- `배송 진행 상황` flex 박스를 이용하여 레이아웃 작업 후 css 처리


### ✨6. `구매하기`

![](https://images.velog.io/images/withcolinsong/post/5cf2a5cc-0639-4da8-98e8-2ce22c798724/ezgif.com-gif-maker%20(2).gif)

- 장바구니에서 `구매하기`를 눌렀을 시 해당 아이템들의 갯수만큼 `<input>` 태그를 JSP에서 JSTL `<c:forEach><//forEach>`을 이용하여 추가했다.
- `10% 할인쿠폰 적용`
  - 해당 select의 option 값을 가져온다. 
  - 적용하기 버튼을 `onClick` 시에 장바구니에서 넘어온 총 금액을 JSTL 을 이용하여 자바스크립트 변수에  `var name = ${sum}` 담아준다. 그 변수를 `typeOf`-> `parseInt`을 통해 형변환 후 `*0.1`의 연산식을 끝낸 후 jQuery를 이용하여 .attr 속성을 이용하여 데이터를 담아준다.


### ✨7. `결제하기`
- `아임포트`를 이용하여 toss 신용카드 결제/무통장 입금 API를 구현했다.
- 토스 신용카드 결제/무통장 입금 API

![](https://images.velog.io/images/withcolinsong/post/80ee3c4f-c8fe-4fae-a0ad-92135c32cdc0/ezgif.com-gif-maker.gif)

![](https://images.velog.io/images/withcolinsong/post/1a010224-ec1b-40cb-9f30-faa7789fb6fb/ezgif.com-gif-maker%20(1).gif)



## 프로젝트 후기



















