学习笔记

BFS模板

```java
void BFS(int s){
	queue<int> q;
	q.push(s); 
	while(!q.empty()){
		取出队首元素top;
		访问队首元素top；
		将队首元素出队；
		将top的下一层结点未曾入队的结点全部入队，并设置为已入队
	}
} 
```

图的遍历也可以用BFS，不局限于树