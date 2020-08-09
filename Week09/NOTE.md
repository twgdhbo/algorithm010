学习笔记

不同路径2 dp方程

```java
if (obstacleGrid[i][j] == 0 ) {
	dp[i][j] = dp[i - 1][j] + dp[i][j-1];
}else {
    dp[i][j] = 0;
}
```

