# EX:2C - BACKTRACKING - SUBSET SUM PROBLEM
## DATE:

## AIM:

To demonstrate that the sum of the subset of a given set is equal to the given sum.


## Algorithm

1. Read an integer `n` for the size of the array, take n inputs to form the array `arr`.
2. Read the integer `x`, the target sum to be achieved by subsets.
3. Use a loop to generate subsets of all lengths from `0` to `n` using `combinations(arr, i)`.
4. For each generated subset, calculate the sum of its elements. If the sum of the current subset is equal to `x`, consider it a valid subset.
5. Print each subset that matches the target sum.

   
## Program:

```
# Program to implement Subset sum problem

# DEVELOPED BY: YOHESH KUMAR R.M
# REGISTER NUMBER : 212222240118

from itertools import combinations;

def subsetSum(n, arr, x):
	
	# Iterating through all possible
	# subsets of arr from lengths 0 to n:
	for i in range (n+1):
		for subset in combinations(arr, i):
			# printing the subset if its sum is x:
			if sum(subset) == x:
				print(list(subset))

n=int(input())
arr=[]
for i in range(0,n):
    a=int(input())
    arr.append(a)
x = int(input())

subsetSum(n, arr, x)

```

## Output:

![image](https://github.com/user-attachments/assets/861485be-da38-4535-a598-ae8846c7b46f)


## Result:

The Subset Sum program executed successfully, and the result was determined based on whether a subset matching the target sum was found or not.
