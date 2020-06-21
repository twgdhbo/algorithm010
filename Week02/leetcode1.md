#### [两数之和](https://leetcode-cn.com/problems/two-sum/)

### solution 1

```java
class Solution {
    public int[] twoSum(int[] nums, int target) {

        HashMap<Integer, Integer> map = new HashMap<>();
        for (int i = 0; i < nums.length; i++) {
            int key = target - nums[i];
            if (map.containsKey(key)) {
                return new int[]{i, map.get(key)};
            }
             map.put(nums[i], i); 
        }   
        throw new IllegalArgumentException("No two sum solution");
    }
}
```

comment:HashMap 先写map.put()会导致返可能回第一个数的wrong case