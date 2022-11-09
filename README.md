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
    1. Cookie<br>
    - HTTP의 일종으로 사용자가 어떠한 웹 사이트를 방문할 경우, 그 사이트가 사용하고 있는 서버에서 **사용자의 컴퓨터에 저장하는 작은 기록 정보 파일**이다.<br>
    - HTTP에서 클라이언트의 상태 정보를 클라이언트의 PC에 저장하였다가 **필요시 정보를 참조하거나 재사용할 수 있다.**<br>
    2. Session<br>
    - 일정 시간 동안 같은 사용자(브라우저)로부터 들어오는 일련의 요구를 하나의 상태로 보고, 그 상태를 유지시키는 기술이다.<br>
    - 여기서 일정 시간은 방문자가 웹 브라우저를 통해 웹 서버에 접속한 시점부터 웹 브라우저를 종료하여 연결을 끝내는 시점을 말한다.<br>
      즉, **방문자가 웹 서버에 접속해 있는 상태를 하나의 단위로 보고 그것을 세션이라고 한다.**
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
    - TCP는 연속성보다 신뢰성있는 전송이 중요할 때에 사용하는 프로토콜이며, UDP는 TCP보다 속도가 빠르며 네트워크 부하가 적다는 장점이 있지만,<br>
      신뢰성있는 데이터 전송을 보장하지는 않습니다.<br>
    - 그렇기 때문에 신뢰성보다는 연속성이 중요한 서비스의 예를 들면 실시간 서비스(streaming)에 자주 사용됩니다.
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
<details>
<summary>HTTP 프로토콜은 Stateless이기 때문에 상태를 저장하지 않는데, 이를 보완하기 위해 도입된 기술은 무엇인가요?</summary>
<div markdown="1">       
    Cookie와 Session입니다.
</div>
</details>

### 자료구조
<details>
<summary>List Set Map에 대해서 설명해 보고 적절한 사례를 설명해보세요.</summary>
    1. List<br>
    - 순서가 있고 중복을 허용합니다.<br>
    - 인덱스로 원소에 접근이 가능합니다.<br>
    - 크기가 가변적입니다.<br>
    
    2. Set<br>
    - 데이터의 집합이며 순서가 없고 중복된 데이터를 허용하지 않습니다.<br>
    - 중복되지 않은 데이터를 구할 때 유용합니다.<br>
    - 빠른 검색 속도를 가집니다.<br>
    - 인덱스가 따로 존재하지 않기 때문에 iterator를 사용합니다.<br>
    
    3. Map<br>
    - Key와 Value의 한쌍으로 이루어지는 데이터의 집합.<br>
    - Key에 대한 중복이 없으며 순서를 보장하지 않습니다.<br>
    - 뛰어난 검색 속도를 가집니다.<br>
    - 인덱스가 따로 존재하지 않기 때문에 iterator를 사용합니다.
<div markdown="1">       
</div>
</details>
<details>
<summary>이진 탐색트리의 시간 복잡도와 이진 탐색트리에 대해 설명해주세요</summary>
<div markdown="1"> 
    - 이진탐색트리란 이진탐색(binary search)과 연결리스트(linked list)를 결합한 자료구조의 일종입니다.<br>
      이진탐색의 효율적인 탐색 능력을 유지하면서도, 빈번한 자료 입력과 삭제를 가능하게끔 고안됐습니다.
    - 이진탐색의 경우 탐색에 소요되는 계산복잡성은 𝑂(log𝑛)으로 빠르지만 자료 입력, 삭제가 불가능합니다. 연결리스트의 경우 자료 입력,<br>
      삭제에 필요한 계산복잡성은 𝑂(1)로 효율적이지만 탐색하는 데에는 𝑂(𝑛)의 계산복잡성이 발생합니다.
