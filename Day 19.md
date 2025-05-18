# Mother's and Father's Day Challenges – Day 19

> **Tags**: #java #50daysofcode #DrGvishwanathanChallenge #shriramsir

##  Day 19:
[**DSA**](https://leetcode.com/problems/valid-parentheses/) <br>
Solution
```java
class Solution {
    public boolean isValid(String s) {
        if (s == null) return true;
        if (s.length() % 2 != 0) return false;

        Stack<Character> stack = new Stack<>();
        for (char c : s.toCharArray()) {
            if (stack.isEmpty() || (c == '(' || c == '{' || c == '[')) stack.push(c);
            else if (validate(stack.peek(), c)) stack.pop();
            else return false;
        }
        return stack.isEmpty();
    }
    
    private boolean validate(char a, char b) {
        if (a == '(') return b == ')';
        if (a == '{') return b == '}';
        if (a == '[') return b == ']';
        return false;
    }
}
```
---
[**EASY DSA**](https://leetcode.com/problems/contains-duplicate/description/) <br>
Solution - 
```java
class Solution {
    public int maxProfit(int[] prices) {
        int result = 0;
        if(prices == null || prices.length == 0)
            return result;
        int maxPro = 0;
        int minPrice = Integer.MAX_VALUE;
        int len = prices.length;
        for(int i = 0; i < len; i++){
            minPrice = Math.min(minPrice, prices[i]);
            maxPro = Math.max(maxPro, prices[i] - minPrice);
        }
        return maxPro;
    }
}
```


