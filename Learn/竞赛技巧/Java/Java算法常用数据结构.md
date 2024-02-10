# Java算法常用数据结构

## ArrayList(链表)
```java
// 默认将元素添加到链表尾，可以通过index添加到指定位置
add(ele)
// 移除指定位置元素
remove(index)
// 修改指定位置元素
set(index,element)
// 得到指定位置元素
get(index)
// 返回第一次/最后一次出现某元素的索引
indexOf/lastIndexOf(ele)
//返回大小/是否为空
size()/isEmpty()
// 链表变数组
toArray()
// 字符串形式输出【若要输出自定义形式，可以遍历后用StringBuilder拼接】
toString()
```
## LinkedList(栈和队列)

> 栈常用方法

```java
// 栈顶插入元素
push(ele)   
// 返回栈顶元素并弹出    
pop()   
//返回栈顶元素但不弹出
peek()    
```
> 队列常用方法

```java
// 头插
addFirst(ele)
// 尾插
addLast(ele)
// 获取队列头元素    
getFirst()
// 获取队列尾元素    
getLast
// 获取头元素并弹出
poll()
// 获取尾元素并弹出     
pollLast() 
// 删除指定索引元素    
remove(index)
// 返回首次出现某元素的索引
indexOf(ele)
```

## PriorityQueue (优先队列)
[优先队列](https://www.cainiaojc.com/java/java-priorityqueue.html)