class Solution {
public:
    vector<int> topKFrequent(vector<int>& nums, int k) 
    {
        vector<int> v;
        unordered_map<int, int> count_map;
        for(auto n: nums) count_map[n]++;
        priority_queue<pair<int, int>, vector<pair<int, int>>, greater<pair<int,int>>> minHeap;
        for(auto& pair: count_map) 
        {
            minHeap.emplace(pair.second, pair.first);
            if(minHeap.size() > k) minHeap.pop();
        }
        while(k--)
        {
            v.push_back(minHeap.top().second);
            minHeap.pop();
        }
        return v;
    }
};