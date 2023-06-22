# 27. Remove Element
- Method 1

    Just use two pointers. Similar to 26

    | |   Complexity  |
    | ----------- | ----------- | 
    |  Memory     | O(1)  | 
    |      Time       |  O(n) | 


    Solution:

    ```
    class Solution {
    public:
        int removeElement(vector<int>& nums, int val) {
            int left = 0, right = 0;
            while(right < nums.size()) {
                if(nums[right] != val) nums[left++] = nums[right];
                right++;
            }
            return left;
        }
    };

    ```
