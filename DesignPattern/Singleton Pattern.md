# 싱글턴 패턴(Singleton Pattern)

- 인스턴스가 오직 1개만 생성되야 하는 경우에 사용되는 패턴
- 클래스 인스턴스가 하나만 만들어지도록 하고, 생성된 객체를 어디에서든지 참조할 수 있도록 하는 패턴

- 하나의 인스턴스를 메모리에 등록해서 여러 스레드가 동시에 해당 인스턴스를 공유하여 사용하게끔 할 수 있으므로, 요청이 많은 곳에서 사용하면 효율을 높일 수 있다.

- getInstance() 메서드를 통해 모든 클라이언트에게 동일한 인스턴스를 반환하는 작업을 수행

### 문제점

다중 스레드에서 클래스를 이용할 때 인스턴스가 1개 이상 생성되는 경우가 발생할 수 있다.

- 경합조건(Race Condition)을 발생시키는 경우
  - 경합조건: 메모리와 같은 동일한 자원을 2개 이상의 스레드가 이용하려고 경합하는 현상

### 해결책

- 정적 변수에 인스턴스를 만들어 바로 초기화하는 방법(Eager Initialization)

  ```java
  public class SingletonClass{
      private static SingletonClass instance = new SingletonClass();
      private SingletonClass(){}
      
      public static SingletonClass getInstance(){
          return instance;
      }
  }
  ```

  - static 변수
    - 객체가 생성되기 전 클래스가 메모리에 로딩될 때 만들어져 초기화가 한 번만 실행된다.
    - 프로그램 시작~종료까지 없어지지 않고 메모리에 계속 상주하며 클래스에서 생성된 모든 객체에서 참조할 수 있다.

- 인스턴스를 만드는 메서드에 동기화하는 방법(Thread-Safe Initialization)

  ```java
  public class SingletonClass{
      //외부에 제공할 자기 자신의 인스턴스
      private static SingletonClass instance = null;
      private int counter = 0;
      private SingletonClass() { }
      
      //인스턴스를 만드는 메서드 동기화(임계 구역)
      public synchronized static SingletonClass getInstance(){
          if(instance == null){
              instance = new SingletonClass();
          }
          return instance;
      }
      
      public void print(String str){
          //오직 하나의 스레드만 접근을 허용(임계구역)
          //성능을 위해 필요한 부분만을 임계 구역으로 설정
          synchronized(this){
              counter++;
              System.out.println(str+counter);
          }
      }
  }
  ```

  - 인스턴스를 만드는 메서드를 임계구역으로 변경
    - 다중 스레드 환경에서 동시에 여러 스레드가 getInstance 메서드를 소유하는 객체에 접근 하는 것을 방지 한다.
- 공유 변수에 접근하는 부분을 임계 구역으로 변경
    - 여러 개의 스레드가 하나뿐인 counter 변수 값에 동시에 접근해 갱신하는 것을 방지한다.
  - getInstance()에 Lock을 하는 방식이라 속도가 느리다.



## 자바와 스프링의 싱글턴 패턴

- 싱글톤 객체의 생명주기가 다르다.

- 자바에서 범위는 클래스 로더, 스프링에서는 어플리케이션 컨텍스트(ApplicationContext)가 기준이 된다.



## 스프링의 싱글턴 패턴

- 스프링은 빈을 등록할 때 범위(scope)를 지정할 수 있는데 디폴트가 싱글턴이다.
  - prototype, request, session도 있다.
- 클라이언트 요청마다 각 로직을 담당하는 객체를 만들어 사용한다면 GC가 있더라도 메모리 부하가 올 수 있다.

- 스프링은 어노테이션 설정만으로 IoC 컨테이너(applicationContext) 에 제어권을 넘겨줌으로써 손쉽게 빈(Bean) 을 싱글턴으로 생성하여 사용할 수 있다.





참고: [https://gmlwjd9405.github.io/2018/07/06/singleton-pattern.html](https://gmlwjd9405.github.io/2018/07/06/singleton-pattern.html)