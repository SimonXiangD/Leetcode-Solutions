# 1. Two Sum
- Method 1:

    two loops, direct idea

    |      time       | O(n^2) |  
    | ----------- | ----------- | 
    |   memory     | O(1)  | 


- Method 2：

    define an array of pairs, pair contains the original array member and its index, define an comparator to sort it and use front and back pointer
    |      time       | O(nlogn)  |  
    | ----------- | ----------- | 
    |  memory     | O(n)  | 

- Method 3:
    use a hash to record, as hash takes average O(1), worst O(n) to find

    |      time       | O(n)   |  
    | ----------- | ----------- | 
    |  memory     | O(n)  | 

    solution:

    ```
    class Solution {
    public:
        vector<int> twoSum(vector<int>& nums, int target) {
            unordered_map<int, int> umap;
            for(int i = 0; i < nums.size(); i++) {
                if(umap.find(target - nums[i]) != umap.end()) {
                    return {umap[target - nums[i]], i};
                }
                umap[nums[i]] = i;
            }
            return {-1, -1};
        }
    };
    ```

- Additional Knowledge:
       
    What is the difference between map and unordered_map in c++ ? 

    |             | ordered_map | unordered_map |
    | ----------- | ----------- | ----------- |
    | implementation      | RB tree  | hash map |
    | find time   | O(logn)        | average O(1), worst O(n)|
    | insert time   | O(logn)        | average O(1), worst O(n)|
    | delete time   | O(logn)        | average O(1), worst O(n)|
    | suitable for   | ordered case        | frequent find|



<br>