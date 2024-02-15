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

```java
Stack<Integer> stack = new Stack<>(); // 初始化
stack.push(1); // 入栈
stack.pop(); // 出栈
```

在Java中不推荐使用```Vector```及其子类```Stack``` 一般使用```LinkedList```。

```java
LinkedList<Integer> stack = new LinkedList<>(); // 初始化
stack.addLast(1); // 入栈
stack.removeLast(); // 出栈
```

## 队列

队列是一种具有 先入先出 特点的抽象数据结构，可使用链表实现

```java
Queue<Integer> queue = new LinkedList<>(); // 初始化
queue.offer(1); // 入队
queue.poll(); // 出队
```

## PriorityQueue (优先队列)
[优先队列](https://www.cainiaojc.com/java/java-priorityqueue.html)