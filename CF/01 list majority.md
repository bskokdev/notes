If I need to find a majority across a vector of 0s and 1s I can sum them up and see if the sums is >= threshold

### Example
```cpp
int n;
cin >> n;
int res = 0;
while (n-- > 0) {
	int a, b, c;
	cin >> a >> b >> c;
	res += (a + b + c >= 2);
}
```
Here I want to add one to res only if there's more than or equal to 2 ones in the vector. Therefore I can take the sum compare it to the threshold and add one if it's true. In C++ true boolean expression evaluates to 1 and false to 0.