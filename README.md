Download Link: https://assignmentchef.com/product/solved-csc-385-assignment-4-faster-sorting-algorithms
<br>
This problem is taken from a hackerrank programming challenge. The problem is tagged as having medium difficulty in hacker rank:

<a href="https://www.hackerrank.com/challenges/fraudulent-activity-notifications">(</a><a href="https://www.hackerrank.com/challenges/fraudulent-activity-notifications">https://www.hackerrank.com/challenges/fraudulent</a><a href="https://www.hackerrank.com/challenges/fraudulent-activity-notifications">–</a><a href="https://www.hackerrank.com/challenges/fraudulent-activity-notifications">activity</a><a href="https://www.hackerrank.com/challenges/fraudulent-activity-notifications">–</a><a href="https://www.hackerrank.com/challenges/fraudulent-activity-notifications">notifications</a> <a href="https://www.hackerrank.com/challenges/fraudulent-activity-notifications">)</a>

<strong> </strong><strong>Problem Description—Fraud Detection </strong>

HackerLand National Bank has a simple policy for warning clients about possible fraudulent account activity. If the amount spent by a client on a particular day is <em>greater than or equal to </em>2 ×the client’s <a href="https://en.wikipedia.org/wiki/Median">median</a> <a href="https://en.wikipedia.org/wiki/Median">s</a>pending for the last d days, they send the client a notification about potential fraud. The bank doesn’t send the client any notifications until they have at least <strong>d </strong>prior days of transaction data.

Given the value of <strong>d </strong>and a client’s total daily expenditures for a period of <strong>n </strong>days (where n&gt;d) write a method which returns the number of times the client will receive a notification over all days.




<strong>Note: Your algorithm efficiency should not exceed O(nd) </strong>where n is the total number of daily expenditures and d is the number of prior day expenditures used for fraud detection.




<em> </em>

<strong>What you need to do: </strong>

To receive full credit, your method must have the following signature:




<strong>public int </strong>getNumberOfFrauds(<strong>int</strong>[] dailyExpeditures, <strong>int </strong>d)







For example:




getNumberOfFrauds({4,3,2,2,3,6,8,9,10}, 5) must return 3







<strong>Explanation: </strong>We must determine the total number of notifications the client receives over a period of days. For the first five days, the customer receives no notifications because the bank has insufficient transaction data and the number of notifications are zero.

On the sixth day, the bank has 5 days of prior transaction data {4,3,2,2,3} and the median is 3 dollars, the client spent 6 dollars on the sixth day which triggers a notification because 6 &gt;=2* median, so the number of notifications after sixth day is 1. On the seventh day, the bank has 5 days of prior transaction data {3,2,2,3,6} and the median is 3 dollars, the client spent 8 dollars on the seventh day which triggers a notification because 8 &gt;=2* median, so the number of notifications after seventh day is

2.

On the eights day, the bank has 5 days of prior transaction data {2,2,3,6,8} and the median is 3 dollars, the client spent 9 dollars on the eighth day which triggers a

notification because 9&gt;=2* median, so the number of notifications after eighth day is 3. On the ninth day, the bank has 5 days of prior transaction data {2,3,6,8,9} and the median is 6 dollars, the client spent 10 dollars on the ninth day which does not triggers a notification because 10&lt;2* median, so the number of notifications after ninth day stays at 3.

We then return the final value of notifications which is 3.




<strong>Hints: </strong>You can store the first d day spending in another array and sort this array using a fast sorting algorithm such as quick sort. For instance, for the above example, the sorted array would be {2,2,3,3,4}. Compare the next day spending ( 6 dollars) with the median and update the number of frauds. Then replace the first day spending (4 dollars) with d+1 day spending (6 dollars) in the sorted array, that is: {2,2,3,3,6}. If the resulting array is not sorted, shift array elements until it is sorted again. Find the median and compare it with d+2 day spending and update the number of frauds. Next, replace the second day spending ( 3 dollars) with d+2 day spending (8 dollars) in the sorted array, that is: {2,2,8,3,6}. If the resulting array is not sorted, shift the array elements until it is sorted again {2,2,3,6,8}. Find the median and compare it with d+3 day spending and update the number of frauds. Continue this process until you get to the last day spending and return the number of frauds.

Once you write your program you can test it on hacker Rank against their extensive test cases <a href="https://www.hackerrank.com/challenges/fraudulent-activity-notifications">(</a><a href="https://www.hackerrank.com/challenges/fraudulent-activity-notifications">https://www.hackerrank.com/challenges/fraudulent</a><a href="https://www.hackerrank.com/challenges/fraudulent-activity-notifications">–</a><a href="https://www.hackerrank.com/challenges/fraudulent-activity-notifications">activity</a><a href="https://www.hackerrank.com/challenges/fraudulent-activity-notifications">–</a><a href="https://www.hackerrank.com/challenges/fraudulent-activity-notifications">notifications</a> <a href="https://www.hackerrank.com/challenges/fraudulent-activity-notifications">)</a> . If it passes all the test cases on hacker rank then your program is probably correct. It is fun. I had to fix my program about 3-4 times before it could pass very large test cases on hacker rank.







<strong>What you need to turn in:</strong>

<ol>

 <li>Please enclose your <strong>getNumberOfFrauds </strong>method together with all the helper methods and attributes you use in a class called “<strong>java</strong>”. You don’t need to include a driver (main method) to test your method. I will test your program against my own test harness or against the hacker rank test cases. <strong>Please note that you cannot use Arrays.sort or any other Java library for sorting. You can; however, use quicksort code from the lectures or textbook. </strong></li>

</ol>




<ol>

 <li>Please include a document with your submission which briefly describe your algorithm and determine its time efficiency in terms of order of magnitude (Big Oh). Don’t just say that my algorithm is O(nd). We already know that.</li>

</ol>

<strong>Explain how you arrived at this time efficiency. </strong><strong> </strong>




<strong>Grading Rubric </strong>

<strong> </strong>

<table width="639">

 <tbody>

  <tr>

   <td width="319">Your program correctly returns the number of frauds and passes all the test cases on hacker</td>

   <td width="319">14</td>

  </tr>

  <tr>

   <td width="319"><strong>Analysis of time efficiency of your algorithm </strong></td>

   <td width="319">3</td>

  </tr>

  <tr>

   <td width="319">The time efficiency of your algorithm does not exceed O(nd)</td>

   <td width="319">3</td>

  </tr>

  <tr>

   <td width="319">Total</td>

   <td width="319">20</td>

  </tr>

 </tbody>

</table>


