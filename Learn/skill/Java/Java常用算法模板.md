# Java常用算法模板
### 质数判断
```java
// 大于等于5的质数一定和6的倍数相邻，1不是质数
// 判断素数的方法，已知1不是素数，在主函数中去除1即可
public static boolean isPrimeNumber(int n) {
    if (n == 2 || n == 3) return true;
    if ((n - 1) % 6 == 0 || (n + 1) % 6 == 0) {
        // 当前可能是素数
        for (int i = 2; i <= Math.sqrt(n); i++) {
            if (n % i == 0) return false;
        }
        return true;
    }
    return false;
}
```
### 最大公因数/最小公倍数
```java
// 最大公约数，此法原理为欧几里得算法，可以理解为是发现的一个规律，不必深究
int gcd(int a, int b) {
    return b == 0 ? a : gcd(b, a % b);
}

// 最小公倍数=两数之积/两数最大公约数
int lcm(int a, int b) {
    return a * b / gcd(a, b);
}

```