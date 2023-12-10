## Pointer
```
void modify(int *a, int *b){
    int tempA = *a;
    *a = tempA + *b;
    *b = abs(tempA - *b);
}