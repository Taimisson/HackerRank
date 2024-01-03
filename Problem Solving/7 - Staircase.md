# Staircase

Its base and height are both equal to . It is drawn using # symbols and spaces. The last line is not preceded by any spaces.

Write a program that prints a staircase of size 

[Staircase - HackerRank](https://www.hackerrank.com/challenges/staircase/problem?isFullScreen=true)

# Solution

```
void staircase(int n)
{
    string s="";
    for(int i = 0; i < n; ++i)
    {
        s+='#';
        cout<< setw(n) << right << s << "\n";
    }
}
```