# Recitation - You Want LeetCode, You Got LeetCode!

## Student Outcomes

After completing this recitation, a student will be able to

1. Use arrays to represent a solution to a requirement.
2. Use loops and nested to loops to implement a solution to a problem.

## Task 1 - List Hopping

You are given a list of integers, where each value of the list represents a hop to the next integer in the list.  Write a program that will determine if there is a hop route to the last position in the list.  A failure is determined by the inability to reach or hop beyond the last position on the list.  

For example, given the following list

```
3 1 0 1 3
```

The first entry always represents the starting list position. From the starting list position, the number 3 means hop forward 3 positions in the list.  This results in landing on the number 1 (4th integer in the list). From that position in the list, a hop of 1 will result in landing on the last position in the list. **This represents a success**.

Now consider a list like:

```
4 3 2 1 0 2 3
```

Again, start at the first list position and hop forward 4 positions, landing on 0 (5th integer in the list). From this position the last position cannot be reached because of the 0 hop. **This is a failure**.

Consider again the following list,

```
5 3 2 1 0 2 3
```

### Implementation

Implement the solution in the `lastItemReachable()` method in the Recitiation10 class.  The method should return a <span style="color:blue;">`true`</span> if the last item in the list is reachable; otherwise the method returns a <span style="color:blue;">`false`</span>.

For Example:

```
Recitation7.lastItemReachable(new int[]{5, 3, 2, 1, 0, 2, 3});
```

Should result in a <span style="color:blue;">`false`</span>. 


```
Recitation7.lastItemReachable(new int[]{5, 3, 1, 0, 1, 3});
```

Should result in a <span style="color:blue;">`true`</span>.

### Additional Information

+ You do not need to verify the correctness of the input.
+ Assume the array does not contain any negative integers.
+ You do not have to handle exceptions.


## Task 2 - Sliding Window

You are tasked with writing a program that will process a list of integers with a specified window size.  The window establishes a sub-list of integers from the list.  As the window slides, a new sub-list of integers appears.  For each sub-list, the program must display the smallest number.  For example, given a window size of 2 and the following list,

```
12 15 11 7 19 5
```

The list of integers will be divided into sub-lists of two, and the window will move one position to the right. The smallest integer for each sub-list is displayed. The list of smallest integers would be:

```
12 11 7 7 5
```

The result was obtained as follows. 

1. The initial sub-list, given the window size of 2, is 12 and 15, with 12 being the smallest of the two.	<br/> <span style="border:1px solid gray;padding:5px"><span style="background-color:black; color: white; padding:5px;">12 15</span> 11 7 19 5</span>
2.	The window slides forward one position revealing the next sub-list of 15 and 11, with 11 being the smallest of the two. 	<span style="border:1px solid gray;padding:5px">12 <span style="background-color:black; color: white; padding:5px;">15 11</span> 7 19 5</span>
3.	Sliding the window forward one position reveals the next sub-list as 11 and 7, with 7 being the smallest of the two. <br/>	<span style="border:1px solid gray;padding:5px">12 15 <span style="background-color:black; color: white; padding:5px;">11 7</span> 19 5</span>
4.	Sliding the window forward one position yields the sub-list 7 and 19, with 7 being the smallest of the two.<br/>	<span style="border:1px solid gray;padding:5px">12 15 11 <span style="background-color:black; color: white; padding:5px;">7 19</span> 5</span>
5.	Sliding the window forward one position yields the sub-list 19 and 5, with 5 being the smallest of the two.<br/>		<span style="border:1px solid gray;padding:5px">12 15 11 7 <span style="background-color:black; color: white; padding:5px;">19 5</span></span>

### Implementation

Implement the solution in the `slidingWindowMin()` method in the Recitiation10 class.  The method should return an array with the sub-list minimum values as explained above.  The size of the array should be exactly equal to the number of sub-lists possible for the given window size.

For example,

```
Recitation7.slidingWindowMin(new int[] {14, 92, 3, -7, 18, -9, 47, -12}, 4)
```

should result in an array of length 5 contaning the following,

<p>
<span style="border:1px black solid;">
<span style="border-right:1px solid black;">-7</span> <span style="border-right:1px solid black;">-7</span> <span style="border-right:1px solid black;">-9</span> <span style="border-right:1px solid black;">-9</span> -12
</span>
</p>

Another example,

```
Recitation7.slidingWindowMin(new int[] {14, 92, 3, -7}, 4)
```

should result in an array of length 1 contaning the following,

<p>
<span style="border:1px black solid;">
-7
</span>
</p>

Finally, for a window size less than or equal to zero (0) or larger than the list size, `slidingWindowMin()` should return an array of length 0!

### Additional Information

+ You do not need to verify the correctness of the input.
+ You do not have to handle exceptions.
