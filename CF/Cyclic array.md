Suppose we're looking for a subarray in an array. However, we can also find this subarray in a cyclic manner. For example:

We'd look for a subarray that sums up to 8 in the following array
```
[1,2,3,4]
```

We can form a subarray which sums up to 8 by using 3+4+1, however, the 1 is not at the end but rather cycles back the front of the array.

In order to access the elements in this manner, we will use `mod len(list)`
```cpp
auto nums = {1,2,3,4};
int n = nums.size();
for (int i = 0; i < n; i++) {
	if (nums[i] + nums[(i+1) % n] + nums[(i+2) % n]) {
		return {i, (i+1) % n, (i+2) % n};
	}
}
```