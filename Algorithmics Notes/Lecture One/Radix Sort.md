# Radix Sort 

## Exercise One

Suppose we want to sort the following sequence with **Radix Sort**: 

`15, 43, 5, 27, 60, 18, 26, 2]`

Binary encodings are given by: 

| Value | Binary String |
| ----- | ------------- |
| 15    | 001111        |
| 43    | 101011        |
| 5     | 000101        |
| 27    | 011011        |
| 60    | 111100        |
| 18    | 010010        |
| 26    | 011010        |
| 2     | 000010        |

And given: 
- **m = 6**
- **b = 3**

This means that in **Radix Sort**, we have: 

**2<sup>b</sub> = 2<sup>3</sup> = 8** buckets labelled **0, 1, 2, 3, 4, 5, 6, 7** (or equivalently **000, 001, 010, 011, 100, 101, 110, 111**)
and **m/b = 2** iterations are required.

### 1st Iteration 

An item is placed in a bucket corresponding to the integer represented by the bits in positions:
- **(b x i) - 1, ..., b x (i - 1)**
- **(3 x 1) - 1, ..., 3 x (1 - 1)**
- **2 ... 0**

| 000 | 001 | 010 | 011 | 100 | 101 | 110 | 111 |
| --- | --- | --- | --- | --- | --- | --- | --- |
|     |     | 18  | 43  | 60  | 5   |     | 15  |
|     |     | 26  | 27  |     |     |     |     |
|     |     | 2   |     |     |     |     |     |

### New Sequence: [18, 26, 2, 43, 27, 60, 5, 15]

| Value | Binary String |
| ----- | ------------- |
| 18    | 010010        |
| 26    | 011010        |
| 2     | 000010        |
| 43    | 101011        |
| 27    | 011011        |
| 60    | 111100        |
| 5     | 000101        |
| 15    | 001111        |

### 2nd Iteration 

An item is placed in a bucket corresponding to the integer represented by the bits in positions:
- **(b x i) - 1, ..., b x (i - 1)**
- **(3 x 2) - 1, ..., 3 x (2 - 1)**
- **5 ... 3**

| 000 | 001 | 010 | 011 | 100 | 101 | 110 | 111 |
| --- | --- | --- | --- | --- | --- | --- | --- |
| 2   | 15  | 18  | 26  |     | 43  |     | 60  |
| 5   |     |     | 27  |     |     |     |     |

### Final (Sorted) Sequence: [2, 5, 15, 18, 26, 27, 43, 60]