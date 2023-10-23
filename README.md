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

사용 이유 : SOLID 객체 지향 원칙을 적용하면 코드를 확장하고 유지 보수 관리하기가 더 쉬워지며, 불필요한 복잡성을 제거해 리팩토링에 소요되는 시간을 줄임으로써 프로젝트 개발의 생산성을 높일 수 있다.
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
<h5>2. OCP(Open-Closed Principle) - 개방 폐쇄 원칙 : 확장에는 열려있고, 수정에는 닫혀있어야 한다.</h5>
<br>
방법
<br>
추상화와 다형성 활용 : 추상 클래스와 인터페이스를 사용하여 확장 가능한 코드를 작성
<br>
디자인 패턴 사용 : OCP를 준수하는 설계 패턴을 제공함
<br>
의존성 주입 : 의존성 주입을 통해 외부에서 객체의 의존성을 주입받게 함으로써 새로운 구현을 추가하거나 변경할 때 기존 코드를 수정하지 않고도 확장 가능한 코드를 작성할 수 있다.

```
interface Shape {
    void draw();
}

class Circle implements Shape {
    void draw() {
        // 원을 그리는 코드
    }
}

class Rectangle implements Shape {
    void draw() {
        // 사각형을 그리는 코드
    }
}

class Triangle implements Shape {
    void draw() {
        // 삼각형을 그리는 코드
    }
}

// 클라이언트 코드
public class DrawingApp {
    public void drawShapes() {
        List<Shape> shapes = new ArrayList<>(); // 인터페이스를 생성하여 draw라는 기능만 가지도록 하게 하고 클래스를 추가하여 확장하도록 설계해놓음
        shapes.add(new Circle());
        shapes.add(new Rectangle());
        shapes.add(new Triangle());
        
        for (Shape shape : shapes) {
            shape.draw();
        }
    }
}
```

<h5>3. LSP(Liskov Substitution Principle) - 리스코프 치환 원칙 : 하위 타입은 항상 상위 타입을 대체 할 수 있어야 한다.</h5>

<br>
잘못된 예제

```
class Bird {
    void fly() {
        System.out.println("새가 날아갑니다.");
    }
}

class Ostrich extends Bird {
    void fly() {
        throw new UnsupportedOperationException("타조는 날지 않습니다.");
    }
}

public class Main {
    public static void main(String[] args) {
        Bird bird = new Ostrich();
        bird.fly();
    }
}

```

Ostrich는 Bird의 서브타입이지만 fly 메서드의 동작이 슈퍼타입(Bird)에서 기대되는 동작과 다름 
<br>
-> 'Bird'에서는 '새가 날아갑니다'라는 말을 출력하지만 Ostrich에서는 예외를 던지면서 다른 동작을 수행함


<br>
올바른 예시

```
class Shape {
    int area() {
        return 0;
    }
}

class Rectangle extends Shape {
    int width;
    int height;

    int area() {
        return width * height;
    }
}

```

```

void printArea(Shape shape) {
    int area = shape.area();
    System.out.println("넓이: " + area);
}

public static void main(String[] args) {
    Shape shape = new Shape();
    Rectangle rectangle = new Rectangle();
    
    printArea(shape);      // 결과: "넓이: 0"
    printArea(rectangle);  // 결과: "넓이: (직사각형의 넓이)"
}

```

<br>

<h5>4. ISP(Interface Segregation Principle) - 인터페이스 분리 원칙 : 한 클래스는 자신이 사용하지 않는 메서드에 의존해서는 안 되며, 인터페이스는 그 구현체들에게 필요한 메서드만을 제공해야 한다. </h5>

<br>
잘못된 예

```
interface Worker {
    void work();
    void eat();
}

```

```

class SuperWorker implements Worker {
    public void work() {
        // 일을 수행하는 코드
    }

    public void eat() {
        // 점심 식사를 하는 코드
    }
}

```



올바른 예

<br>

```

interface Workable {
    void work();
}

interface Feedable {
    void eat();
}

class SuperWorker implements Workable, Feedable {
    public void work() {
        // 일을 수행하는 코드
    }

    public void eat() {
        // 점심 식사를 하는 코드
    }
}

class RegularWorker implements Workable {
    public void work() {
        // 일을 수행하는 코드
    }
}



```


<br>




<h5>5. DIP(Dependency Inversion Principle) - 의존 관계 원칙 : 구체적인 클래스보다 상위 클래스, 인터페이스, 추상클래스와 같이 변하지 않을 가능성이 높은 클래스와 관계를 맺어라</h5>

<br>
잘못된 예

```
class Bulb {
    void turnOn() {
        // 전구를 켜는 코드
    }
}

class Switch {
    private Bulb bulb;

    // Switch 클래스가 Bulb 클래스에 직접 의존하고 있음
    Switch() {
        this.bulb = new Bulb();
    }

    void operate() {
        bulb.turnOn();
    }
}


```
<br>
올바른 예
<br>

