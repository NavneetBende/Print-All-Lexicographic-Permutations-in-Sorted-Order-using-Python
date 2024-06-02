Lexicographic Permutations in Sorted Order
Here, on this page, we will learn the program to Print All Lexicographic Permutations in Sorted Order using Python Programming language. We are given with string and need to print them.

Lexicographic Permutations in Sorted Order

Algorithm ( Method 1 )
Sort and print the given string in ascending order
The string sorted in non-decreasing order is always the first permutation
Begin creating the next higher permutation
Continue until the next higher permutation is no longer conceivable
When we arrive at a permutation in which all characters are arranged in non-increasing order, we have arrived at the final permutation
Lexicographic Permutations in Sorted Order using Python
Python Code
Run

ans = []


def permute(a, l, r):
    if l == r:
        ans.append(''.join(a))
    else:
        for i in range(l, r):
            a[l], a[i] = a[i], a[l]
            permute(a, l + 1, r)
            a[l], a[i] = a[i], a[l]


string = "ABC"
n = len(string)
a = list(string)
permute(a, 0, n)
for i in sorted(ans):
    print(i)
Output
ABC 
ACB 
BAC 
BCA 
CAB 
CBA
