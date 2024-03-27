# Java常用算法模板

### 最大公约数 and 最小公倍数
```java
// 求 a，b 的最大公约数
static int gcd(int a, int b){
	return b == 0 ? a : gcd(b, a % b);
}
// 求 a，b 的最小公倍数
static int lcm(int a, int b){
	return a * b / gcd(a, b);
}
```

### 质数判断
```java
// 大于等于5的质数一定和6的倍数相邻，1不是质数
// 判断素数的方法，已知1不是素数，在主函数中去除1即可
static boolean isPrime(int num){
	if (num == 0 || num == 1) return false;
    for (int i = 2; i <= Math.sqrt(num); i++) {
        if(num%i == 0) return false;
    }
    return true;
}
```

### 前缀和(Prefix Sum)

```java

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

### BFS
```java
import java.util.Scanner;
import java.util.LinkedList;
import java.util.Queue;
/*
使用bfs广度优先搜索
*/
public class Main {
    public static void main(String[] args) {
        Scanner scan = new Scanner(System.in);
        int N=scan.nextInt(),M=scan.nextInt();
        int[][] map = new int[150][150];//地图
        int[][] flg = new int[150][150];//0-未走，1-已走
        Queue<Point> r = new LinkedList<Point>();//队列
        int[] dx = {0,1,0,-1};
        int[] dy = {1,0,-1,0};
        for(int i=1;i<=N;i++)
            for(int j=1;j<=M;j++)
                map[i][j] = scan.nextInt();
        int start_x=scan.nextInt(), start_y=scan.nextInt();//起点
        int end_x=scan.nextInt(), end_y=scan.nextInt();//终点

        //开始bfs
        Point point = new Point(start_x,start_y,0);
        r.offer(point);//起点入队
        flg[start_x][start_y] = 1;
        
        while(!r.isEmpty()){
            //判断现在队首是否在终点
            int x=r.peek().x;
            int y=r.peek().y;
            if(x==end_x && y==end_y){
                System.out.println(r.peek().step);
                return;
            }
            //四个方向试探
            for(int k=0;k<4;k++){
                int tx = x+dx[k];
                int ty = y+dy[k];
                if(map[tx][ty]==1 && flg[tx][ty]==0){
                    //入队
                    r.offer(new Point(tx,ty,r.peek().step+1));
                    flg[tx][ty] = 1;
                }
            }
            r.poll();//拓展完了需要将队首元素出队
        }
        System.out.println(-1);
        scan.close();
    }
}
class Point{
    int x;
    int y;
    int step;
    public Point(){}
    public Point(int x,int y,int step){
        this.x=x;
        this.y=y;
        this.step=step;
    }
}
```