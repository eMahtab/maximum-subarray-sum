# Maximum Contiguous Subarray Sum (Kadane's Algorithm)

For array [-2, 1, -3, 4, -1, 2, 1, -5, 4] the maximum contiguous subarray sum is 6 [4, -1, 2, 1]

We can use the Kadane's algorithm to find the maximum contiguous subarray sum in just one iteration through the input array.

```java
class Solution {
    public int maxSubArray(int[] nums) {
        if(nums == null || nums.length == 0)
            return 0;
        
        int maxSum = nums[0];
        int currentMax = nums[0];
        for(int i = 1; i < nums.length; i++){
            currentMax = Math.max(nums[i], nums[i]+currentMax);
            maxSum = Math.max(maxSum, currentMax);
        }
        return maxSum;
    }
}

```

```
Runtime Complexity : O(n)
Space Complexity   : O(1)
```
