#### [岛屿数量](https://leetcode-cn.com/problems/number-of-islands/)

### solution 1

```java
class Solution {
       public int numIslands(char[][] grid) {
        if (grid == null || grid.length == 0 || grid[0].length == 0) return 0;

        int count = 0;
        for (int row = 0; row < grid.length; row++) {
            for (int col = 0; col < grid[0].length; col++) {
                if (grid[row][col] == '1') {
                    dfs(grid, row, col);
                    count++;
                }
            }
        }
        return count;
    }

    private void dfs(char[][] grid,int row,int col) {
        if (row<0||row== grid.length||col<0||col==grid[0].length||grid[row][col]!='1') {
            return;
        }
        grid[row][col] = '0';
        dfs(grid, row-1, col);
        dfs(grid, row+1, col);
        dfs(grid, row, col+1);
        dfs(grid, row, col-1);
    }

}
```

comment:count++的位置想不太清楚
