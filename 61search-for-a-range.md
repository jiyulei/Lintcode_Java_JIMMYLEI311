

**题目：**

Given a sorted array of n integers, find the starting and ending position of a given target value.

If the target is not found in the array, return \[-1, -1\].

  


**Example**

Given \[5, 7, 7, 8, 8, 10\] and target value 8,  
 return \[3, 4\].

先找到左边界 再找到右边界

  


`public class Solution {`

`  
`

` /**`

` *@param A : an integer sorted array`

` *@param target : an integer to be inserted`

` *return : a list of length 2, [index1, index2]`

` */`

`  
`

` public int[] searchRange(int[] A, int target) {`

` // write your code here`

` int[] results = new int[2];`

` if (A == null || A.length == 0) {`

` results[0] = -1;`

` results[1] = -1;`

` return results;`

` }`

` int start = 0;`

` int end = A.length - 1;`

` int first = -1;`

` int last = -1;`

` while (start + 1 < end) {`

` int mid = start + (end - start) / 2;`

` if (A[mid] < target) {`

` start = mid;`

` } else if (A[mid] > target) {`

` end = mid;`

` } else {`

` end = mid;`

` }`

` }`

` if (A[start] == target) {`

` first = start;`

` } else if (A[end] == target) {`

` first = end;`

` }`



` start = first;`

` end = A.length - 1;`

` while (start + 1 < end) {`

` int mid = start + (end - start) / 2;`

` if (A[mid] < target) {`

` start = mid;`

` } else if (A[mid] > target) {`

` end = mid;`

` } else {`

` start = mid;`

` }`

` }`

` if (A[end] == target) {`

` last = end;`

` } else if (A[start] == target) {`

` last = start;`

` }`



` if (first == -1 || last == -1) {`

` results[0] = -1;`

` results[1] = -1;`

` return results;`

` }`

` results[0] = first;`

` results[1] = last;`

` return results;`

` }`

`}`

`  
`

`  
`

