# leetcode----1128
Number of Equivalent Domino pairs
//code in java
import java.util.HashMap;
import java.util.Map;

class Solution {
    public int numEquivDominoPairs(int[][] dominoes) {
        Map<Integer, Integer> count = new HashMap<>();
        int pairs = 0;
        for (int[] domino : dominoes) {
            int key = Math.min(domino[0], domino[1]) * 10 + Math.max(domino[0], domino[1]);
            pairs += count.getOrDefault(key, 0);
            count.put(key, count.getOrDefault(key, 0) + 1);
        }
        return pairs;
    }
}
