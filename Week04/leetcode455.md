#### [分发饼干](https://leetcode-cn.com/problems/assign-cookies/)

### solution 1

```java
class Solution {
    public int findContentChildren(int[] g, int[] s) {

        int j = 0;

        Arrays.sort(g);
        Arrays.sort(s);

        for (int i = 0; i < s.length; i++) {
            System.out.println(i + "  " +j);
            if (s[i] >= g[j]) {
                j++;

                if (j >= g.length){
                    return j;
                }
            }
        }

        return j;

        

    }
}



//贪心算法大的饼干先给大的小朋友
```

comment:贪心,一开始没想到sort2个array想了O（N2）的解法写起来还很烦