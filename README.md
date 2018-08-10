# Pseudo-Code-of-Common-Algorithms



## 1. KnapSack Problem 

*Problem Statement* - Given a Knapsack of a maximum capacity of W and N items each with its own value and weight, throw in items inside the Knapsack such that the final contents has the maximum value.

Let 'n' be the number of the objects. 

Let 'c' be the capacity of the bag.

Let 'P' be the total profit.

Let 'Pi' be the profit of the i-th object

Let 'Wi' be the weight of the i-th object

```
for i = 1 to n {
	compute Pi/Wi  
}

Sort object in non-increasing order of the Pi/Wi ratio.

In Sorted List -> for i=1 to n {
	if(c > 0 && Wi < c) {
	c = c - Wi;
	P = P + Pi;
	}
	else break;
	if(c > 0) {
	P = P + Pi(c/Wi);
	}
}

return P;
```

## 2. Huffman Coding 

*Principle* - The principle is to use a lower number of bits to encode the data that occurs more frequently.

Let 'c' be the set of the characters.

```
Huffman(c) {
	n = |c|
	make a min-heap 'Q' with 'c'
	for i = 1 to n {
	Allocate new node 'z' 
	z.left = x = Extract-min(Q);
	z.right = y = Extract-min(Q);
	z.frequency = x.frequency + y.frequency; //frequency is the number of occurences present of the character.
	Insert(Q,z);
	return (Extract-min(Q))
	}
}	
```

## 3. 0/1 KnapSack 

Let {w1,w2,w3,.....wN} be the weights of the 'n' objects.

Let {p1,p2,p3,.....,pN} be the profits of the 'n' objects.

Let wI be the weight of the i-th object.

Let pI be the profit of the i-th object.

Let 'C' be the capacity of the bag.

```
for i = 0 to c do
T[0,i] = 0;

for i = 1 to n {
	T[0,i] = 0;
	for j = 1 to C {
	if ( (wI <= j) && T[i-1, j-wI] + pI > T[i-1, j] ) then 
	T[i,j] = T[i-1, j-wI] + pI; // if we include the object
	else 
	T[i,j] = T[i-1, j]; // if we dont include the object
	}
}
```

## 4. Longest Common Subsequences

*Problem Statement* - Given two sequences, find the length of longest subsequence present in both of them. A subsequence is a sequence that appears in the same relative order, but not necessarily contiguous.

Let 'X' be one string.

Let 'Y' be another string.

LCS(X, Y) is the function which takes two strings and find the longest common subsequences in those strings.


```
LCS(X, Y) {
	m = X.length;
	n = Y.length;

	Let C(0...m, 0...n) be a new table.

for i=1 to m 
c[i,0] = 0;
for j=0 to n
c[0,j] = 0;

for i=1 to m {
	for j=1 to n {
	if (xI = yJ) {
	c[i, j] = c[i-1, j-1] + 1;
	} else {
	c[i,j] = max(c[i-1, j], c[i, j-1]);
	}
	}
}
return c;
} 
```
> More will be updated.
