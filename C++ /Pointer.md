## Pointer
```
void modify(int *a, int *b){
    int tempA = *a;
    *a = tempA + *b;
    *b = abs(tempA - *b);
}


int main() {
    
    int a;
    int b;
    cin >> a >> b;
    
    modify(&a, &b);
    
    cout << a << endl;
    cout << b << endl;
    
    return 0;
}
```