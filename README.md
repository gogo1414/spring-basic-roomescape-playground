## 요구사항 분석
### 1단계 - 로그인
- 로그인 기능을 구현하세요.
- 로그인 후 Cookie를 이용하여 사용자의 정보를 조회하는 API를 구현하세요.
#### 로그인 기능
- 아래의 request와 response 요구사항에 따라 /login에 email, password 값을 body에 포함하세요.
- 응답에 Cookie에 "token"값으로 토큰이 포함되도록 하세요.
#### 인증 정보 조회
- 상단바 우측 로그인 상태를 표현해주기 위해 사용자의 정보를 조회하는 API를 구현하세요.
- Cookie를 이용하여 로그인 사용자의 정보확인하세요.

### 2단계 - 로그인 리팩터링
- 사용자의 정보를 조회하는 로직을 리팩터링 합니다.
- 예약 생성 API 및 기능을 리팩터링 합니다. 
#### 로그인 리팩터링
- Cookie에 담긴 인증 정보를 이용해서 멤버 객체를 만드는 로직을 분리합니다.
  - HandlerMethodArgumentResolver을 활용하면 회원정보를 객체를 컨트롤러 메서드에 주입할 수 있습니다.
#### 예약 생성 기능 변경
- 예약 생성 시 ReservationReqeust의 name이 없는 경우 Cookie에 담긴 정보를 활용하도록 리팩터링 합니다.
  - ReservationReqeust에 name값이 있으면 name으로 Member를 찾고
  - 없으며 로그인 정보를 활용해서 Member를 찾도록 수정합니다.
