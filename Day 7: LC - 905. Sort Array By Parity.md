Given an integer array nums, move all the even integers at the beginning of the array followed by all the odd integers.

Return any array that satisfies this condition.

 

Example 1:

Input: nums = [3,1,2,4]
Output: [2,4,3,1]
Explanation: The outputs [4,2,3,1], [2,4,1,3], and [4,2,1,3] would also be accepted.
Example 2:

Input: nums = [0]
Output: [0]
 

Constraints:

1 <= nums.length <= 5000
0 <= nums[i] <= 5000

INSIGHTS = THIS QUESTION IS SILMILAR TO Solved LC: 2164. Sort Even and Odd Indices Independently
Just by removing those tricky constraints!

```cpp
class Solution {
public:
    vector<int> sortArrayByParity(vector<int>& nums) {
        int i, n=nums.size();
        // created different vectors for storing even elements and odd elements in vector
        vector<int> even;
        vector<int> odd;
        vector<int> ans;
        for(i=0; i<n; i++){
            if(nums[i]%2==0){
                even.push_back(nums[i]);
            }
            else{
                odd.push_back(nums[i]);
            }
        }
        // directly pushing back elements from even and odd vector to ans vector as there are no conditions - just that even elements come first
        int a=even.size(), s=odd.size();
        for(i=0; i<a; i++){
            ans.push_back(even[i]);
        }
        for(i=0; i<s; i++){
            ans.push_back(odd[i]);
        }
        return ans;
    }
};
```