```
interface Switchable {
    void turnOn();
}

class Bulb implements Switchable {
    public void turnOn() {
        // 전구를 켜는 코드
    }
}

class Fan implements Switchable {
    public void turnOn() {
        // 선풍기를 켜는 코드
    }
}

class Switch {
    private Switchable device;

    // Switchable이라는 인터페이스(추상)에 의존하여 이 인터페이스를 구현한 Bulb와 Fan을 사용할 수 있음 
    Switch(Switchable device) {
        this.device = device;
    }

    void operate() {
        device.turnOn();
    }
}
```


</details>

<details>
<summary> <h2>9. 자바의 메모리 영역에 대해 설명하시오.</h2></summary>

자바의 메모리 공간은 크게 Method 영역, Stack 영역, Heap 영역으로 구분되고, 데이터 타입에 따라 할당된다.
<br>
- 메소드(스태틱) 영역 : 전역변수와 static 변수를 저장하며, Method 영역은 프로그램의 시작부터 종료까지 메모리에 남아있다.
<br>
- 스택(Stack) 영역 : 스레드 별 지역변수와 매개변수 데이터 값이 저장되는 공간이며, 메소드가 호출될 때 메모리에 할당되고 종료되면 메모리가 해제된다. LIFO(Last In First Out) 구조를 갖고 변수에 새로운 데이터가 할당되면 이전 데이터는 지워진다.
<br>
- 힙(Heap)영역 : new 키워드로 생성되는 객체(인스턴스), 배열 등이 Heap 영역에 저장되며, 가비지 컬렉션에 의해 메모리가 관리되어 진다.
<br>
<br>
<h5>각 메모리 영역이 할당되는 시점은?</h5>
<br>
- 메소드 영역 : JVM이 동작해서 클래스가 로딩될 때 생성<br>
- 스택 영역 : 컴파일 타임 시 할당<br>
- 힙 영역 : 런타임시 할당<br>


</details>

<details>
<summary> <h2>10. VO vs DTO vs DAO</h2></summary>

- VO(Value Object) : 값 오브젝트로써 값을 위해 쓰인다. Read-Only의 특징을 가진다.<br> 
- DTO(Data Transfer Object) : 순수한 데이터 객체로써 속성과 그 속성에 접근하기 위한 getter, setter 메소드만 가진 클래스
<br>
- DAO(Data Access Object) : DB의 data에 접근하기 위한 객체로 실제 DB에 접근하는 객체
<br>
</details>


<details>
<summary> <h2>11. 단방향, 양방향 바인딩에 대해서 설명하시오</h2></summary>

- 데이터 바인딩 : 두 데이터 혹은 정보의 소스를 일치시키는 기법으로, 화면에 보이는 데이터와 브라우저 메모리에 있는 데이터(여러 개의 자바스크립트 객체)를 일치시키는 것을 말함
<br>
<br>
양방향 데이터 바인딩<br>
▶ 장점 : 코드의 사용면에서 코드량을 크게 줄여줌<br>
▷ 단점 : 변화에 따라 DOM 객체 전체를 렌더링해주거나 데이터를 바꿔주므로, 성능이 감소되는 경우가 있음<br>
<br>
단방향 데이터 바인딩<br>
▶ 장점 : 데이터 변화에 따른 성능 저하 없이 DOM 객체 갱신 가능,<br>
데이터 흐름이 단방향(부모 -> 하위 컴포넌트)이라, 코드를 이해하기 쉽고 데이터 추적과 디버깅이 쉬움<br>
▷ 단점 :  변화를 감지하고 화면을 업데이트 하는 코드를 매번 작성해야 함<br>

</details>

<details>
<summary> <h2>12. Code spliting에 대해서 설명하시오</h2></summary>

하나의 번들 파일을 여러 개의 번들 파일로 나누어 더 빠른 속도로 화면을 로드하기 위함

</details>

<details>
<summary> <h2>13. AOP(Aspect Oriented Programming)에 대해서 설명하시오</h2></summary>

프로그램 내의 핵심 비즈니스 로직에서 공통적으로 들어가야 될 코드를 부가 기능 로직으로 분리하여 구현하는 것을 AOP라고 한다.
<br>
예를 들어 컨트롤러 (get, post)연결에서 IP값을 받고 싶을 때 일반적으로 비즈니스 로직을 구현한다면 IP를 호출하는 함수를 모든 비즈니스 로직에 넣어야 하지만 AOP 방식을 사용하면 부가기능 영역에 IP를 호출하는 함수를 넣으면 모든 연결에서 IP를 가져올 수 있다.


</details>


