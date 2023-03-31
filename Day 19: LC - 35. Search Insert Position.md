Given a sorted array of distinct integers and a target value, return the index if the target is found. If not, return the index where it would be if it were inserted in order.

You must write an algorithm with O(log n) runtime complexity.

 

Example 1:

Input: nums = [1,3,5,6], target = 5
Output: 2
Example 2:

Input: nums = [1,3,5,6], target = 2
Output: 1
Example 3:

Input: nums = [1,3,5,6], target = 7
Output: 4
 

Constraints:

1 <= nums.length <= 104
-104 <= nums[i] <= 104
nums contains distinct values sorted in ascending order.
-104 <= target <= 104


INSIGHTS - Another application of Binary Search!

```cpp
class Solution {
public:
    // applying binary search 
    int BinarySearch(vector<int> &nums, int start, int end, int target){
        while(start<=end){
            int mid= start + (end-start)/2;
            // here search nums[mid] and compare
            if(nums[mid]>=target){
                end=mid-1;
            }
            else{
                start=mid+1;
            }
        }
        return start;
    }
    
    int searchInsert(vector<int>& nums, int target) {
        // initialize start as 0 and end as nums.size()-1
        return BinarySearch(nums, 0, nums.size()-1, target);
    }
};
```
