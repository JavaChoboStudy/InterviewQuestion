# 백엔드 개발자 기술 면접 질문
실제 면접에서 받았던 질문들을 모아 놓았습니다.<br>
많은 기여를 통해 더 발전시켜주시면 감사하겠습니다.<br>

## 참고사항
1. 해당 레포지토리는 아래의 오픈톡방에서 관리 중입니다.<br>
[자바의정석 스터디 오픈톡방](https://open.kakao.com/o/gOqR1NJe)<br>

## 면접 시 팁
면접관 성향마다 다 다르겠지만,<br>
저는 질문 키워드에 대해서 단순히 단답형으로 대답하는 것 대신에<br>
제가 아는 정보는 모두 설명하려고 노력했습니다.<br>

## CS 지식
### 네트워크
<details>
<summary>HTTP에 대해서 설명해 보세요.</summary>
<div markdown="1">
</div>
</details>
<details>
<summary>HTTP 구조에 대해 설명해 보세요.</summary>
<div markdown="1">       
</div>
</details>
<details>
<summary>HTTP 메서드에 대해서 설명해 보세요.</summary>
<div markdown="1">
</div>
</details>
<details>
<summary>Cookie와 Session의 차이를 설명해 보세요.</summary>
<div markdown="1">       
</div>
</details>
<details>
<summary>OSI 7계층이 무엇인지 아시나요?</summary>
<div markdown="1">
1. Physical - 물리적인 데이터 전송<br>
2. Data Link - Mac 주소를 통한 통신<br>
3. Network - IP 라우터를 통한 IP 지정<br>
4. Transport(전송) - TCP(신뢰성, 연결성) / UDP (비신뢰성, 비연결성, 실시간)<br>
5. Session - API, Socket 논리적 연결 TCP/IP<br>
6. Presentation(표현) - JPEG 데이터 표현 독립성, 파일 인코딩 압축 등<br>
7. Application(응용) - HTTP, FTP 일반적 응용 서비스
</div>
</details>
<details>
<summary>TCP/IP 4계층이 무엇인지 아나요?</summary>
<div markdown="1">       
</div>
</details>
<details>
<summary>TCP와 UDP의 차이점은 무엇인가요?</summary>
<div markdown="1">       
</div>
</details>
<details>
<summary>TCP 3-Way Handshake에 대해서 설명해주세요.</summary>
<div markdown="1">
<img src="https://user-images.githubusercontent.com/36688619/196090240-f9bf779a-40b2-425a-a2b2-48bccffcdc88.png" width="461" height="366"><br>
1. 클라이언트가 서버에게 SYN 패킷을 보냄 (sequence : x)<br>
2. 서버가 SYN(x)을 받고, 클라이언트로 받았다는 신호인 ACK와 SYN 패킷을 보냄 (sequence : y, ACK : x + 1)<br>
3. 클라이언트는 서버의 응답은 ACK(x+1)와 SYN(y) 패킷을 받고, ACK(y+1)를 서버로 보냄<br>
이렇게 3번의 통신이 완료되면 연결이 성립된다. (3번이라 3 way handshake인 것)
</div>
</details>
<details>
<summary>동시성에 대한 문제를 해결해본 경험이 있나요? 이 문제에 대해 생각해본 적이 있나요?</summary>
<div markdown="1">       
</div>
</details>
<details>
<summary>퍼사드 패턴에 대해 알고있나요? 어떠한 경우에 사용하나요?</summary>
<div markdown="1">       
</div>
</details>
<details>
<summary>SSL Handshake에 대해서 설명해주세요.</summary>
<div markdown="1">
<img src="https://user-images.githubusercontent.com/36688619/196090207-271b88b3-e37d-45b5-9bc1-7caa0497aaec.png" width="500" height="470"><br>
1. 클라이언트는 서버에게 `client hello` 메시지를 담아 서버로 보낸다. 이때 암호화된 정보를 함께 담는데, `버전`, `암호 알고리즘`, `압축 방식` 등을 담는다.<br>
2. 서버는 클라이언트가 보낸 암호 알고리즘과 압축 방식을 받고, `세션 ID`와 `CA 공개 인증서`를 `server hello` 메시지와 함께 담아 응답한다. 이 CA 인증서에는 앞으로 통신 이후 사용할 대칭키가 생성되기 전, 클라이언트에서 handshake 과정 속 암호화에 사용할 공개키를 담고 있다.<br>
3. 클라이언트 측은 서버에서 보낸 CA 인증서에 대해 유효한 지 CA 목록에서 확인하는 과정을 진행한다.<br>
4. CA 인증서에 대한 신뢰성이 확보되었다면, 클라이언트는 난수 바이트를 생성하여 서버의 공개키로 암호화한다. 이 난수 바이트는 대칭키를 정하는데 사용이 되고, 앞으로 서로 메시지를 통신할 때 암호화하는데 사용된다.<br>
5. 만약 2번 단계에서 서버가 클라이언트 인증서를 함께 요구했다면, 클라이언트의 인증서와 클라이언트의 개인키로 암호화된 임의의 바이트 문자열을 함께 보내준다.<br>
6. 서버는 클라이언트의 인증서를 확인 후, 난수 바이트를 자신의 개인키로 복호화 후 대칭 마스터 키 생성에 활용한다.<br>
7. 클라이언트는 handshake 과정이 완료되었다는 `finished` 메시지를 서버에 보내면서, 지금까지 보낸 교환 내역들을 해싱 후 그 값을 대칭키로 암호화하여 같이 담아 보내준다.<br>
8. 서버도 동일하게 교환 내용들을 해싱한 뒤 클라이언트에서 보내준 값과 일치하는 지 확인한다. 일치하면 서버도 마찬가지로 `finished` 메시지를 이번에 만든 대칭키로 암호화하여 보낸다.<br>
9. 클라이언트는 해당 메시지를 대칭키로 복호화하여 서로 통신이 가능한 신뢰받은 사용자란 걸 인지하고, 앞으로 클라이언트와 서버는 해당 대칭키로 데이터를 주고받을 수 있게 된다.
</div>
</details>

### 자료구조
<details>
<summary>List Set Map에 대해서 설명해 보고 적절한 사례를 설명해보세요.</summary>
<div markdown="1">       
</div>
</details>
<details>
<summary>Stack과 Queue에 대해서 설명해 보고 적절한 사례를 설명해보세요.</summary>
<div markdown="1">       
</div>
</details>

### OS
<details>
<summary>프로세스와 쓰레드의 차이점을 설명해 보세요.</summary>
<div markdown="1">       
</div>
</details>

## JAVA
<details>
<summary>접근제어자에 대해서 설명해 보세요,</summary>
<div markdown="1">       
</div>
</details>
<details>
<summary>오버라이딩과 오버로딩을 설명해 보세요.</summary>
<div markdown="1">       
</div>
</details>
<details>
<summary>대표적인 GC의 동작방식을 설명해 보세요.</summary>
<div markdown="1">       
</div>
</details>
<details>
<summary>GC의 종류는 무엇이 있나요?</summary>
<div markdown="1">       
</div>
</details>
<details>
<summary>JVM에 대해서 설명해 보세요.</summary>
<div markdown="1">       
</div>
</details>
<details>
<summary>클래스 변수와 인스턴스 변수의 차이를 설명해 보세요.</summary>
<div markdown="1">       
</div>
</details>
<details>
<summary>불변객체를 사용해본적 있나요? 사용해본적이 있다면 사용이유와 장단점을 알고있나요? </summary>
<div markdown="1">       
</div>
</details>
<details>
<summary>객체를 직렬화 하는 방법에 대해 알고있나요? 알고있다면 직렬화 하는 이유는 무엇인가요?</summary>
<div markdown="1">       
</div>
</details>
<details>
<summary>빌더패턴에 대해 알고있나요? 빌더패턴은 어떤 문제를 해결하려고 사용하는건가요?</summary>
<div markdown="1">       
</div>
</details>
<details>
<summary>예외클래스를 직접 작성해본 적 있나요?</summary>
<div markdown="1">       
</div>
</details>

## Spring
<details>
<summary>Spring Framework가 무엇인지 설명해보세요.</summary>
<div markdown="1">       
</div>
</details>
<details>
<summary>Spring Framework를 사용하는 이유는 무엇인가요?</summary>
<div markdown="1">       
</div>
</details>
<details>
<summary>DI에 대해서 설명해 보세요.</summary>
<div markdown="1">       
</div>
</details>
<details>
<summary>AOP에 대해서 설명해 보세요.</summary>
<div markdown="1">       
</div>
</details>
<details>
<summary>Filter와 Interceptor의 차이점은 뭔가요?</summary>
<div markdown="1">       
</div>
</details>
<details>
<summary>Bean은 무엇이고 객체와 무엇이 다른가요?</summary>
<div markdown="1">       
</div>
</details>

## DB
<details>
<summary>PK와 FK를 설명해 보세요.</summary>
<div markdown="1">       
</div>
</details>
<details>
<summary>Transaction에 대해 설명해 보세요.</summary>
<div markdown="1">       
</div>
</details>
<details>
<summary>Index가 무엇이고 왜 사용하나요?</summary>
<div markdown="1">       
</div>
</details>
<details>
<summary>정규화란 무엇인가요?</summary>
<div markdown="1">       
</div>
</details>
<details>
<summary>On과 Where의 차이를 설명해 보세요.</summary>
<div markdown="1">       
</div>
</details>
<details>
<summary>오라클과 MySQL의 차이점 아는 대로 설명해 주세요.</summary>
<div markdown="1">       
</div>
</details>

## 그 외
<details>
<summary>MVC에 대해서 설명해 보세요.</summary>
<div markdown="1">       
</div>
</details>
<details>
<summary>JWT가 무엇인지 설명해 보세요.</summary>
<div markdown="1">       
</div>
</details>
<details>
<summary>REST API에 대해서 설명해 보세요.</summary>
<div markdown="1">       
</div>
</details>
<details>
<summary>MyBatis랑 JPA의 차이점과 각각 장단점은 무엇인가요?</summary>
<div markdown="1">       
</div>
</details>
<details>
<summary>알고 있는 디자인 패턴의 종류에 대해서 설명해주세요.</summary>
<div markdown="1">       
</div>
</details>
<details>
<summary>SOLID 원칙에 대해서 설명해주세요.</summary>
<div markdown="1">
1. Single Responsibility Principle(SRP) - 단일책임<br>
    - 클래스는 오직 하나의 이유로 수정되어야 한다.<br>
2. Open Closed Principle(OCP) - 개방폐쇄<br>
    - 자신의 확장에는 열려있고 주변의 변화에는 닫혀 있어야 하는 것을 의미한다.<br>
3. Liskov Substitution Principle(LSP) - 리스코프 치환<br>
    - base 클래스에서 파생된 클래스는 base 클래스를 대체해서 사용할 수 있어야한다.<br>
4. Interface Segregation Principle(ISP) - 인터페이스 분리<br>
    - 사용하지 않는 메소드에 의존하면 안된다.<br>
5. Dependency Inversion Principle(DIP) - 의존관계 역전<br>
    - 자신(high level module)보다 변하기 쉬운 모듈(low level modeul)에 의존해서는 안된다.
</div>
</details>
