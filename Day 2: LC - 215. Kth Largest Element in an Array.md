Given an integer array nums and an integer k, return the kth largest element in the array.

Note that it is the kth largest element in the sorted order, not the kth distinct element.

You must solve it in O(n) time complexity.

 

Example 1:

Input: nums = [3,2,1,5,6,4], k = 2
Output: 5
Example 2:

Input: nums = [3,2,3,1,2,4,5,5,6], k = 4
Output: 4
 

Constraints:

1 <= k <= nums.length <= 105
-104 <= nums[i] <= 104

```cpp
class Solution {
public:
    int findKthLargest(vector<int>& nums, int k) {
        int i,j, n=nums.size(),ans;
        // we have to find kth largest element in sorted order
        sort(nums.begin(), nums.end());
        for(i=0; i<n; i++){
            while(nums[i]==nums[j]){
                //erasing duplicate elements 
                nums.erase(nums.begin()+i, nums.end());
                break;
            }
        }
        //returning kth largest element (traverse from last)
        ans=nums[n-k];
        return ans;
    }
};
```