<details>
<summary> <h2>14. Connection Pool에 대해서 설명하시오</h2></summary>

<h4>핵심 키워드 : WAS, DB 연결 객체, Pool</h4>
<br>
WAS가 실행되면서 DB와 연결해놓은 객체들을 pool에 저장시켜놓고 필요할 때 가져다 쓰는 방식을 말함
<br>
<br>
<h4>Web Server VS WAS/Web Contatiner </h4><br>
- Web Server :  Http 프로토콜을 기반으로 클라이언트가 웹 브라우저에서 어떠한 요청을 하면 그 요청을 받아 <b>정적 컨텐츠</b>를 제공하는 서버.
<br>

<br>
- WAS(Web Application Server)/Web Container :  DB 조회 or 다양한 로직 처리를 요구하는 <b>동적 컨텐츠</b>를 제공하기 위해 만들어진 Application 서버
(정적인 리소스 역시 처리할 수 있음 )
<br>

<br>
WAS에서 웹서버의 기능까지 모두 수행하면 안되는 이유<br>
1. 서버 부하 방지<br>
정적 컨텐츠까지 WAS가 처리한다면 부하가 커지게 되고, 수행 속도가 느려짐<br>
2. 보안 강화<br>
SSL에 대한 암호화, 복호화 처리에 웹 서버를 사용 가능<br>
3. 여러 대의 WAS 연결 가능<br>
로드 밸런싱을 위해 웹 서버를 사용할 수 있다. 여러 개의 서버를 사용하는 대용량 웹 어플리케이션의 경우 웹 서버와 WAS를 분리하여 무중단 운영을 위한 장애 극복에 쉽게 대응할 수 있다.<br>
4. 여러 웹 어플리케이션 서비스 가능<br>
하나의 서버에서 PHP, JAVA 어플리케이션을 함께 사용할 수 있다.<br>




</details>


<details>
<summary> <h2>15. DDL, DML, DCL에 대해서 설명하시오 </h2></summary>

DDL(Defination 정의) : CREATE, ALTER, DROP, TRUNCATE <br>
DML(Manipulation 조작) : SELECT, INSERT, UPDATE, DELETE <br>
DCL(Control 통제) : GRANT,  REVOKE <br>
 
</details>

<details>
<summary> <h2>16. DBMS에 대해서 설명하시오 </h2></summary>

DataBase Management System => 데이터에 관한 정보를 가능한 한 효율적이고 효과적으로 구성, 복원 및 검색할 수 있도록 만든 응용 프로그램 모음<br>

* RDBMS(관계형) -> oracle, mysql, mssql과 같이 테이블을 만들어서 속성에 따라 관리하는 DB를 말한다.
* noSql(비관계형) -> JSON 데이터 형식(key-value)으로 데이터를 관리하는 DB

</details>

<details>
<summary> <h2>17. 정규화, 비정규화에 대해서 설명하시오 </h2></summary>

키워드 : 데이터 무결성, 중복 데이터 제거<br>
- 데이터 무결성 : 데이터가 정확하고 일관성 있게 유지되는 상태를 나타내는 개념<br>
(데이터가 정확하게 저장, 검색, 처리 및 전달되는 것을 보장하는 것을 의미)<br>
ex) 물류 데이터베이스에서 재고 상품 수량이 음수가 된다든지 주문번호가 중복되는 상황이 데이터 무결성이 오류가 난 것

* 1NF(원자성- 하나의 값)
* 2NF(완전 함수의 종속)
- 2정규화를 더 쉽게 이해하기 위한 TIP<br>
=> 2정규화의 주요 목적은 테이블을 더 작고 더 유연한 부분으로 분할하여 각 테이블이 서로 다른 성격을 가지도록 만드는것.<br>
(성적 테이블은 성적에 관련된 내용만, 학생 테이블은 학생에 관련된 내용만)
<br>
ex) 테이블 예시 

```
    수강생번호	성명	전화번호	수강과목	담당선생님	성적
    1111	    갑	010-1234-5678	수학	    김하나	    C
    1112	    을	010-1111-2222	과학	    판테온	    A
    1113	    병	010-7777-7777	수학	    김하나	    B
    1113	    병	010-7777-7777	국어	    오징어	    A
    1114	    정	010-5151-6161	국어	    오징어	    C
    1114	    정	010-5151-6161	과학	    판테온	    B
    1115	    갑	010-1234-5678	영어	    제임스	    B
    1115	    갑	010-1234-5678	수학	    김하나	    B
```
<br>
- 2정규화을 적용했을 때
<br>

