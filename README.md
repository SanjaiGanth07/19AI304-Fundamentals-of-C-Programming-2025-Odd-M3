# 19AI304-Fundamentals-of-C-Programming-2025-Odd-M3
# IAPR-3- Module 3 - FoC
5. Implementation of one-dimensional array and multidimensional array.
6. Implementation of string manipulation.
# Ex.No:11
  Formulate a C program to convert a given decimal number into its binary equivalent and display it.
## Aim:
To formulate a C program to convert a decimal number into its binary equivalent and display it.
## Algorithm:
Step 1: Start<br>
Step 2: Include the standard input-output library: #include<stdio.h>.<br>
Step 3: Declare variables: num (input number), rem (remainder), binary[] (array to store binary digits), and loop counters i and k.<br>
Step 4: Read the decimal number from the user.<br>
Step 5: Initialize i = 0.<br>
Step 6: Repeat while num > 0:<br>
  Divide num by 2 and store the remainder in binary[i].<br>
  Increment i.<br>
  Update num = num / 2.<br>
Step 7: Display the binary digits in reverse order (from i-1 down to 0).<br>
Step 8: Stop<br>
## Program:
```
#include <stdio.h>
int main() {
    int n;
    printf("Enter a decimal number: ");
    scanf("%d", &n);
    if (n == 0) { printf("0"); return 0; }
    int bin[32], i = 0;
    while (n > 0) { bin[i++] = n % 2; n /= 2; }
    for (i--; i >= 0; i--) printf("%d", bin[i]);
    return 0;
}
```
## Output:
<img width="289" height="53" alt="image" src="https://github.com/user-attachments/assets/ab0b92af-2fad-477e-91d3-78d6afdea5d3" />

## Result: 
Thus, the program was implemented and executed successfully, and the required output was obtained.


# Ex.No:12
  Develop a C program to read a matrix and find its saddle point. A saddle point is an element that is the minimum in its row and also the maximum in its column. If such an element exists, display its position and value.
## Aim:
  To develop a C program that inputs a matrix, checks each row for its minimum element, verifies whether that element is also the maximum in its corresponding column, and displays the saddle point and its position if it exists.
## Algorithm:
Step 1: Start<br>
Step 2: Include the standard input-output library: #include<stdio.h>.<br>
Step 3: Declare variables i, j, k, m, min, max and a position array pos[2][2].<br>
Step 4: Read the order of the square matrix m.<br>
Step 5: Declare an m × m matrix and read its elements.<br>
Step 6: Display the matrix.<br>
Step 7: For each row `i` from `0` to `m−1`:<br>
  Step 7.1: Set `min` as the first element of the row.  <br>
  Step 7.2: Scan the row to find its minimum element and store its position in `pos[0]`.  <br>
  Step 7.3: Let `j` be the column of this minimum element.  <br>
  Step 7.4: Set `max` as the first element of column `j`.  <br>
  Step 7.5: Scan column `j` to find its maximum element and store its position in `pos[1]`.  <br>
Step 8: Check if the row minimum equals the column maximum:<br>
  If `min == max` **and their positions match**, then the element is a **saddle point**.<br>
  Print the saddle point value and its position.<br>
Step 9: Stop
## Program:
```
#include <stdio.h>
int main() {
    int m,i,j,k,flag=0;
    printf("Enter order: ");
    scanf("%d",&m);
    int a[m][m];
    for(i=0;i<m;i++)
        for(j=0;j<m;j++)
            scanf("%d",&a[i][j]);

    for(i=0;i<m;i++) {
        int min=a[i][0], col=0;
        for(j=1;j<m;j++) if(a[i][j]<min){ min=a[i][j]; col=j; }
        int max=a[0][col];
        for(k=1;k<m;k++) if(a[k][col]>max) max=a[k][col];
        if(min==max) {
            printf("Saddle point at (%d,%d) = %d\n",i,col,min);
            flag=1;
        }
    }
    if(!flag) printf("No saddle point\n");
    return 0;
}
```
## Output:
<img width="279" height="138" alt="image" src="https://github.com/user-attachments/assets/0890a346-d55a-4e0b-a32b-eac095eb7bec" />

## Result: 
Thus, the program was implemented and executed successfully, and the required output was obtained.


# Ex.No:13
  Formulate a C program to reverse a string entered by the user and display the reversed string.
## Aim:
  To formulate a C program that reads a string from the user, reverses it, and prints the reversed string.
