---
tags: [dynamic programming]
---
Finding the longest palindrome in the string RACECAR. 
A cell (i, j) corresponds to a substring S[i...j] . For example, cell (1, 5) corresponds to Substring RACEC.  
The table will be filled by filling each cell in a row starting from the bottom row and then moving to the next row above. At each step if a substring is found to be palindrome, it's length can be compared to the maximum length string seen so far.  

- Each single letter substring is a palindrome by definition.  
- Each double letter substring can be readily checked to be a palindrome.  
- A string S[i...j] is a palindrome if both S[i] = S[j] and S[i+1...j-1] is a palindrome. The S[i+1...j-1] string is the string obtained by removing the first and the last letters of the S[i..j] string. It corresponds to the cell diagonally below the S[i...j]  string.  

The highlighted cell is the maximum length Palindromic substring. In this case it is the string itself. :)

![](https://chaitanyavardhan-blog-assets.s3.amazonaws.com/Palindromic_Substring_1.png)  
![](https://chaitanyavardhan-blog-assets.s3.amazonaws.com/Palindromic_Substring_2.png)   