```
수강생 정보(Students) 테이블

| 수강생번호  | 성명  | 전화번호 |
|------------|-------|---------|
| 1111       | 갑    | 010-1234-5678 |
| 1112       | 을    | 010-1111-2222 |
| 1113       | 병    | 010-7777-7777 |
| 1114       | 정    | 010-5151-6161 |
| 1115       | 갑    | 010-1234-5678 |

수각 과목 정보(Courses) 테이블

| 수강과목 | 담당선생님 |
|----------|-----------|
| 수학     | 김하나     |
| 과학     | 판테온     |
| 국어     | 오징어     |
| 영어     | 제임스     |


수강 정보(Enrollments) 테이블

| 수강생번호 | 수강과목 | 성적 |
|------------|----------|------|
| 1111       | 수학     | C    |
| 1112       | 과학     | A    |
| 1113       | 수학     | B    |
| 1113       | 국어     | A    |
| 1114       | 국어     | C    |
| 1114       | 과학     | B    |
| 1115       | 영어     | B    |
| 1115       | 수학     | B    |


```


* 3NF(이행적 종속 제거)

- 정규화 : 데이터 무결성을 유지하기 위해 잘 정의 된 방식으로 테이블을 분할하여 데이터베이스에서 중복 데이터를 제거하는 프로세스

- 비정규화 : 복잡한 쿼리 속도를 높이고 성능을 향상시키기 위해 테이블에 중복 데이터를 추가하는 프로세스

</details>

<details>
<summary> <h2>18. 데이터베이스 뷰에 대해서 설명하시오 </h2></summary>

직접 테이블에 접근하지 않고 테이블 내 허용된 데이터를 제한적으로 보여주기 위해 만들어진 가상 테이블


</details>

<details>
<summary> <h2>19. 데이터베이스 트랜잭션(ACID 성질)에 대해서 설명하시오 </h2></summary>

키워드 : 원자성, 일관성, 독립성, 영속성<br>

데이터 베이스에서 하나의 작업을 할 때 한꺼번에 모두 수행되어야 할 작업들을 의미한다.<br>
Commit과 Rollback을 통해 작업을 수행할 수 있다.


</details>


<details>
<summary> <h2>20. 프로시저에 대해서 설명하시오</h2></summary>

실행할 DB쿼리를 미리 데이터 베이스 저장하여 호출시킬 수 있는 기능
<br>
프로그래밍 언어의 함수와 비슷한 역할을 한다고 할 수 있다.


</details>

<details>
<summary> <h2>21. 트리거에 대해서 설명하시오</h2></summary>

DML(insert, update, delete)가 발생했을 때 자동으로 작업을 처리하는 것
<br>
장점 : 데이터의 무결성<br>
단점 : 트리거를 과도하게 사용한다면 연쇄 트리거 작동으로 기능이 저하될 수 있다.<br>
(하나의 트리거가 활성되면서 트리거내 DML이 수행되고, 또 다른 트리거가 발생하게 되기 때문이다.)


</details>

<details>
<summary> <h2>22. 이상현상에 대해서 설명하시오</h2></summary>

데이터베이스에서 데이터 무결성이 깨지면서 삽입,수정,삭제 이상현상이 발생하여 데이터가 망가지는 것을 의미<br>
(원하지 않는 값이 삽입, 수정, 삭제되는 현상)


</details>

<details>
<summary> <h2>23. Locking에 대해서 설명하시오</h2></summary>

트랜잭션이 DB를 다루는 동안 다른 트랜잭션이 관여하지 못하게 막는 것

</details>


<details>
<summary> <h2>24. 인덱스에 대해서 설명하시오</h2></summary>

DB에서 데이터를 더 빠르게 검색하기 위해서 사용하는 자료구조
<h3> 클러스터드 인덱스</h3>
- 데이터를 테이블 내에서 물리적으로 재배치하는 것<br>
- 하나의 테이블에는 한 개의 클러스터드 인덱스만 존재<br>
<br>
<h4>!!! 헷갈렸던 개념 : pk와 클러스터드 인덱스의 차이점 !!!</h4><br>
주된 역할<br>
PK : 레코드 식별과 데이터 무결성 유지(각 행을 고유하게 식별하는 데 사용)<br>
클러스터드 인덱스 : 데이터의 물리적인 재배치<br>


<h3>비클러스터드 인덱스</h3>
- 데이터의 물리적인 순서를 변경하지 않고, 별도의 인덱스 구조를 생성<br>
- 원본 테이블과는 별도로 관리되며, 인덱스에 있는 키 값과 해당 키가 가리키는 실제 데이터의 위치를 가리킴<br>
- 하나의 테이블에 여러 개의 비클러스터드 인덱스 생성 가능<br>


</details>

<details>
<summary> <h2>25. ArrayList, LinkedList</h2></summary>

* ArrayList : 인덱스 값으로 접근 -> 검색에 유리
* LinkedList : 주소값 값으로 접근 -> 삽입, 삭제가 유리

</details>



