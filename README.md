# fongdang

```
 주 제 : 펀딩사이트 제작
 구현목표 :  펀딩사이트의 주요기능을 벤치마킹한 웹 사이트 구현
 - 다양하고 참신한 아이템들을 합리적인 가격으로 소개하여 다른 사람들로부터 후원을 받을 수 있는 크라우드 펀딩 웹사이트를 구현하고자 하였다.
 - 판매자, 사이트 관리자, 소비자 사이의 의사소통을 원활하게 하고 신고 기능과 누적된 신고를 관리하여 소비자에게 피해가 가는 일이 없는 사이트로 방향을 잡았다.

```

## 목차
[1. 개발환경 및 사용기술](#개발환경-및-사용기술)  
[2. 프로젝트 설계주안점](#프로젝트-설계주안점)  
[3. 구현 기능](#구현-기능)  
[4. 팀원 및 주 담당 기능](#팀원-및-주-담당-기능)<br>
[5. ERD(pdf링크)](https://github.com/Hwangsunae88/fongdang/blob/0cfedacd47701ab88b4f16dcaf67fea0193abc83/fongdang_ERD.png)<br>
[6. UI설계서(pdf링크)](https://github.com/Hwangsunae88/fongdang/blob/bce3d834b03d3f4c4069bf27d775c8acde707ba9/fongdang_UI%20%EC%84%A4%EA%B3%84%EC%84%9C.pdf)<br>
[7. 스토리보드(pdf링크)](https://github.com/Hwangsunae88/fongdang/blob/7f7e839e9fd8fcf1a817b8540bea9597028fecd6/fongdang_%EC%8A%A4%ED%86%A0%EB%A6%AC%EB%B3%B4%EB%93%9C.pdf)<br>
[8. 최종발표자료(pdf링크)](
https://github.com/Hwangsunae88/fongdang/blob/b778339d3549602f449b6f58e9451d6cd1d5285f/fongdang_%EC%B5%9C%EC%A2%85%EB%B0%9C%ED%91%9C%EC%9E%90%EB%A3%8C.pdf)
<br>



## 개발환경 및 사용기술
[개발환경]
- Apache Tomcat Web Server 9.0
- Visual Studio Code 1.66
- Spring tool suite 3 (Version: 3.9.18.RELEASE)
- Get Started With Oracle Database 11g Express Edition / Oracle SQL Developer, Version:Oracle IDE 17.2.0, Oracle IDE 21.2.1 
- listly(DB크롤링도구)
- StarUML (Version: 5.0.1)
- draw.io

[개발언어]
- java(jdk-11.0.2)
- HTML5
- CSS3
- JS(jquery-3.6.0)
- ojdbc6
- spring-jdbc
- commons-dbcp
- mybatis
- mybatis-spring
- gson-2.8.6
- aspectjweaver
- commons-io
- commons-fileupload 

[api]
- 김연종 : 소셜(카카오, 네이버, 구글)로그인 API, javax.mail API
- 황선애 :  uploadcare API, Kakao postcode Map API, 사업자등록번호조회 API
- 이소윤 : uploadcare API, javax.mail API
- 윤성훈 : Kakao postcode Map API
- 김인곤 : import payment API, Kakao postcode Map API

[OS 환경]
- Windows 10 Pro/Home x64

[참조사이트]
- Bootstrap
- wadiz
- 크라우디
- 텀블벅

<p>
<img src="https://user-images.githubusercontent.com/98323305/194753386-a7ab8c89-1351-4f42-b6f1-767cf00ed570.jpg" width="600" height="350"/>
</p>



## 프로젝트 설계주안점

+ 로그인- 카카오,네이버 api를 통한 로그인 기능과 회원가입. 회원가입 시 다양한 유효성 체크, 아이디 저장과 비밀번호, 아이디 찾기 기능
+ 메인, 리스트 페이지- 상품과 상품 정보들을 화면에 출력, 다양한 css 효과들을 이용하여 화면을 지루하지 않게 구성, 카테고리 검색과 선택을 통해 상품을 페이지에 출력
+ 상품상세페이지 – 알림 기능을 통한 핸드폰 문자 서비스, 좋아요, 신고하기, 상품의 상세정보, 펀딩 회사 정보, 펀딩한 사람만 작성 가능한 리뷰 등을 제공
+ 펀딩 등록페이지 – 상품의 오픈 날짜, 마감기한, 가격, 옵션, api를 통한 주소검색과 사업자 등록번호 확인
+ 내정보 페이지 – 좋아요 목록, 펀딩한 상품 목록, 보낸 메시지, 받은 메시지, 프로필 사진 등록, 비밀번호 변경, 회원탈퇴, 내가 등록한 펀딩 프로젝트 목록 등을 확인할 수 있도록 구현
+ 고객센터 – 1:1 문의, 이용가이드, 공지사항, 오시는 길
+ 관리자 페이지 – 회원 관리, 상품 관리, 정산 관리, 신고 관리, 1:1 문의에 대한 답변, 공지사항 등을 관리할 수 있도록 구현  
+ 펀딩 결제페이지 - 상품의 옵션 선택이 가능하고 배송 받을 수 있는 날짜가 표시. 결제 API를 통한 결제 기능. 


## 구현 기능
+ 소셜 로그인 기능, 회원가입 시 이메일 인증
+ 펀딩예정 상품/펀딩상품 목록 상세 조회
+ 상품의 데이터를 활용하여 좋아요순, 펀딩 모금액 순, 마감기한 순 랭킹 집계
+ 알람을 신청한 펀딩 예정 상품이 펀딩 오픈 시 알람이 올 수 있도록 구현
+ 좋아요를 누를 수 있고 마이 페이지에서 좋아요를 누른 상품을 확인 가능하도록 구현
+ 메이커와 소통할 수 있는 쪽지 기능 제공
+ sns를 통한 공유하기 기능
+ 신고 누적 횟수에 따라 메이커 제재
+ 결제 API를 이용한 결제 시스템


## 팀원 및 주 담당 기능

<img src="https://user-images.githubusercontent.com/98323305/194754285-db9d9c51-b9a8-4f69-b246-2dcbb8432d13.jpg" width="700" height="350"/>

## ERD

[ERD(pdf링크)](https://github.com/Hwangsunae88/fongdang/blob/0cfedacd47701ab88b4f16dcaf67fea0193abc83/fongdang_ERD.png)

## UI 설계서
[UI설계서(pdf링크)](https://github.com/Hwangsunae88/fongdang/blob/bce3d834b03d3f4c4069bf27d775c8acde707ba9/fongdang_UI%20%EC%84%A4%EA%B3%84%EC%84%9C.pdf)

## 스토리보드
[스토리보드(pdf링크)](https://github.com/Hwangsunae88/fongdang/blob/7f7e839e9fd8fcf1a817b8540bea9597028fecd6/fongdang_%EC%8A%A4%ED%86%A0%EB%A6%AC%EB%B3%B4%EB%93%9C.pdf) 

## 최종발표자료

[최종발표자료(pdf링크)](
https://github.com/Hwangsunae88/fongdang/blob/b778339d3549602f449b6f58e9451d6cd1d5285f/fongdang_%EC%B5%9C%EC%A2%85%EB%B0%9C%ED%91%9C%EC%9E%90%EB%A3%8C.pdf)
  
  