</div>
</details>
<details>
<summary>Stack과 Queue에 대해서 설명해 보고 적절한 사례를 설명해보세요.</summary>
<div markdown="1"> 
    1. 스택(Stack)<br>
    - 스택(stack)은 제한적으로 접근할 수 있는 나열 구조이다. 그 접근 방법은 언제나 목록의 끝에서만 일어난다. 
    - 스택은 한 쪽 끝에서만 자료를 넣거나 뺄 수 있는 선형 구조(LIFO — Last In First Out)으로 되어 있다.
    2. 큐(Queue)<br>
    - 스택과는 달리 선입선출(FIFO, First In First Out)방식으로 되어 있다.
    - 이처럼 어떤 작업을 순서대로 실행하거나, 사용을 위해 대기를 시켜야 하는 경우에 사용한다.
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
    1. private<br>
    - 제어자가 private으로 설정되었다면 private 이 붙은 변수, 메소드는 해당 클래스에서만 접근이 가능하다.
    2. default<br>
    - 접근 제어자를 별도로 설정하지 않는다면 접근 제어자가 없는 변수, 메소드는 default 접근 제어자가 되어 해당 패키지 내에서만 접근이 가능하다.
    3. protected<br>
    - 접근제어자가 protected로 설정되었다면 protected가 붙은 변수, 메소드는 동일 패키지의 클래스 또는 해당 클래스를 상속받은 다른 패키지의 클래스에서만 접근이 가능하다.
    4. public<br>
    - 접근제어자가 public으로 설정되었다면 public 접근제어자가 붙은 변수, 메소드는 어떤 클래스에서라도 접근이 가능하다.
</div>
</details>
<details>
<summary>오버라이딩과 오버로딩을 설명해 보세요.</summary>
<div markdown="1">      
    오버로딩(Overloading) = 확장<br>
        - 같은 이름의 메서드 여러 개를 가지면서 매개변수의 유형과 개수가 다르도록 사용하는 것
    오버라이딩(Overriding) = 재정의<br>
        - 상위 클래스가 가지고 있는 메서드를 하위 클래스가 재정의해서 사용하는 것
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
<details>
<summary>빌더패턴에 대해 알고있나요? 빌더패턴은 어떤 문제를 해결하려고 사용하는건가요?</summary>
<div markdown="1">       
</div>
</details>
<details>
<summary>Abstract Class와 Interface의 차이점에 대해서 설명해주세요</summary>
<div markdown="1">       
    - 추상 클래스와 인터페이스의 차이점은 그 목적이라고 할 수 있습니다. 
    - 추상 클래스는 기본적으로 클래스 이며 이를 상속, 확장하여 사용하기 위한 것입니다. 
    - 반면 인터페이스는 해당 인터페이스를 구현한 객체들에 대한 동일한 사용방법과 동작을 보장하기 위해 사용합니다.
</div>
</details>
<details>
<summary>Error와 Exception의 차이와, Exception의 종류에 대해 설명해주세요.</summary>
<div markdown="1">
    - 에러는 메모리 부족이나 스택오버플로우와 같이 발생하면 복구할 수 없는 심각한 오류이고, 예외는 발생하더라도 수습할 수 있는 비교적 덜 심각한 오류입니다.
    - 자바의 예외에는 일반 예외와 실행 예외가 있고, 각각 Checked Exception과 Unchecked Exception으로 구분할 수 있습니다.<br>
      전자인 일반 예외, 즉 Checked Exception은 개발자가 반드시 예외 처리를 직접 진행해야 합니다.<br>
      후자인 실행 예외, 즉 Unchecked Exception은 개발자가 예외처리를 직접 하지 않아도 됩니다. 명시적인 예외 처리가 강제되는 것이 아니므로 unchecked 라고 부릅니다.
</div>
</details>
<details>
<summary>Abstract Class와 Interface의 차이점에 대해서 설명해주세요</summary>
<div markdown="1">       
    - 추상 클래스와 인터페이스의 차이점은 그 목적이라고 할 수 있습니다. 
    - 추상 클래스는 기본적으로 클래스 이며 이를 상속, 확장하여 사용하기 위한 것입니다. 
    - 반면 인터페이스는 해당 인터페이스를 구현한 객체들에 대한 동일한 사용방법과 동작을 보장하기 위해 사용합니다.
