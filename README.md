# Задача "Понимание JVM"

JVM загрузит классы с помощью ClassLoader. С помощью Application ClassLoader загрузит класс JvmComprehension. С помощью Bootstrap ClassLoader загрузит классы System, Object и другие системные. Создаётся стековая память(Stack Memory).

```java

public class JvmComprehension {

    public static void main(String[] args) {
        int i = 1;                      // 1 - создаст переменую в Stack Memory
        Object o = new Object();        // 2 - создаст переменую в Stack Memory, которая указывает на объект в Heap
        Integer ii = 2;                 // 3 - создаст переменую в Stack Memory, которая указывает на объект в Heap
        printAll(o, i, ii);             // 4 - создаст фрейм  printAll в Stack Memory
        System.out.println("finished"); // 7 - создаст фрейм  в Stack Memory
    }

    private static void printAll(Object o, int i, Integer ii) {
        Integer uselessVar = 700;                   // 5 - создаст переменую в Stack Memory, которая указывает на объект в Heap
        System.out.println(o.toString() + i + ii);  // 6 - создаст фрейм в Stack Memory
    }
}

```
