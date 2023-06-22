# 26. Remove Duplicates from Sorted Array
- Method 1

    Just use two pointers.

    | |   Complexity  |
    | ----------- | ----------- | 
    |  Memory     | O(1)  | 
    |      Time       |  O(n) | 


    Solution:

    ```
    class Solution {
    public:
        int removeDuplicates(vector<int>& nums) {
            int left = 0, right = 0;
            while(right < nums.size()) {
                if(right == 0 || nums[right] != nums[right-1]) nums[left++] = nums[right];
                right++;
            }
            return left;
        }
    };
    
    ```