</div>
</details>
<details>
<summary>Functional interface에 대해서 설명해주세요</summary>
<div markdown="1">       
    - 함수형 인터페이스(Functional interface)는 1개의 추상 메소드를 갖고 있는 인터페이스를 말합니다.<br>
      Single Abstract Method(SAM)라고 불리기도 합니다.
</div>
</details>

## JavaScript
<details>
<summary>고차함수와 순수함수에 대해서 설명해주세요</summary>
<div markdown="1">
    1. 순수함수<br>
        - 같은 입력을 받았을 때, 같은 출력을 반환한다.
        - side-effect를 갖지 않는다.
    2. 고차함수<br>
    - 함수를 매개변수로 사용가능합니다.
    - 함수가 함수를 반환 할 수 있습니다.
    - 함수가 변수에 할당할 수 있습니다.
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
    외부에서 두 객체 간의 관계를 결정해주는 디자인 패턴( IoC 구현 기법 )으로,<br>
    인터페이스를 사이에 둬서 클래스 레벨에는 의존관계가 고정되지 않도록 하고 런타임 시에 관계를 다이나믹하게 주입하여 유연성을 확보하고 결합도를 낮출 수 있게 해준다.
</div>
</details>
<details>
<summary>AOP에 대해서 설명해 보세요.</summary>
<div markdown="1">       
    AOP는 Aspect Oriented Programming의 약자로 관점 지향 프로그래밍이라고 불린다.<br>
    관점 지향은 쉽게 말해 어떤 로직을 기준으로 핵심적인 관점, 부가적인 관점으로 나누어서 보고 그 관점을 기준으로 각각 모듈화하겠다는 것이다.<br>
    여기서 모듈화란 어떤 공통된 로직이나 기능을 하나의 단위로 묶는 것을 말한다.<br>
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
<details>
<summary>DispatcherServlet 입장에서 filter와 Interceptor는 각각 어디에 위치하고 있는지 설명해주세요.</summary>
<div markdown="1">
    1. filter : Web Context안에 위치하고 있고, DispatcherServlet보다 왼쪽(먼저)에 위치하고 있다.<br>
    2. Interceptor : Spring Context안에 위치하고 있고, DispatcherServlet보다 오른쪽(나중)에 위치하고 있다.
</div>
</details>
<details>
<summary>Request가 와서 Controller까지 가는 과정을 설명해주세요</summary>
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
 - 트랜잭션은 데이터베이스의 상태를 변환시키는 하나의 논리적 기능을 수행하기 위한 작업의 단위 또는 한꺼번에 수행되어야할 일련의 연산들을 의미한다.
</div>
</details>
<details>
<summary>Transaction의 4가지 속성 ACID에 대해서 설명해주세요.</summary>
<div markdown="1">       
 1. 원자성(Atomicity)
    - 트랜잭션이 DB에 모두 반영되거나, 혹은 전혀 반영되지 않아야 된다.
 2. 일관성(Consistency)
    - 트랜잭션의 작업 처리 결과는 항상 일관성 있어야 한다.
 3. 독립성(Isolation)
    - 둘 이상의 트랜잭션이 동시에 병행 실행되고 있을 때, 어떤 트랜잭션도 다른 트랜잭션 연산에 끼어들 수 없다.
 4. 지속성(Durability)
    - 트랜잭션이 성공적으로 완료되었으면, 결과는 영구적으로 반영되어야 한다.
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
<details>
<summary>Stored Procedure에 대해 설명해주세요</summary>
<div markdown="1"> 
    저장 프로시저 또는 스토어드 프로시저는 일련의 쿼리를 마치 하나의 함수처럼 실행하기 위한 쿼리의 집합이다.<br>
    데이터베이스에 대한 일련의 작업을 정리한 절차를 관계형 데이터베이스 관리 시스템에 저장한 것으로, 영구저장모듈이라고도 불린다.
