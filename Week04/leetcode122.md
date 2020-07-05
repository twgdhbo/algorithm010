#### [买卖股票的最佳时机 II](https://leetcode-cn.com/problems/best-time-to-buy-and-sell-stock-ii/)

### solution 1

```java
class Solution {
    public int maxProfit(int[] prices) {
        
        int m = 0;
        int j = 0;

        for (int i = 1; i < prices.length; i++) {

            //买入
            if (prices[i] > prices[j]) {
                m = m + prices[i] - prices[j];
                j = i;

            }else {
                j++;
            }

        }

        return m;
        
    }

    
}
```

comment:贪心