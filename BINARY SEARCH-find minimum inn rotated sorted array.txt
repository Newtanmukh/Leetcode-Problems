class Solution {
public:
    int findMin(vector<int>& nums) {
        int s = 0;
        int e = nums.size()-1;
        int mid;
        
        while(s<=e){
            mid = (s+e)/2;
            
            if(nums[mid] >= nums[e]){
                s = mid+1;
            }
            else{
                e = mid;
            }
        }
        return nums[mid];
        
    }
};