</div>
</details>
<details>
<summary>PreparedStatement와 Statement을 비교하여 설명해주세요.</summary>
<div markdown="1"> 
    1. Statement
        -  단일로 사용될 때 빠른 속도를 지닙니다.
        -  쿼리에 인자를 부여할 수 없습니다.
        -  매번 컴파일을 수행해야 합니다.<br>
    2. PreparedStatement
        - 쿼리에 인자를 부여할 수 있습니다.
        - 처음 프리컴파일 된 후, 이후에는 컴파일을 수행하지 않습니다.
        - 여러번 수행될 때 빠른 속도를 지닙니다. (동일한 쿼리문을 조금씩 바꿔서 여러번 실행해야 할 때 좋다)
</div>
</details>
<details>
<summary>SQL Injection을 방어할 수 있는 방법에 대해서 설명해주세요.</summary>
<div markdown="1"> 
    1. 입력 값에 대한 검증
        -  검증 로직을 추가하여 미리 설정한 특수문자들이 들어왔을 때 요청을 막아낸다.<br>
    2. Error Message 노출 금지
        - 데이터베이스 에러 발생 시 따로 처리를 해주지 않았다면, 에러가 발생한 쿼리문과 함께 에러에 관한 내용을 반환해 준다. 여기서 테이블명, 컬럼명, 쿼리문이 노출이 될 수 있기 때문에, 오류발생 시           사용자에게 보여줄 수 있는 페이지를 따로 제작하거나 메시지박스를 띄우도록 해야한다.<br>
    3. Prepared Statement 구문사용
        - 서버의 php파일에 sql 쿼리문이 아래와 같이 고정되어 있고 외부의 입력으로는 이 템플릿을 변경할 수 없다면, ?에 들어가는 데이터는 단순히 문자열로 취급하기 때문에 SQL 인젝션은 발생할 수 없           다.  
</div>
</details>
<details>
<summary>Index Range Scan을 할때 인덱스를 탄다고 하는데, 인덱스를 잘 타지 못하는 경우가 있는데 왜 그런지 설명해주세요.</summary>
<div markdown="1"> 
    1. 가공할때<br>
        - where substr('업체명',1,2) = '대한'
    2. 부정형 비교할 때<br>
        - where 국가 <> '대한민국'
    3. is not null(부정형)<br>
        - where 부서코드 is not null
</div>
</details>
<details>
<summary>Database에서 Isolation Level의 각 단계와 특징에 대해서 설명해주세요</summary>
<div markdown="1"> 
    1. Read Uncommitted (Level 0)<br>
        - 어떤 트랜잭션의 내용이 커밋(Commit)이나 롤백(Rollback)과 상관없이 다른 트랜잭션에서 조회가 가능합니다.<br>
          정합성의 문제가 많은 격리 수준이기 때문에 RDBMS 표준에서는 격리수준으로 인정하지 않습니다.
    2. Read Committed (Level 1)<br>
        - 한 트랜잭션의 변경내용이 커밋(Commit)되어야만<br>
          다른 트랜잭션에서 조회가 가능합니다. 대부분의 RDBMS에서 기본적으로 사용하는 격리수준입니다.
    3. Repeatable Read (Level 2)<br>
        - 트랜잭션이 시작되기 전에 커밋된 내용에 대해서만 조회가 가능합니다. MySQL에서 기본으로 사용하며, 이 격리수준에서는 `Non-repeatable Read`이 발생하지 않습니다.
        - 트랜잭션이 완료될 때까지 Select문이 사용하는 모든 데이터에 Shared Lack이 걸립니다. 따라서 트랜잭션이 범위 내에서 조회한 데이터의 내용이 항상 동일함을 보장합니다.
    4. SERIALIZABLE (Level 3)
        - 가장 **단순하면서 엄격한 격리 수준**이지만 성능 측면에서는 동시 **처리성능이 가장 낮습니다**.
        - `SERIALIZABLE`에서는 `PHANTOM READ`가 발생하지 않습니다.트랜잭션들이 동시에 일어나지 않고, 순차적으로 실행되는 것처럼 동작합니다. 하지만, 거의 사용되지 않습니다.
