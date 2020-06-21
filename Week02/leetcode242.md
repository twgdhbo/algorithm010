#### [有效的字母异位词](https://leetcode-cn.com/problems/valid-anagram/)

### solution 1

```java
class Solution {
    public boolean isAnagram(String s, String t) {

        HashMap<Character, Integer> map = new HashMap();

        for(int i=0;i<s.length();i++) {
             char c=s.charAt(i);
             if (map.containsKey(c)) {
                map.put(c, map.get(c) + 1);
            }else {
                map.put(c, 1);
            }

        }


        for(int i=0;i<t.length();i++){
             char c=t.charAt(i);
            if (map.containsKey(c)) {
                map.put(c, map.get(c) - 1);
            }else {
                map.put(c, 1);
            }

        }
           
        for(Integer value : map.values()){
             if (value != 0) {
                 return false;
             }
        }

        return true;
    }
}
```

comment:HashMap 速度较慢,空间也大