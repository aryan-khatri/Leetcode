# Mothers and Father's Day Challenges - Day 17

## DSA Based Challenge

**Problem Link:** [Min Stack Problem](https://leetcode.com/problems/min-stack/)

### Solution (Java)
```java
class MinStack {
    private Deque<Integer> stk1 = new ArrayDeque<>();
    private Deque<Integer> stk2 = new ArrayDeque<>();

    public MinStack() {
        stk2.push(Integer.MAX_VALUE);
    }

    public void push(int val) {
        stk1.push(val);
        stk2.push(Math.min(val, stk2.peek()));
    }

    public void pop() {
        stk1.pop();
        stk2.pop();
    }

    public int top() {
        return stk1.peek();
    }

    public int getMin() {
        return stk2.peek();
    }
}
```

# Easy DSA Challenge

## Problem Link
[Two Sum Problem](https://leetcode.com/problems/two-sum/)

## Solution (Java)
```java
class Solution {
    public int[] twoSum(int[] nums, int target) {
        if (nums != null && nums.length > 1) {
            for (int i = 0; i < nums.length; i++){
                for (int j = 0; j < nums.length ; j++){
                    if (i == j) {
                        continue;
                    }
                    if (nums[i] + nums[j] == target){
                        int[] res = new int[2];
                        res[0] = i;
                        res[1] = j;
                        return res;
                    }
                }
            }
            return null;
        } else {
            return null;
        }
    }
}
