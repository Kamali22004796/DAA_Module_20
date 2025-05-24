# EX 2C BACKTRACKING- SUBSET SUM PROBLEM
## AIM:
To demonstrate that the sum of the subset of a given set is equal to the given sum.

## Algorithm:
```
1. Input the size of the array.
2. Input the array elements.
3. Input the target sum value.
4. Define a recursive function SubsetSum(a, i, sum, target, n) to check if a subset with the target sum exists.
5. If end of list is reached, return True if sum equals target, else False.
6. If sum exceeds target, return False.
7. Otherwise, recursively check with and without including the current element.
8. Call SubsetSum(a, 0, 0, target, n).
9. If it returns True, print the array and "True, subset found".
10. Else, print the array and "False, subset not found".
```

## Program:
```
Developed by: Kamali E
Register Number:  212222110015

def SubsetSum(a,i,sum,target,n):
    if i==n:
        return sum==target
    if sum>target:
        return False
    if sum==target:
        return True
    return SubsetSum(a,i+1,sum,target,n) or SubsetSum(a,i+1,sum+a[i],target,n)
a=[]
size=int(input())
for i in range(size):
    x=int(input())
    a.append(x)

target=int(input())
n=len(a)
if(SubsetSum(a,0,0,target,n)==True):
    for i in range(size):
        print(a[i])
    print("True,subset found")
else:
    for i in range(size):
        print(a[i])
    print("False,subset not found")
```

## Output:
![Screenshot 2025-04-29 113951](https://github.com/user-attachments/assets/a66cd300-41d7-48e8-9015-f337970d4815)

## Result:
The Subset Sum program executed successfully, and the result was determined based on whether a subset matching the target sum was found or not.
