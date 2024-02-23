# Electronics Shop

A person wants to determine the most expensive computer keyboard and USB drive that can be purchased with a give budget. Given price lists for keyboards and USB drives and a budget, find the cost to buy them. If it is not possible to buy both items, return .

[Electronics Shop - HackerRank](https://www.hackerrank.com/challenges/electronics-shop/problem?isFullScreen=true)

# Solution

```
int getMoneySpent(vector<int> keyboards, vector<int> drives, int budget) {
    int mostExpensive = -1;
    
    sort(keyboards.begin(), keyboards.end());
    sort(drives.begin(), drives.end());
    
    for(int i = 0; i < keyboards.size(); ++i){
        for(int j = 0; j < drives.size(); ++j){
            int sum = keyboards[i] + drives[j];
            if(sum > budget) break;
            if(sum > mostExpensive) mostExpensive = sum;
        }
    }
        
    return mostExpensive;
}
```