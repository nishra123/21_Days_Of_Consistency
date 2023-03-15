Given an integer array nums, move all 0's to the end of it while maintaining the relative order of the non-zero elements.

Note that you must do this in-place without making a copy of the array.

 

Example 1:

Input: nums = [0,1,0,3,12]
Output: [1,3,12,0,0]
Example 2:

Input: nums = [0]
Output: [0]
 

Constraints:

1 <= nums.length <= 104
-231 <= nums[i] <= 231 - 1
 

Follow up: Could you minimize the total number of operations done?


```cpp
class Solution {
public:
    void moveZeroes(vector<int>& nums) {
        int i,j, n=nums.size(),temp;
        // using a nested loop to swap zeroes with non-zero numbers
        for(i=0; i<n; i++){
            for(j=i+1; j<n; j++){
                if((nums[i]==0) && nums[j]!=0){
                    // at this point I didn't know that cpp had an in-built swap function!
                    temp=nums[i];
                    nums[i]=nums[j];
                    nums[j]=temp;
                }
            }
        }
        // returning the required array
        for(i=0; i<n; i++){
            cout<<nums[i]<<",";
        }
    }
};
```
