# P2910[USACO08OPEN]Clear And Present Danger S

洛谷 [题目链接](https://www.luogu.com.cn/problem/P2910)。

> Floyd，模板题

### C++代码

### Java代码

```Java
import java.util.Scanner;

public class Main {

    static int n;
    static int m;
    static int[][] map;
    static int[] path;

    public static void main(String[] args) {
        Scanner scan = new Scanner(System.in);
        n = scan.nextInt();
        m = scan.nextInt();

        map = new int[n + 1][n + 1];
        path = new int[m];
        for (int i = 0; i < m; i++) {
            path[i] = scan.nextInt();
        }

        for (int i = 1; i <= n; i++) {
            for (int j = 1; j <= n; j++) {
                map[i][j] = scan.nextInt();
            }
        }

        // Floyd
        for (int k = 1; k <= n; k++) {
            for (int i = 1; i <= n; i++) {
                for (int j = 1; j <= n; j++) {
                	map[i][j] = Math.min(map[i][j], map[i][k] + map[k][j]);
                }
            }
        }
        long ans = 0;
        for (int i = 1; i < m; i++) {
            ans += map[path[i - 1]][path[i]];
        }
        System.out.println(ans);
        scan.close();
    }
}
```

### Python3代码