</div>
</details>
<details>
<summary>Database에서 DML,DDL,DCL,TCL의 각 명령어는 어떤것이 있는지 말씀해주세요</summary>
<div markdown="1"> 
    1. DML : SELECT, INSERT, UPDATE, DELETE<br>
    2. DDL : CREATE, ALTER, DROP, RENAME, TRUNCATE<br>
    3. DCL : GRANT, REVOKE<br>
    4. TCL : COMMIT, ROLLBACK
</div>
</details>

## 그 외
<details>
<summary>MVC에 대해서 설명해 보세요.</summary>
<div markdown="1">
    MVC는 소프트웨어 공학에서 사용되는 소프트웨어 디자인 패턴이다.<br>
    이 패턴을 성공적으로 사용하면, 사용자 인터페이스로부터 비즈니스 로직을 분리하여 애플리케이션의 시각적 요소나 그 이면에서 실행되는 비즈니스 로직을 서로 영향 없이 쉽게<br> 
    고칠 수 있는 애플리케이션을 만들 수 있다.<br> 
    MVC에서 모델은 애플리케이션의 데이터를 나타내며, 뷰는 텍스트, 체크박스 항목 등과 같은 사용자 인터페이스 요소를 나타내고,<br> 
    컨트롤러는 데이터와 비즈니스 로직 사이의 상호동작을 관리한다.<br>
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
<details>
<summary>싱글톤 패턴과 DI(Dependency Injection)을 연관지어서 설명해주세요</summary>
<div markdown="1">
    - 싱글톤 패턴은 TDD(Test Driven Development)를 할 때 걸림돌이 된다.<br>
      TDD를 할 때 단위 테스트를 주로 하는데, 단위 테스트는 테스트가 서로 독립적이어야 하며 테스트를 어떤 순서로든 실행할 수 있어야 하는데<br> 
      싱글톤 패턴은 미리 생성된 하나의 인스턴스를 기반으로 구현하는 패턴이므로 각 테스트마다 ‘독립적인’ 인스턴스를 만들기가 어렵다.
    - 또한, 싱글톤 패턴은 사용하기가 쉽고 굉장히 실용적이지만 모듈 간의 결합도가 높아져 개방-폐쇄 원칙을 위배하게 된다. 이는 객체 지향 설계 원칙에 어긋난다.
    - 이때 의존성 주입(DI, Dependency Injection)을 통해 모듈 간의 결합을 조금 더 느슨하게 만들어 해결할 수 있다.
</div>
</details>
<details>
<summary>프레임워크와 라이브러리의 차이에 대해서 설명해주세요</summary>
<div markdown="1">
    - 프레임워크와 라이브러리의 차이점은 흐름을 누가 지니고 있냐의 차이입니다.<br>
      프레임워크는 전체적인 흐름을 자체적으로 가지고 있어 프로그래머는 그 안에서 필요한 코드를 작성합니다.<br>
      반면에 라이브러리는 프로그래머가 전체적인 흐름을 가지고 있어 라이브러리를 자신이 원하는 기능을 구현하고 싶을 때 가져다 사용할 수 있다는 것입니다.
</div>
</details>
<details>
<summary>HTML4와 HTML5의 차이에 대해 설명해주세요</summary>
<div markdown="1">
    1. 간략하고 명확해진 문법
        - DOCTYPE 선언 방법 : <! DOCTYPE html>
    2. 멀티미디어 요소
        - video 밑 audio 태그 추가
        - html4까지 Silverlight, flash의 지원을 받았어야 했다.
    3. 사용자 위치 식별 액세스 추가
        - GeoLocation를 이용하여 보다 간단하게 사용자의 위치 액세스 가능
    4. Client 측면의 저장소 (** WebStorage)
        - html4에서는 browser cache를 이용하여 데이터를 저장했다.
        - html5에서는 javascript 인터페이스를 통해 web sql 데이터 베이스 및 응용프로그램 사용이 가능하다.
</div>
</details>
