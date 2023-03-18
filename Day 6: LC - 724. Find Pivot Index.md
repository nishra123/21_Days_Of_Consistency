Given an array of integers nums, calculate the pivot index of this array.

The pivot index is the index where the sum of all the numbers strictly to the left of the index is equal to the sum of all the numbers strictly to the index's right.

If the index is on the left edge of the array, then the left sum is 0 because there are no elements to the left. This also applies to the right edge of the array.

Return the leftmost pivot index. If no such index exists, return -1.

 

Example 1:

Input: nums = [1,7,3,6,5,6]
Output: 3
Explanation:
The pivot index is 3.
Left sum = nums[0] + nums[1] + nums[2] = 1 + 7 + 3 = 11
Right sum = nums[4] + nums[5] = 5 + 6 = 11
Example 2:

Input: nums = [1,2,3]
Output: -1
Explanation:
There is no index that satisfies the conditions in the problem statement.
Example 3:

Input: nums = [2,1,-1]
Output: 0
Explanation:
The pivot index is 0.
Left sum = 0 (no elements to the left of index 0)
Right sum = nums[1] + nums[2] = 1 + -1 = 0
 

Constraints:

1 <= nums.length <= 104
-1000 <= nums[i] <= 1000
 
 
 ```cpp
 class Solution {
public:
    int pivotIndex(vector<int>& nums) {
        int i, n=nums.size(), ans;
        for(int i=0;i<n;i++){  
            int left_sum=0;  
            int right_sum=0;  
            // calculate left sum of each index (see here the constraints in for loop)  - only from 0 to i
            for(int j=0;j<i;j++){  
             left_sum+=nums[j];  
            }  
            // calculate right sum of each index  - from i + 1  to n
            for(int j=i+1;j<n;j++){  
             right_sum+=nums[j];  
            }
            if(left_sum==right_sum){
                return i;
            }
        }  
        return -1;
    }
};
```

INSIGHTS - I was not knowing how to calculate sum of array elements to the left of the given index !
I searched for it and then I got it that the index for doing so will be from o to i.

I even searched for the solution of this question on chatgpt as I was so frustrated and here's what I got - 

```cpp
#include <vector>
using namespace std;

int pivotIndex(vector<int>& nums) {
    int sum = 0;
    int left_sum = 0;
    // first calculating total sum of all array elements
    for (int i = 0; i < nums.size(); i++) {
        sum += nums[i];
    }
    for (int i = 0; i < nums.size(); i++) {
        // now subtracting the array element and left sum from tottal sum and checking if it is equal to right sum or not
        if (left_sum == sum - left_sum - nums[i]) {
            return i;
        }
        // increasing left sum
        left_sum += nums[i];
    }
    return -1;
}
```
It was like the old school hip hop where in Maths if we have been given total sum and left sum then we can calculate right sum as rsum=total-lsum and hence I liked this solution and wanted to share over here.
