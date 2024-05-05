# Java算法常用数据结构

## ArrayList(链表)

链表是可扩展长度的数组。

 **函数名**           | **功能**         
:-----------------:|:--------------:
 add(ele)          | 将ele插入到数组中     
 remove(int idx)   | 删除下标idx的元素     
 set(int idx, ele) | 替换idx处的元素为ele  
 get(int idx)      | 获取idx处的元素      
 indexOf(ele)      | 返回第一次出现ele的索引  
 lastIndexOf(ele)  | 返回最后一次出现ele的索引 
 size()            | 返回链表的长度        
 isEmpty()         | 判断链表是否为空       
 toArray()         | 转为数组           

## 栈

栈是一种具有 先入后出 特点的抽象数据结构，可使用数组或链表实现

实际上 Stack 在Java中已经废弃，官方也不再建议继续使用。可以使用 Deque 来代替 Stack ，详细请看下方## 栈和队列的替代

```java
    Stack<Integer> stack = new Stack<>(); // 初始化
    stack.push(1);          // 入栈
    int a = stack.peek();   // 获取栈顶元素
    int b = stack.pop();    // 出栈
    stack.size();           // 栈的大小
    stack.empty();          // 判断栈是否为空
```

<!-- 在Java中不推荐使用```Vector```及其子类```Stack``` 一般使用```LinkedList```。

```java
LinkedList<Integer> stack = new LinkedList<>(); // 初始化
stack.addLast(1); // 入栈
stack.removeLast(); // 出栈
``` -->

## 队列

队列是一种具有 先入先出 特点的抽象数据结构，可使用链表实现

```java
    Queue<Integer> queue = new LinkedList<>(); // 初始化
    queue.offer(1); // 入队
    queue.poll();   // 出队
    queue.peek();   // 获取队头元素
    queue.size();   // 队列的大小
    queue.isEmpty();// 判断队列是否为空
```

## 栈和队列的替代

Deque是一个双端队列接口，继承自Queue接口，Deque的实现类是LinkedList、ArrayDeque、LinkedBlockingDeque，其中LinkedList是最常用的。

Deque有三种用途：

    1. 普通队列: Queue queue = new LinkedList()或Deque deque = new LinkedList()
    2. 双端队列：Deque deque = new LinkedList()
    3. 堆栈：Deque deque = new LinkedList()

只要我们使用 ```Deque deque = new LinkedList()``` 就可以实现堆栈，队列，双端队列的所有功能

```java
import java.util.Deque;
import java.util.LinkedList;

public class Main {
    public static void main(String[] args) {
        // 作为栈使用
        Deque<Integer> deque = new LinkedList<>();
        deque.push(12); // 入栈
        deque.size();   // 栈的大小
        deque.peek();   // 获取栈的第一个元素
        deque.pop();    // 弹出栈的第一个元素
        deque.isEmpty();// 判断栈是否为空

        // 作为队列使用
        deque.offerLast(12); // 入队
        deque.offerLast(13); // 入队
        deque.pollFirst();   // 出队
        deque.peekFirst();   // 获取队首元素
    }
}
```

## PriorityQueue (优先队列)

```java
import java.util.*;

public class Main {
    public static void main(String[] args) {
        // 创建小根堆
        PriorityQueue<Integer> queuea = new PriorityQueue<>();
        // 创建大根堆
        PriorityQueue<Integer> queueb = new PriorityQueue<>((a, b) -> (b - a));

        // 入堆
        numbers.add(4);
        numbers.offer(1);

        // 获取元素，不弹出
        numbers.peek();

        // 获取元素，弹出
        numbers.poll();
    }
}
```