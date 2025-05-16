Mothers and Father's Day Challenges Day  
Day 12 :

 **Maths Based Problem**  
 [Count Odd Numbers in an Interval Range](https://leetcode.com/problems/count-odd-numbers-in-an-interval-range/description/)

 **DSA Based Problem**  
 [Insert Greatest Common Divisors in Linked List](https://leetcode.com/problems/insert-greatest-common-divisors-in-linked-list/description/)

```java
// Maths Based Problem
class Solution {
    public int countOdds(int low, int high) {
        return ((high + 1) >> 1) - (low >> 1);
    }
}
```


// DSA Based Problem
```java
/**
 * Definition for singly-linked list.
 * public class ListNode {
 *     int val;
 *     ListNode next;
 *     ListNode() {}
 *     ListNode(int val) { this.val = val; }
 *     ListNode(int val, ListNode next) { this.val = val; this.next = next; }
 * }
 */
class Solution {
    public ListNode insertGreatestCommonDivisors(ListNode head) {
        for (ListNode pre = head, cur = head.next; cur != null; cur = cur.next) {
            int x = gcd(pre.val, cur.val);
            pre.next = new ListNode(x, cur);
            pre = cur;
        }
        return head;
    }

    private int gcd(int a, int b) {
        if (b == 0) return a;
        return gcd(b, a % b);
    }
}
```
