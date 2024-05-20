# kurumaster



## 프로젝트
![Image of the alt text](https://images.unsplash.com/photo-1545569341-9eb8b30979d9?q=80&w=1000&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxleHBsb3JlLWZlZWR8Mnx8fGVufDB8fHx8fA%3D%3D)


##  요구사항 분석 설계서

<a href="https://docs.google.com/presentation/d/1lTJSTo-P14JcGu3FWIZ9zQvL1bJq6Uij77BIFGUbml4/edit#slide=id.gc6f80d1ff_0_0" target="_blank">요구사항 분석 설계서</a>



### 쿠루마스터 (KuruMaster)

## 배포 사이트 :






프로젝트 일정 : 2024.5.17 ~ 2024.7.29








프로젝트 Repository : [https://github.com/SungChangNam/kurumaster](https://github.com/SungChangNam/kurumaster)



## 1. 프로젝트 주제

### 렌터카 예약 및 여행정보 공유 사이트

렌터카 예약 시스템  및 커뮤니티
웹사이트 
다양한 차종 제공 
(경차, 컴팩트, SUV 등)
합리적인 가격 책정 (엔화 약세 반영)
간편하고 안전한 결제 시스템 구축
한국어 고객센터 운영



## 2. 기술 스택

- 백엔드
    - Java 1.8
    - JSP
    - Servlet
    - Spring
- 프론트엔드
    - HTML5
    - Javascript
    - JQuery
    - CSS
- 데이터베이스
    - Oracle 
- 개발도구
    - Eclipse
- 서버
    - Apache Tomcat
- 배포
    - cafe24
    

## 3. 쿠루마스터 팀 팀원 및 역할

### 여승현 - [![GitHub](https://img.shields.io/badge/GitHub-F0594F/yellowgreen.svg)](https://github.com/)


팀장 / 프로젝트 기획 / 프론트엔드 개발/ HTML/ CSS/ JavaScript/이용

### 김이현 - [![GitHub](https://img.shields.io/badge/GitHub-F0594F/yellowgreen.svg)](https://github.com/)

팀원 / 프로젝트 기획 / user기능 / 게시글 기능 / 회원관리 / FrontEnd 제작,API연결

### 성창남 - [SungChangNam - Overview](https://github.com/SungChangNam)

팀원 / 프로젝트 기획 / 데이터베이스 구축 / DB 모델링 / FrontEnd 제작,API연결

### 김진호 - [![GitHub](https://img.shields.io/badge/GitHub-F0594F/yellowgreen.svg)](https://github.com/)

팀원 / 프로젝트 기획 / 댓글 기능/ 프론트엔드 백업/크롤링/상세보기 수정 및 삭제

## 4. 프로젝트 기능


 ### 회원 기능 (회원가입,회원정보수정,email인증)

- 회원가입 시, 아이디, 닉네임, 비밀번호 정규표현식 필터링 적용 ( 회원정보 수정 시에도 적용)
- 회원정보 CRUD 기능
- 회원가입 시 약관동의 기능
- Email인증기능

### 게시판 기능 (게시글, 댓글, 대댓글)

- 게시글 CRUD 기능
- 게시글 검색 기능
- 게시글 신고 기능 (super 계정이 처리)
- 게시글 댓글 기능

### 관리자 기능 ( 사이트 관리 페이지)

- 권한을 받은 유저가 접근 가능, 권한은 admin이 부여
- 신고당한 게시글 검토 후 처리 가능
- 유저 삭제 기능
- 차량 정보 관리
- 고객정보관리
- 게시판 관리
  

### 예약 기능

- 원하는 차종
- 예약 기간
- 실시간 예약 기능 여부 확인



## 4-1. 트러블 슈팅

### 여승현

**문제 : 

**원인 : 

**해결 : 

**참조: 

### 김이현

**문제 : 

**원인 : 

**해결 : 
### 성창남

**문제 : 

**원인 : 

**해결 : 

### 김진호

**문제 : 

**원인 : 

**해결 :

### 



## 5. 와이어프레임

![와이어프레임](https://github.com/SungChangNam/kurumaster/assets/112399821/a3b51f57-3f77-46e2-b5ac-ee3b6145f8a6)


## 6. DB 설계 ERD

![RentCar (7)](https://github.com/SungChangNam/kurumaster/assets/112399821/2d85f0b1-42ad-4908-a495-34101715cfc6)


## 7.클래스 다이어그램

| Class          | Attributes                                                                 | Methods         |
|----------------|----------------------------------------------------------------------------|-----------------|
| **User**       | - id: int<br> - username: String<br> - password: String<br> - email: String<br> - phone: String<br> - createdAt: Date<br> - isAdmin: boolean | + getters/setters |
| **Verification** | - id: int<br> - userId: int<br> - code: String<br> - expiresAt: Date | + getters/setters |
| **Post**       | - id: int<br> - userId: int<br> - title: String<br> - content: CLOB<br> - createdAt: Date | + getters/setters |
| **Comment**    | - id: int<br> - postId: int<br> - userId: int<br> - content: CLOB<br> - createdAt: Date | + getters/setters |
| **Vehicle**    | - id: int<br> - model: String<br> - availability: boolean<br> - pricePerDay: float<br> - imageUrl: String | + getters/setters |
| **Reservation** | - id: int<br> - userId: int<br> - vehicleId: int<br> - startDate: Date<br> - endDate: Date<br> - totalPrice: float<br> - status: String | + getters/setters |

### 클래스 간의 관계 설명

| Relationship       | Classes         | Type     | Description                                                                                              | Foreign Key                                         |
|--------------------|-----------------|----------|----------------------------------------------------------------------------------------------------------|----------------------------------------------------|
| **User - Post**    | User, Post      | 1:N      | 한 명의 사용자는 여러 개의 게시글을 작성할 수 있습니다.                                                     | `Post` 클래스의 `userId` 속성은 `User` 클래스의 `id` 속성을 참조합니다. |
| **User - Reservation** | User, Reservation | 1:N      | 한 명의 사용자는 여러 개의 예약을 할 수 있습니다.                                                          | `Reservation` 클래스의 `userId` 속성은 `User` 클래스의 `id` 속성을 참조합니다. |
| **Post - Comment** | Post, Comment   | 1:N      | 한 개의 게시글은 여러 개의 댓글을 가질 수 있습니다.                                                       | `Comment` 클래스의 `postId` 속성은 `Post` 클래스의 `id` 속성을 참조합니다. |
| **Reservation - Vehicle** | Reservation, Vehicle | 1:1      | 예약은 한 대의 차량만 예약할 수 있습니다.                                                                  | `Reservation` 클래스의 `vehicleId` 속성은 `Vehicle` 클래스의 `id` 속성을 참조합니다. |

### 관계도

```plaintext
User (1) --- (N) Post
User (1) --- (N) Reservation
Post (1) --- (N) Comment
Reservation (1) --- (1) Vehicle




