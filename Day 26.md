# Mother's and Father's Day Challenges – Day 26

> **Tags**: #java #50daysofcode #DrGvishwanathanChallenge #shriramsir

##  Day 26:
**Problem Description** - [DSA](https://leetcode.com/problems/find-first-and-last-position-of-element-in-sorted-array/submissions/1644302150/) <br>
Solution
```java
class Solution {
    public int[] searchRange(int[] nums, int target) {
        if(nums == null) return new int[]{-1, -1};
        int len = nums.length;
        int index = binarySearch(0, len - 1, nums, target);
        if(-1 == index) return new int[]{-1, -1};
        else{
            int high = index;
            while(++high < len && nums[high] == target){};
            int low = index;
            while(--low >= 0 && nums[low] == target){}
            return new int[]{low + 1, high - 1};
        }
    }
    private static int binarySearch(int low, int high, int[] nums, int target){
        if(low > high)
            return -1;
        int mid = low + (high - low) / 2;
        int midVal = nums[mid];
        if(midVal == target) return mid;
        if(midVal > target)
            return binarySearch(low, mid - 1, nums, target);
        else
            return binarySearch(mid + 1, high, nums, target);
    }
}
```

---

**Problem Description** - [EASY DSA](https://leetcode.com/problems/binary-tree-inorder-traversal/submissions/1644298719/) <br>
Solution - 
```java
/**
 * Definition for a binary tree node.
 * public class TreeNode {
 *     int val;
 *     TreeNode left;
 *     TreeNode right;
 *     TreeNode() {}
 *     TreeNode(int val) { this.val = val; }
 *     TreeNode(int val, TreeNode left, TreeNode right) {
 *         this.val = val;
 *         this.left = left;
 *         this.right = right;
 *     }
 * }
 */
class Solution {
    public List<Integer> inorderTraversal(TreeNode root) {
        List<Integer> rst = new ArrayList<>();
        if (root == null) return rst;
        List<Integer> left = inorderTraversal(root.left);
        List<Integer> right = inorderTraversal(root.right);
        rst.addAll(left);
        rst.add(root.val);
        rst.addAll(right);
        return rst;
        
    }
}
```
