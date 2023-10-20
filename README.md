# 기술 면접 질문 정리

 면접 LIST

<details>
<summary> <h2>1. JAVA의 특징을 설명해주세요.</h2></summary>
- 자바는 객체 지향 프로그래밍 언어입니다.   <br>
- 기본 자료형을 제외한 모든 요소들이 객체로 표현되고, 객체 지향 개념의 특징이 캡슐화, 상속, 다형성이 잘 적용된 언어입니다.    

<h3>장점</h3>
- JVM(자바 가상머신) 위에서 동작하기 때문에 운영체제에 독립적이다. <br>   
- GabageCollection을 통한 자동적인 메모리 관리가 가능하다.   
<h3>단점</h3>
- JVM 위에서 동작하기 때문에 실행 속도가 상대적으로 느리다.   <br>
- 다중 상속이나 타입에 엄격하며, 제약이 많다(그래서 인터페이스를 사용하여 보완함).

</details>


<details>
<summary> <h2>2. GC 가바지 컬렉션에 대해 설명하시오</h2></summary>
시스템에서 더 이상 사용하지 않는 동적 할당된 메모리 블록이나 객체를 찾아 자동적으로 다시 사용 가능한 자원으로 회수하는 것
<br>
(C, C++ 같은 경우에는 메모리를 수동으로 해제해주어야함)<br>
-> 자바의 경우에는 JVM이 이 역할을 수행해준다.

<br>
<h4>꼬리 질문</h4>
<details>
<summary> <h4> 가비지 컬렉션 알고리즘</h4></summary>
- 마킹 작업(Mark And Sweep) : 사용중인 메모리와 사용하지 않는 메모리 식별 -> 자바, 자바스크립트가 사용중
- 일반 삭제(Reference Counting) : 참조되지 않는 객체를 제거하고 빈 공간에 대한 포인터를 남긴다.(객체가 참조되는 횟수를 세어, 참조 횟수가 0이 되면 해당 객체를 삭제)
<br>
</details>
<summary> <h4> 가비지 컬렉션의 과정</h4></summary>
- GC의 작업을 수행하기 위해 JVM이 어플리케이션의 실행을 잠시 멈추고, GC를 실행하는 쓰레드를 제외한 모든 쓰레드들의 작업을 중단 후(Stop The World 과정) 사용하지 않는 메모리를 제거(Mark and Sweep 과정)하고 작업이 재개된다.
<br>
</details>

</details>

<details>
<summary> <h2>3. 오버라이딩과 오버로딩을 설명하시오</h2></summary>
- 오버라이딩 : 상위 클래스(부모 클래스)에 있는 메소드를 하위 클래스(자식 클래스)에서 재정의 하는 것<br>
- 오버로딩 : 매개변수의 개수, 타입을 다르게 하여 같은 이름의 메소드를 여러개 정의하는 것   
</details>

<details>
<summary> <h2>4. Get방식과 Post방식의 차이점을 설명하시오</h2></summary>
- GET : 파라미터 정보를 URL 뒤(쿼리스트링)에 붙여 보내는 방식<br>
- POST : body에 파라미터 정보를 넣어 보내는 방식
<br>
[사용목적]<br>
- GET : 서버에서 데이터를 조회할 때 사용
- POST : 서버에 데이터를 생성 혹은 수정할 때 사용
<br>
[보안]<br>
- GET : 주소창에 쿼리스트링으로 보내진 정보들이 보여지기 때문에 보안이 떨어진다.
- POST : HTTP Body에 데이터를 담아 보내기 때문에 GET방식 보다 보안이 좋다.
<br>
[멱등성(idempotent)]-> 동일한 요청을 여러 번 전송해도 처음 요청과 동일한 상태를 유지한다는 개념
- GET : 정보를 요청하는 용도로 사용되기 때문에 서버의 상태를 변경시키지 않기 때문에 멱등적이다.<br>
- POST : 정보가 변화되는 요청이기 때문에 서버의 상태가 변경됨. 그렇기 때문에 멱등성을 가지지 않는다.


</details>

<details>
<summary> <h2>5. JVM이 무엇이고 무슨 역할을 하는지 설명하시오.</h2></summary>
- 자바 가상 머신의 약자를 줄여 부르는 용어(Java Virtual Machine)<br>
- 메모리 관리(GC)를 수행하며 스택(Stack) 기반으로 동작하고 Java Byte Code를 운영체제(OS)에 맞게 해석해주는 역할<br>
- JVM은 스택(Stack) 기반으로 동작하며, 자바 바이트 코드를 OS에 맞게 해석하는 역할

</details>

<details>
<summary> <h2>6. JVM 동작 방식을 설명하시오.</h2></summary>
JAVA 클래스 파일(.java) -> 자바 컴파일러 -> 자바 바이트 코드(.class) -> JVM(자바 인터프리터, JIT 컴파일러) ->  컴퓨터가 읽을 수 있는 기계어로 해석
</details>

<details>
<summary> <h2>7. 인터프리터 언어 VS 컴파일러 언어 </h2></summary>

- 인터프리터 : 프로그램을 실행할 때 코드를 한 줄 씩 읽어나가며 실행하는 방식 -> JS, Python, Sql
<br>
- 컴파일러 : 기계가 이해할 수 있는 기계어로 번역하여 실행하는 방식 -> C,C++, JAVA
<br>
이해를 돕는 예시<br>
파이썬은 실행하고 난 뒤에 오류를 잡아주고, 자바는 실행하기 전에 빨간줄로 오류를 잡아줌

</details>

<details>
<summary> <h2>8. 객체지향의 설계 원칙(SOLID)</h2></summary>

사용 이유 : SOLID 객체 지향 원칙을 적용하면 코드를 확장하고 유지 보수 관리하기가 더 쉬워지며, 불필요한 복잡성을 제거해 리팩토링에 소요되는 시간을 줄임으로써 프로젝트 새발의 생산성을 높일 수 있다.
<br>
<h5>1. SRP - 단일 책임 원칙 : 한 클래스는 하나의 책임만 가져야 한다.</h5>
<br>
-> 클래스가 변경되어야 하는 이유가 단 하나뿐이어야 함을 의미

ex) 주문 관리 시스템을 만들때 주문 생성, 주문 저장, 주문 검색, 주문 처리, 주문 알림등 다양한 기능이 있을때 아래와 같이 코드를 짜야된다.
```
// 주문 클래스 - 단일 책임 원칙을 준수한 예시
public class Order {
    private int orderId;
    // 주문 정보와 주문 상태 관리

    public int getOrderId() {
        return orderId;
    }

    // 다른 주문과 관련된 메서드
}

// 주문 생성 클래스
public class OrderCreator {
    public Order createOrder() {
        // 주문 생성 로직
        return new Order();
    }
}

// 주문 저장 클래스
public class OrderRepository {
    public void saveOrder(Order order) {
        // 주문 저장 로직
    }

    public Order findOrderById(int orderId) {
        // 주문 검색 로직
        return null;
    }
}

// 주문 처리 클래스
public class OrderProcessor {
    public void processOrder(Order order) {
        // 주문 처리 로직
    }
}

// 주문 알림 클래스
public class OrderNotifier {
    public void sendOrderNotification(Order order) {
        // 주문 알림 전송 로직
    }
}
```

<br>
<h5>2. OCP - 개방 폐쇄 원칙 : 확장에는 열려있고, 수정에는 닫혀있어야 한다.</h5>

</details>

