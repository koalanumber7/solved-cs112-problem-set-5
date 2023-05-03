Download Link: https://assignmentchef.com/product/solved-cs112-problem-set-5
<br>
<strong>Problem Set 5</strong>

<strong>Sequential Search, Binary Search</strong>

<ol>

 <li>Given the following sequence of integers:</li>

</ol>

3, 9, 2, 15, -5, 18, 7, 5, 8

<ol>

 <li>What is the average number of comparisons for a successful search assuming all entries are searched with equal probability? Show your work.</li>

 <li>Suppose the search probabilities for the elements of this list are, respectively: 1, 0.3, 0.05, 0.2, 0.05, 0.1, 0.05, 0.1, 0.05</li>

</ol>

What is the average number of comparisons for successful search with these search probabilities? Show your work.

<ol start="3">

 <li>Rearrange the list entries in a way that would result in the lowest number of comparisons on the average for successful search, given the above probabilities of search. What is this lowest number of comparisons? Show your work.</li>

</ol>

<ol start="2">

 <li>An adaptive algorithm to lower average match time for sequential search is to move an item by one spot toward the front every time it is matched. (Unless it is already at the front, in which case nothing is done on a match.) Complete the following modified sequential search on a linked list with this move-toward-front adaption. Assume a generic Node class with data and next</li>

</ol>

public class LinkedList&lt;T&gt; {          private Node&lt;T&gt; front;          int size;

…

// moves the target one place toward the front

// doesn’t do anything if target is in the first node

// returns true if target found, false otherwise          public boolean moveTowardFront(T target) {

// COMPLETE  THIS METHOD

}

}

<ol start="3">

 <li>Draw the comparison tree for binary search on a sorted array of length 11.

  <ol>

   <li>What is the worst case number of comparisons for success? For failure?</li>

   <li>What is the average number of comparisons for success, assuming equal likelihood of success at any spot?</li>

   <li>What can you say about the average number of comparisons for failure? Can you approximate it within a small range? Does it depend on the distribution of the probabilities of failing at the various failure spots?</li>

  </ol></li>

 <li><strong>*</strong> A variant of binary search, called <em>lazy</em> binary search, works as described in the following algorithm, where t is the target to search, and n is the size of the array:</li>

</ol>

left &lt;– 0     right &lt;– n-1     while (left &lt; right) do         mid &lt;– (left + right)/2        if (t &gt; A[mid]) then           left &lt;– mid + 1        else            right &lt;– mid        endif     endwhile

if (t == A[left]) then

display “found at position”, left     else

display “not found”     endif




<ol>

 <li>Trace this algorithm on the following array, with 46 as the search target:</li>

</ol>

10   15   25   30   45   46   48   72   76   80   93

How many comparisons are made by the time a match is found? How does your answer compare with that for regular binary search?

<ol start="2">

 <li>Repeat with 40 as the target. How many comparisons are made until failure is detected? How does your answer compare with that for regular binary search?</li>

 <li>Draw the comparison tree for lazy binary search on an array of length 11 (same length as the example array above).

  <ol>

   <li>What is the worst case number of comparisons for success? For failure?</li>

   <li>What can you say about the range of values for the average number of comparisons for success? For failure?</li>

   <li>Under what conditions is it preferable to use lazy binary search over the regular binary search?</li>

   <li>An alternative algorithm for searching on a sorted array of size <em>n</em> works as follows. It divides the array into <em>m</em> contiguous blocks each of size <em>s</em>. (Assume that <em>s</em> divides into <em>n</em> without remainder).</li>

  </ol></li>

</ol>

Here is the algorithm to search for a key <em>k</em> in sorted array <em>A</em>.

Compare <em>k</em> with the last entry in the first block, i.e. <em>A[s-1]</em>

If there is match, then stop with success

Otherwise, check if <em>k</em> &lt; <em>A[s-1]</em>

If so, perform a sequential search on the block of entries from  <em>A[0]</em> to <em>A[s-2]</em>. If there is a match, stop with success, otherwise stop with failure.




If <em>k</em> is not &lt; <em>A[s-1]</em> then continue the process by repeating the above on the second block, and so on.




<ol>

 <li>What is the <strong>worst</strong> case number of searches for success?</li>

 <li><strong>**</strong> What is the <strong>average</strong> case number of searches for success?</li>

</ol>