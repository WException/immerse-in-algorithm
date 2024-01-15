# Java算法常用函数

## Math类(操作number类型)
```java
max(a, b); // 返回a和b中较大的值
min(a, b); // 返回a和b中较小的值
// 返回正确舍入的 double 值的正平方根
sqrt(double a)		
// 绝对值
abs(a)		
// a的b次方，返回一个double类型的数。
pow(double a, double b) 
// 向上取整
ceil(double x)		
// 向下取整
floor(double x)	
// 四舍五入取整
round(double x)	
// 生成一个[0,1)之间的double类型的伪随机数
random()				
// tan，cos与sin类似
// acos(-1)=π
// 正弦值
sin(double a) 
// 反正弦值
asin(double a) 			

```

## Arrays类(操作数组)
> 常用方法
```java
// 将arr数组元素变为字符串，一般用于输出看看数组情况，省去遍历的繁琐操作
toString(arr)  		
// arr数组排序，可以传入匿名类Comparator自定义排序方式
sort(arr,new Comparator<T>(){}) 	
// arr数组二分查找(需要排好序)元素ele，返回目标值索引，找不到返回-1			
binarySearch(arr,ele) 	
// 复制arr数组[from,to)位置元素，返回复制好的数组副本
copyOfRange(arr,from,to)
// 使用ele元素将数组填充
fill(arr,ele) 		
// 比较两个数组元素的内容是否完全一致
equals(arr1,arr2) 				
```

## Collections类(操作List)
> 常用方法
```java
// 仅List可用
// 反转List中的元素
reverse(list) 	
// 按照小到大对链表进行排序【默认】，也可以实现Compartor接口自定义排序
sort(list,new Cpmparator<T>(){}) 
// 将list中的i处元素和j处元素进行交换
swap(list,i,j) 
// list2拷贝到list1，要确保list1有足够空间
copy(list1,list2) 	
// 将list中的A替换成B
replaceAll(list,A,B)	
    
// List和Set都可用
// 返回最大、最小元素
max(list)/min(list) 
// ele出现次数
frequency(list,ele) 
```

## Integer
> 常用方法
```java
// Boolean，Double等都有类似将字符串转换的方法👇
// 将字符串参数解析为带符号的十进制整数
parseInt(String s) 	
// 将字符串参数解析为第二个参数指定的基数中的有符号正整数
// radix参数不填则默认以十进制数进行解析
parseInt(String s, int radix)  
// 将i转为k进制真值【有正负号】
toString(int i，k) 
```

## Calendar(操作日期)
> 常用方法
```java

```