# 맛집가이드 (가제)

전국의 맛집을 공유하고 서로 리뷰 할 수 있는 사이트 입니다

<br/>

## 👨‍👨‍👧‍👦역할

| --  | 이름                                    | 역할                                                                  |
|-----|---------------------------------------|---------------------------------------------------------------------|
| 팀원  | [안진우](https://github.com/jinu-ahn) | 메인페이지 구현, <br/>리뷰 등록/조회/삭제 기능 구현                                    |
| 팀장  | [서정연](https://github.com/yeon1128)    | 회원가입페이지 구현, <br/>맛집 정보 크롤링 기능 구현                                    |
| 팀원  | [손지아](https://github.com/JJIaa)       | 로그인페이지 구현, <br/>카테고리 별 맛집 리스트 출력 기능, <br/>맛집 추천 포스팅 기능 구현           |
| 팀원  | [이혜민](https://github.com/hm5938)      | 카테고리별페이지 구현, <br/>회원가입 기능, <br/>맛집 검색 기능 구현, <br/>메인 데이터 전달 기능 구현   |
| 팀원  | [김학준](https://github.com/lgkrwnsdll)  | 상세페이지 구현, <br/>로그인 및 JWT토큰 관리 기능  |
<br/>

## 📆프로젝트 기간

2022.08.01 ~ 2022.08.04 (총 4일)  
<br/>

## ⚙️주요 기능

- 회원가입/로그인/로그아웃

> * hashlib, JWT를 사용하여 로그인과 회원가입을 구현하였습니다.
> * 회원가입시 아이디를 중복하였는지 확인가능합니다.

- 맛집 리스트
> * 각 카테고리 마다 해당 하는 맛집리스트를 볼 수 있습니다.
> * 맛집을 이름으로 검색하여 원하는 키워드가 포함된 맛집리스트를 볼 수 있습니다.
> * SSR(Server Side Rendering)방식으로 구현하였습니다.

- 상세 페이지
> * 맛집 클릭시 그 맛집에 해당하는 상세 설명과 사용자가 남긴 리뷰들을 볼 수 있습니다.
> * 사용자가 별점과 리뷰를 남길 수 있습니다.
> * 자신이 쓴 리뷰를 삭제 할 수 있습니다.
> * SSR(Server Side Rendering)방식으로 구현하였습니다.

- 맛집 추천
> * 로그인 시 사용자는 Url로 맛집을 직접 추천할 수 있습니다.
> * 크롤링을 사용하였습니다.

![]()
<br/>

## 📑API

| 기능              | Method | url               | Request                   | Response    |
|-----------------|--------|-------------------|---------------------------|-------------|
| 회원가입            | POST   | /sign_up/save     | ID, PW                    | msg: 가입완료   |
| 회원가입_중복아이디 체크   | POST   | /sign_up/check_dup | ID                        | msg: 중복 여부  |
| 로그인 | POST   | /login            | ID, PW                    | msg: 로그인 완료 |
| 맛집 추천           | POST   | /post_place       | 카테고리, 별점, 코멘트, 이름, 설명, 주소 | msg: 등록 완료  |
| 카테고리별 맛집 조회      | GET   | /<keyword>      |     카테고리 번호                   |   |
| 맛집 이름으로 검색           | GET   | /search/<search_name>      | 식당 이름                       |   |
| 리뷰 작성(평점)       | POST   | /review       | 리뷰, 별점, 작성자 ID(토큰), 식당 ID     | msg: 등록 완료  |
| 리뷰 목록 조회        | GET    | /review       | -                         | 리뷰 리스트      |
| 리뷰 삭제           | POST   | /review/delete      | 작성자                       | msg: 삭제 완료  |


<br/>

## 🛠️기술 스택

- View: HTML5, CSS3, Javascript, JQuery, AJAX, bootstrap
- Framework: Flask(2.1.3)
- Database: MongoDB
- Server: AWS EC2
- etc: JWT(2.4.0), jQuery, jinja2(3.1.2), pymongo(4.2.0), dnspython(2.2.1)
