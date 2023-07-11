# API

`2023-07-03`
![API-Platforms](./img/API-Platforms.png)
이미지 출처 : https://velog.io/@qowhdgn/%EB%84%A4%ED%8A%B8%EC%9B%8C%ED%81%AC-API%EB%9E%80

**API**(Application Programming Interface)는 응용 프로그램에서 사용할 수 있도록, 운영 체제나 프로그래밍 언어가 제공하는 기능을 제어할 수 있게 만든 인터페이스를 뜻한다. - `위키백과`

> > API는 정의 및 프로토콜 집합을 사용하여 두 소프트웨어 구성 요소가 서로 통신할 수 있게 하는 메커니즘이다. - `aws`

---

<br>

# API의 작동원리

![API-WORKS](./img/API-WORKS.jpg)
<br>
이미지 출처 : https://brunch.co.kr/@ahnjiwoo/26

`클라이언트 요청(Request)` -> `서버는 데이터 제공(Response)`

> 데이터의 형태는 HTML, XML, json 등으로 다양하다.

---

<br>

# API의 종류

## 1. **Private** API

- 내부 API로, 기업이나 연구 단체 등에서 자체 제품과 운영 개선을 위해 단체 내부에서만 사용한다.
- 개발자들이 애플리케이션 코드를 작성하는 방법을 표준화함으로써, 간소화되고 빠른 프로세스 처리가 가능하게 해준다.

## 2. **Public** API

- 개방형 API로, 모두에게 공개되며 Public API 중에서도 접속하는 대상에 대한 제약이 없는 경우를 **Open API**라고 한다.
  > 오픈 API 사이트 예시:
  >
  > > 구글 : https://cloud.google.com/apis?hl=ko <br>
  > > 공공데이터포털- https://www.data.go.kr/ <br>
  > > 문화데이터 광장 – https://www.culture.go.kr/data/main/main.do <br>
  > > 카카오 : https://developers.kakao.com/tool

## 3. **Partner** API

- 특정 비즈니스 파트너 간의 데이터 공유하며, 동의하는 특정인들만 사용할 수 있다.

<br>

# 아키텍처 스타일에 따른 API 종류

1 **SOAP**(Simple Object Access Protocol) API

- 클라이언트와 서버는 XML 메시지를 교환하며 HTTP 또는 SMTP를 통해 요청을 수신합니다.
- 단순 객체 접근 프로토콜을 사용한다.
  > 과거에 더 많이 사용되었으며 유연성이 떨어지는 API이다.

2 **RPC** API

- 이 API를 원격 프로시저 호출이라고 한다.
- 클라이언트가 서버에서 함수나 프로시저를 완료하면 서버가 출력을 클라이언트로 다시 전송한다.

3 **WebSocket** API

- JSON 객체를 사용하여 데이터를 전달하는 또 다른 최신 웹 API 개발이다.
- 클라이언트 앱과 서번간의 양방향 통신을 지원한다.
  > 서버가 연결된 클라이언트에 콜백 메시지를 전송할 수 있어 REST API보다 효율적이다.

4 **REST**(Representational State Transfer) API

- 데이터와 기능의 집합을 제공하여 컴퓨터 프로그램간 `정보 교환`이 가능하도록 한다.
- 클라이언트가 서버에 요청을 데이터로 전송한다.
- 서버가 이 클라이언트를 이용하여 내부 함수를 시작하고 출력 데이터를 다시 클라이언트에 반환한다.
  > 오늘날 웹에서 가장 많이 사용되고 유연한 API이다.

---

<br>

# API의 장단점

## API의 장점

- ### 데이터 접속의 표준화와 편의성

- ### 자동화와 확장성

- ### 적용력

<br>

## API의 단점

- ### 보안성과 HTTP 방식의 제한
