class Solution {
    public int findContentChildren(int[] g, int[] s) {
        Arrays.sort(g);
        Arrays.sort(s);
        int count=0;
        for(int i=g.length-1,j=s.length-1; j>=0 && i>=0 ;i--)
        {
            if(s[j]>=g[i]) 
            {
                count++;
                j--;
            }
        }
        return count;
    }
}