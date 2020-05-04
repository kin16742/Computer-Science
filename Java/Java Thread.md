# Java Thread

#### Thread

```java
public class Test extends Thread {
    public void run() {
        System.out.println("thread run.");
    }

    public static void main(String[] args) {
        Test test = new Test();
        test.start();
    }
}
```

자바에서의 Thread는 위처럼 Thread 클래스를 상속받아 사용한다.

test.start() 메소드를 호출해 run() 메소드를 thread로 실행한다.

thread는 실행 순서가 일정하지 않다. (main이 run보다 먼저 종료되는 경우도 있다)

#### Join

join 메소드는 thread의 종료를 기다리게 하는 메소드이다.

```java
public static void main(String[] args) {
    ArrayList<Thread> threads = new ArrayList<Thread>();
    for(int i=0; i<10; i++) {
        Thread t = new Test(i);
        t.start();
        threads.add(t);
    }

    for(int i=0; i<threads.size(); i++) {
        Thread t = threads.get(i);
        try {
            t.join();
        }catch(Exception e) {
        }
    }
    System.out.println("main end.");
}
```

위 코드에서 join 메소드를 사용하지 않는다면, "main end"가  다른 thread의 종료 전에 출력되지만, join 메소드를 사용해 이를 방지할 수 있다.

#### Runnable

```java
public class Test implements Runnable {
    public void run() {
        System.out.println("thread run.");
    }

    public static void main(String[] args) {
        Thread t = new Thread(new Test());
        t.start();
    }
}
```

implements Runnable을 사용해 Thread를 상속받은 것과 완전히 같은 기능을 사용할 수 있다.

Run 메소드를 강제적으로 구현해야 하고, 다른 클래스를 상속받을 수 있어 유연하다.