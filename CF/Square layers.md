Suppose you're given an `n x m` array where both n and m are even = is a square.

We can traverse the layers in such square like this:
```cpp
for (int i = 0; (i + 1) * 2 <= n && (i + 1) * 2 <= m; i++) {
	// here we can perform w/e operations on that layer
	// also the number of elements in this layer is 2*(n+m-1)
}
```

Notice that we use the same `i` variable for both row and col increments and go by multiplies of 2. This is easier to work with than having 2 variables for current row and col and starting from n, m respectively.