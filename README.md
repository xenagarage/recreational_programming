1st Algorithm: Orchard Division

<!DOCTYPE HTML PUBLIC "-//W3C//DTD HTML 4.01//EN" "http://www.w3.org/TR/html4/strict.dtd">
<html>
<head>
  <meta HTTP-EQUIV="Content-Type" CONTENT="text/html; charset=iso-8859-2">
  <meta http-equiv="cache-control" content="no-cache">
  <link rel="stylesheet" type="text/css" href="default.css" />
</head>
<body>
 <div class="main">

<h2><font color="blue">Orchard division</font></h2>

<p align="justify">
Quido has a square orchard full of various fruit and nut trees. The trees are planted in regular rows and columns forming a rectangular grid. There are as many rows as there are columns. To be able to maintain the orchard more easily Quido wants to divide the orchard into four rectangular parts. First, he will divide the orchard into northern and southern part by one straight path running from east to west between two rows of the trees. Next, he will divide the northern part by one straight path running from the north perpendicularly to the east-west path. The southern part will be divided similarly by a straight path running from south perpendicularly to the east-west path. These two additional path need not to meet at the same point. The resulting situation might look like the one in the picture bellow.
</p>

<p align="justify">
Quido has assigned a quality index to each tree, the index may be positive or negative or zero. The quality of each of four parts of the orchard will be the sum of qualities of all trees in that part. Quido wants the resulting parts to be of similar quality, in fact, he wants the qualities of the four parts be as close to each other as possible. Therefore, he must choose the positions of the three dividing paths according to this demand.
</p>

<table border="0" width="680" align="center">
<tr>
<td align="center">
<img style="width: 200px; height: 200px;" src="https://github.com/user-attachments/assets/dd04f6d7-a852-4af9-adbc-7d63be34f711"/>

<b>Image 1.</b> An example of orchard divided according to Quido's demands. Values represent the qualities of the trees. The qualities of the four parts are (clockwise from north-west)  10, 8, 13, 11. The maximum difference of qualities of any two parts in this division is 5.
  </td>
</tr>
</table>


 <p align="justify">
<b><font style="color: blue">The task</font></b><br>
You are given the quality of each tree in the orchard. The task is to divide the the orchard in the way described above so that the difference between the quality of the part of the highest quality and the part of the lowest quality is minimized.
</p>

<hr>


<h3><font color="blue">Input</font></h3>
<p align="justify">
The input contains more text lines describing the orchard. The first line contains single integer <i>N</i> specifying the size of the orchard. There are  <i>N</i> &times; <i>N</i> trees in the orchard. Each of next <i>N</i> lines specifies one row of trees in the orchard. The line contains <i>N</i> integers separated by one or more spaces. Each integer represents a quality of one tree. The order of lines and the order of values on the lines reflect exactly the order of the trees in the orchard. <br>
All tree qualities are integers from the interval &lang; &minus;10<sup>6</sup>, 10<sup>6</sup> &rang;. The value of <i>N</i> will not exceed 3025.
</p>

<i></i>
<b></b>
<sub></sub>
<sup></sup>


<h3><font color="blue">Output</font></h3>
<p align="justify">
The output contains one integer representing the minimum possible difference between the quality of the part of the highest quality and the part of the lowest quality among all possible divisions of the orchard in the Quido's plan.  The output value is supposed to be non-negative and it will not exceed 10<sup>8</sup>.
</p>


<h3><font color="blue">Example 1</font></h3>
<b>Input</b>
<pre>
5
 3   0   2  -8  -8
 5   3   2   2   3
 2   5   2   1   4
 3   4  -1   4   2
-3   6   2   4   3
</pre>

<b>Output</b>
<pre>
5
</pre>

The Example 1 represents the situation in the Image 1 above.

<h3><font color="blue">Example 2</font></h3>
<b>Input</b>
<pre>
6
1  2  3   4   5   6
2  4  6   8  10   8
3  6  9  12   9   6
4  8 12   8   4   0
5 10  5   0  -5 -10
6  0 -6 -12 -18 -24
</pre>

<b>Output</b>
<pre>
16
</pre>

The orchard should be divided according to the following scheme, the qualities of the four parts are (clockwise from north-west)
30, 29, 14, 18.
<pre>
  1   2   3   4|  5   6
  2   4   6   8| 10   8 
........................
  3|  6   9  12   9   6
  4|  8  12   8   4   0 
  5| 10   5   0  -5 -10 
  6|  0  -6 -12 -18 -24
</pre>

<h3><font color="blue">Example 3</font></h3>
<b>Input</b>
<pre>
8
100 -1 -2 -3 -4 -5 -6 -7
 -1 -1 -1 -1 -1 -1 -1 -1
 -1 -1 -1 -1 -1 -1 -1 -1
 -1 -1 -1 -1 -1 -1 -1 -1
 -1 -1 -1 -1 -1 -1 -1 -1
 -1 -1 -1 -1 -1 -1 -1 -1
 -1 -1 -1 -1 -1 -1 -1 -1
 30 -1 -1 -1 -1 -1 -1 -30
</pre>

<b>Output</b>
<pre>
67
</pre>

The orchard should be divided according to the following scheme, the qualities of the four parts are (clockwise from north-west)
 37, &minus;13, &minus;30, 24.
<pre>
100  -1  -2  -3  -4  -5  -6| -7
 -1  -1  -1  -1  -1  -1  -1| -1 
 -1  -1  -1  -1  -1  -1  -1| -1 
 -1  -1  -1  -1  -1  -1  -1| -1 
 -1  -1  -1  -1  -1  -1  -1| -1 
 -1  -1  -1  -1  -1  -1  -1| -1 
 -1  -1  -1  -1  -1  -1  -1| -1 
................................
 30  -1  -1  -1  -1  -1  -1|-30
</pre>

<br>
<hr>
<h3>Public data</h3>
<p align="justify">
The public data set is intended for easier debugging and approximate program correctness checking.
</p>
<a href="https://github.com/user-attachments/files/17341028/datapub.zip"><h3>Public data set</h3></a>
</div>
</body>

</html>
