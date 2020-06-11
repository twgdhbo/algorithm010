#### [移动零](https://leetcode-cn.com/problems/move-zeroes/)

### solution 1

```java
class Solution {
    public void moveZeroes(int[] nums) {

        //shift times
        int j = 0;
        for (int i = 0; i < nums.length; i++) {
            if (nums[i] != 0 ){
                if(i > j) {
                     nums[j] = nums[i];
                     nums[i] =0;
                }
                j++;
                }

        } 
    }
    //two pointers
    // j current 0 index, after swap +1
}
```

comment:if (i > j)