# 11. Container With Most Water
- Method 1

    Just use two loops, brute effective method.

    | |   Complexity  |
    | ----------- | ----------- | 
    |  Memory     | O(1)  | 
    |      Time       |  O(n^2) | 

    <!-- <br> -->

- Method 2

    Use two pointers. Actually, suppose we have left and right, with height tl and tr, then if the higher pair is somewhere between [tl, tr], then we can add left or sub right by comparing tl and tr. 
    
    W.L.O.G we assume tl > tr, then all pairs with first element bigger than left will have smaller amount water, as it is lagged by tr which is smaller than tl. 

    The special case is tl = tr, then we have to add left and sub right at the same time, as the optimal pair will neither begin at left nor end at right.

    Code is easy, but the idea behind it is not that apprent. I remember the first time I was solving the problem, I got stuck and tried to use some optimizing tricks. However, once I got the idea, this problem is really easy. Also, think before coding saves time at most cases, if not all.

    | |   Complexity  |
    | ----------- | ----------- | 
    |  Memory     | O(1)  | 
    |      Time       |  O(n) | 

    Solution:

    ```
    class Solution {
    public:
        int maxArea(vector<int>& height) {
            int left = 0, right = height.size() - 1;
            int maxVal = 0;
            while(left < right) {
                int leftVal = height[left];
                int rightVal = height[right];
                int tmp = min(leftVal, rightVal) * (right - left);
                maxVal = max(tmp, maxVal);
                if(leftVal > rightVal) right--;
                else if(leftVal < rightVal) left++;
                else {left++; right--;}
            }
            return maxVal;
        }
    };
    ```
