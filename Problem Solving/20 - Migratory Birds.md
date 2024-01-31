# Migratory Birds

Given an array of bird sightings where every element represents a bird type id, determine the id of the most frequently sighted type. If more than 1 type has been spotted that maximum amount, return the smallest of their ids.

[Migratory Birds - HackerRank](https://www.hackerrank.com/challenges/migratory-birds/problem?isFullScreen=true)

# Solution

```
int migratoryBirds(vector<int> arr) {
    map<int, int> birds;
    for(int i = 0; i < arr.size(); ++i)
        birds[arr[i]]++;
        
    int maxType = 0, maxCount = 0;
    
    for(auto const &pair : birds)
        if(pair.second > maxCount){
            maxCount = pair.second;
            maxType = pair.first;
        }else if(pair.second == maxCount && pair.first < maxType)
            maxType = pair.first;
    
    return maxType;
}
```