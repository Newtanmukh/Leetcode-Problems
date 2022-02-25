class Solution {
public:
    bool checkValid(vector<vector<int>>& matrix) {
        int n = matrix.size();
        vector<set<int>> rows(n), cols(n);
        
        for (int i = 0; i < n; i++) {
            for (int j = 0; j < n; j++) {
                
                int curr = matrix[i][j] - '0';
                if (rows[i].count(curr) || cols[j].count(curr)) 
                    return false;
                
                rows[i].insert(curr);
                cols[j].insert(curr);
            }
        }
        
        return true;
    }
};