#### [单词接龙](https://leetcode-cn.com/problems/word-ladder/)

### solution 1

```java
class Solution {
    public int ladderLength(String beginWord, String endWord, List<String> wordList) {

        int depth = 0;

        if (wordList == null || !wordList.contains(endWord)) {
            return 0;
        }
        
        Queue<String> queue = new LinkedList();

        boolean[] visited = new boolean[wordList.size()];

        queue.add(beginWord);

        while (!queue.isEmpty()) {
            int size = queue.size();

            depth++;

            for (int i = 0; i < size; i++) {

                String poll = queue.poll();

                for( int j = 0; j < wordList.size(); j++) {

                    if( visited[j]) {
                        continue;
                    }

                    if (!canConvert(poll, wordList.get(j))) {
                        continue;
                    }

                    if (endWord.equals(wordList.get(j))) {
                        return depth + 1;
                    }

                    queue.add(wordList.get(j));

                    visited[j] = true;

                }


            }
        }

        return 0;
       
        
    }

    public boolean canConvert(String s1, String s2) {
        int count = 0;
        for (int i = 0; i < s1.length(); ++i) {
            if (s1.charAt(i) != s2.charAt(i)) {
                ++count;
                if (count > 1) {
                    return false;
                }
            }
        }
        return count == 1;
    }


}
//n叉树层序遍历
```

comment:BFS没用char有点慢，双向BFS还不太懂

