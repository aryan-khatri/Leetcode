# Mother's and Father's Day Challenges – Day 25

> **Tags**: #java #50daysofcode #DrGvishwanathanChallenge #shriramsir

##  Day 25:
**Problem Description** - [DSA](https://leetcode.com/problems/implement-stack-using-queues/description/) <br>
Solution
```java
class MyStack {
    private LinkedList<Integer> q1;
    public MyStack() {
        q1 = new LinkedList<>();
    }

    public void push(int x) {
        q1.add(x);
        int size = q1.size();
        while (size > 1) {
            q1.add(q1.remove());
            size--;
        }
    }
    
    public int pop() {
        return q1.remove();
    }

    public int top() {
        return q1.peek();
    }

    public boolean empty() {
        return q1.isEmpty();
    }
}
```

---

**Problem Description** - [EASY DSA](https://leetcode.com/problems/rotate-array/description/) <br>
Solution - 
```java
class Solution {
    public void rotate(int[] nums, int k) {
        int n = nums.length;
        k = k % n;
        if (k == 0) return;
        rotateByRange(nums, 0, n - 1);
        rotateByRange(nums, 0, k - 1);
        rotateByRange(nums, k, n - 1);
    }
    private void rotateByRange(int[] nums, int x, int y){
        while (x >= 0 && x < y){
            int temp = nums[x];
            nums[x] = nums[y];
            nums[y] = temp;
            x++;
            y--;
        }
    }
}
```
