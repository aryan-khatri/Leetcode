# Mother's and Father's Day Challenges  
**#Java #50DaysOfCode #DrGVishwanathanChallenge #ShriramSir**

---

## Day 15: DSA and Math-Based Challenges

### 🔹 DSA-Based Challenge  
**Problem**: [Add Two Numbers (Linked List)](https://lnkd.in/dTbq5PJb)  
**Language**: Java

```java
/**
 * Definition for singly-linked list.
 * public class ListNode {
 *     int val;
 *     ListNode next;
 *     ListNode(int x) { val = x; }
 * }
 */
class Solution {
    public ListNode addTwoNumbers(ListNode l1, ListNode l2) {
        int carry = 0;
        ListNode res = new ListNode(0);
        ListNode cur = res;

        while (l1 != null || l2 != null) {
            int val = carry;
            if (l1 != null) {
                val += l1.val;
                l1 = l1.next;
            }
            if (l2 != null) {
                val += l2.val;
                l2 = l2.next;
            }
            cur.next = new ListNode(val % 10);
            carry = val / 10;
            cur = cur.next;
        }

        if (carry > 0) {
            cur.next = new ListNode(carry);
        }

        return res.next;
    }
}
```

---

### 🔹 Math-Based Challenge  
**Problem**: [Excel Sheet Column Title](https://lnkd.in/dGcUw6DU)  
**Language**: Java

```java
class Solution {
    public String convertToTitle(int n) {
        StringBuilder sb = new StringBuilder();

        while (n > 0) {
            int tmp = (n - 1) % 26;
            sb.append((char) ('A' + tmp));
            n = (n - 1) / 26;
        }

        return sb.reverse().toString();
    }
}
```