## Algorithm:
Step 1: Start<br>
Step 2: Include the standard input-output library: #include<stdio.h>.<br>
Step 3: Declare two character arrays: `s` to store the input string and `d` to store the reversed string.<br>
Step 4: Read the string from the user using `scanf("%[^\n]s", s);`<br>
Step 5: Find the length of the string `s` by traversing it until the null character `'\0'` is encountered.<br>
Step 6: Initialize a counter `j` for the reversed string.<br>
Step 7: Copy characters from the end of `s` to the beginning of `d` using a loop until all characters are copied in reverse order.<br>
Step 8: Terminate the reversed string `d` with the null character `'\0'`.<br>
Step 9: Print the reversed string.<br>
Step 10: Stop<br>
## Program:
```
#include <stdio.h>
#include <string.h>
int main() {
    char s[100];
    printf("Enter a string: ");
    scanf("%[^\n]s", s);
    for (int i = strlen(s)-1; i >= 0; i--)
        printf("%c", s[i]);
    return 0;
}
```
## Output:
<img width="232" height="61" alt="image" src="https://github.com/user-attachments/assets/3c19adec-a59e-4472-8143-25230a9dea08" />

## Result: 
Thus, the program was implemented and executed successfully, and the required output was obtained.


# Ex.No:14
  Formulate a C program to count the frequency of each character in a given string and display the count of every character.
## Aim:
  To formulate a C program that accepts a string from the user and calculates the frequency of each character in the string.
## Algorithm:
Step 1: Start<br>
Step 2: Include the standard input-output library: #include<stdio.h>.<br>
Step 3: Declare a character array `s[100]` to store the input string, an integer array `visited[256]` initialized to `0`, and variables `i`, `n`, and `count`.<br>
Step 4: Read the string from the user using `scanf("%[^\n]", s);`<br>
Step 5: Calculate the length of the string using `strlen(s)` and store it in `n`.<br>
Step 6: For each character `s[i]` in the string (from `i = 0` to `n - 1`):<br>
  If `visited[(unsigned char)s[i]] == 0` (character not yet counted):  <br>
  Initialize `count = 0`.  <br>
  Loop through the string again and increment `count` for every occurrence of `s[i]`.  <br>
  Print `s[i]` and its count.  <br>
  Set `visited[(unsigned char)s[i]] = 1` to mark it as counted.<br>
Step 7: Repeat Step 6 for all characters.<br>
Step 8: Stop<br>
## Program:
```
#include <stdio.h>
#include <string.h>

int main() {
    char s[100];
    int visited[256] = {0}, i, j, n, count;

    printf("Enter a string: ");
    scanf("%[^\n]", s);

    n = strlen(s);

    for (i = 0; i < n; i++) {
        if (!visited[(unsigned char)s[i]]) {
            count = 0;
            for (j = 0; j < n; j++) {
                if (s[i] == s[j]) count++;
            }
            printf("'%c' occurs %d times\n", s[i], count);
            visited[(unsigned char)s[i]] = 1;
        }
    }

    return 0;
}
```
## Output:
<img width="237" height="141" alt="image" src="https://github.com/user-attachments/assets/4e5bc0a1-681f-45a1-8c0e-372afd2c39dc" />

## Result: 
Thus, the program was implemented and executed successfully, and the required output was obtained.


# Ex.No:15
  Formulate a C program to remove duplicate words from a given string and display the string with only unique words.
## Aim:
  To formulate a C program to remove duplicate words from a given string and display the string with only unique words.
## Algorithm:
Step 1: Start<br>
Step 2: Include the standard input-output library: #include<stdio.h>.<br>
Step 3: Declare a character array `str` to store the input string and a 2D array `words` to store individual words.<br>
Step 4: Read the input string using `scanf("%[^\n]s", str);`<br>
Step 5: Split the string into words:<br>
  Traverse the string character by character.  <br>
  When a space is encountered, terminate the current word with `'\0'` and move to the next row in `words`.  <br>
  Otherwise, copy the character into the current word.<br>
Step 6: Compare each word with all other words to detect duplicates:<br>
  If a duplicate is found, mark it by setting the first character to `'\0'`.<br>
Step 7: Print all words that are not marked as duplicates.<br>
Step 8: Stop<br>
# Program:
```
#include <stdio.h>
#include <string.h>
int main() {
    char str[200], words[50][50]; int n=0,i,j;
    printf("Enter a string: ");
    scanf("%[^\n]s", str);
    char *p=strtok(str," ");
    while(p){ strcpy(words[n++],p); p=strtok(NULL," "); }
    for(i=0;i<n;i++) for(j=i+1;j<n;j++) if(!strcmp(words[i],words[j])) words[j][0]='\0';
    for(i=0;i<n;i++) if(words[i][0]) printf("%s ",words[i]);
    return 0;
}
```
# Output:
<img width="464" height="55" alt="image" src="https://github.com/user-attachments/assets/eb2debc3-1b24-46a6-82e5-d9bcad0b0929" />

# Result: 
Thus, the program was implemented and executed successfully, and the required output was obtained.
