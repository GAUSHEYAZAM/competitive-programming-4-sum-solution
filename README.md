# competitive-programming-4-sum-solution









class Solution {
public:
    vector<vector<int>> fourSum(vector<int>& nums, int target) {
        int n=nums.size();
        vector<vector<int>> arr;
        sort(nums.begin(), nums.end());
       for(int i=0;i<n-3; i++){
           if(i>0 && nums[i]==nums[i-1] ){
               continue;
           }
           
           for(int j=i+1;j<n-2; j++){
               if(j>i+1 && nums[j]==nums[j-1]){
                   continue;
               }
               
               int l=j+1;
               int r=n-1;
               
               while(l<r){
                   if(l>j+1 && nums[l]==nums[l-1]){
                       l++;
                       continue;
                   }
                   if(r<n-1 && nums[r]==nums[r+1]){
                       r--;
                       continue;
                   }
                   if(nums[i]+nums[j]+nums[l]+nums[r]== target){
                       arr.push_back({nums[i], nums[j], nums[l], nums[r]});
                       l++;
                       r--;
                   }
                   else if(nums[i]+nums[j]+nums[l]+nums[r]>target){
                       r--;
                   }else{
                       l++;
                   }
               }
               
           }
       }
        return arr;
        
    }
};
