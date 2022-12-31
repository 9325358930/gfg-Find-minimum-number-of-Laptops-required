# gfg-Find-minimum-number-of-Laptops-required
Problem of the day31

Example 1:

Input:
N = 3
start[] = {1, 2, 3}
end[] = {4, 4, 6}
Output:
3
Explanation:
We can clearly see that everyone's supposed to
be doing their job at time 3. So, 3 laptops
will be required at minimum.

class Solution {
  public:
    int minLaptops(int N, int start[], int end[]) {
        // Code here
        sort(start, start+N);
        sort(end, end+N);
        
        int ans = 0;
        int count = 0;
        int i = 0, j = 0;
        while(i< N){
            if(start[i] < end[j]){
                count++;
                ans = max(ans, count);
                i++;
            }
            else{
                count--;
                j++;
            }
        }
        return ans;
    }
};
