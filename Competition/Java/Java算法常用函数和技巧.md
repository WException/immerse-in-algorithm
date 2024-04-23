# Java算法常用类和函数

## String类
```java
// 查找
int indexOf(String s)       // s在字符串中首次出现的索引位置，如果没有则返回-1
int lastIndexOf(String s)   // s在指定字符串中最后一次出现的索引位置，如果没有则返回-1
boolean startsWith(String prefix, int toffset) // 查找prefix是否为字符串的前缀，toffset:查找位置 默认从0

// 获取
char charAt(int index)      // 返回index处的字符
String substring(int start, int end) // 返回索引start到end的字符串，索引从0开始 注：end要+1

// 删除/修改
String trim()               // 去除首尾的空格
String replace("被替换字符串", "替换字符串")
String toUpperCase()        // 全部转为大写字母
String toLowerCase()        // 全部转为小写字母

```

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
ceil(double x)          // 向上取整
floor(double x)	        // 向下取整
round(double x)	        // 四舍五入取整
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
sort(arr, new Comparator<T>(){})    // arr数组排序，可以传入匿名类Comparator自定义排序方式
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
// Boolean，Double等都有类似将字符串转换的方法
int parseInt(String s, int radix)  // 将s以radix进制的格式解析，转为int类型。radix默认为10
String toString(int num, int k)    // 将num转为k进制真值, k非必填
int bitCount(int num)              // 计算把num转为二进制后其中包含多少个1
```

## Calendar(操作日期)
> 常用方法
```java
/*初始化 获取当前时区的时间*/
import java.util.Calendar;
Calendar calendar = Calendar.getInstance();

// 设置指定字符串格式时间
calendar.setTime(new Date("2000/01/01 00:00:00"));

// 获取当前时间戳毫秒数
long getTimeInMillis()

```

## BigDecimal(高精度，大数)

Java中的BigDecimal类可以表示任意大小(任意精度)的数值，其范围理论上是无限的。

> 常用方式

```java
BigDecimal num1 = new BigDecimal(3);
BigDecimal num2 = new BigDecimal(2);

// 比较大小
if ( num1.compareTo(num2) == 1 ) //等同于num1 > num2

// 四则运算
num1 = num1.add(num2); // 加
num1 = num1.subtract(num2); // 减
num1 = num1.multiply(num2); // 乘
num1 = num1.divide(num2); // 除

// 取余
BigDecimal[] nums3 = num1.divideAndRemainder(num2);
// nums3包含两个元素，第一个元素为两数相除的商，第二个元素为余数。

```

# 常用技巧

竞赛中尽量使用静态环境变量，

## 快速IO

```java
import java.io.*;

public class Example {

  public static void main(String[] args) throws IOException {
      BufferedReader br = new BufferedReader(new InputStreamReader(System.in));
      StreamTokenizer in = new StreamTokenizer(br);
      PrintWriter out = new PrintWriter(new OutputStreamWriter(System.out));
      while (in.nextToken() != StreamTokenizer.TT_EOF) {
    	  // 使用in.nval读入，会自动过滤空格和换行
    	  int n = (int)in.nval;
    	  // 读完一个值之后使用in.nextToken()跳到下一个值
    	  in.nextToken();
    	  // 这里输出只是暂存到内存中了
          out.println("ans");
      }
      
      // 一次性把暂存的输出全输出，相当于只进行一次io操作
      out.flush();
      out.close();
  }
}
```
