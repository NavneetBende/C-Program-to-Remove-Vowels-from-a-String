Program to remove vowels
In this article we will learn how to code a Program to remove vowels ‘A’, ‘E’, ‘I’, ‘O’, ‘U’ are five vowels out of 26 characters in English alphabet letters.C programming is case sensitive, and hence lowercase and uppercase characters are considered differently, so we will have to check for both the cases and then we can remove the vowels from a string

Program to remove vowels
Objective
Write a program that will take one string as input the program will then remove vowels a e i o u.

C Program to Remove Vowels from a String

Algorithm:
Initialize the variables.
Accept the input.
Initialize for loop.
Check and delete the vowels.
Store the string without vowels using another for loop.
Terminate both for loop.
Print the string without vowels.
Run
#include <stdio.h>
#include <stdlib.h>

int main() {
    // Initializing variable.
    char str[100];
    int i, j, len = 0;

    // Accepting input.
    printf("Enter a string : ");
    // gets(str);
    scanf("%s", str);

    len = strlen(str);
    // Accepting input.

    for (i = 0; i < len; i++) {
        // Checking vowels.
        if (str[i] == 'a' || str[i] == 'e' || str[i] == 'i' || str[i] == 'o' || str[i] == 'u' ||
            str[i] == 'A' || str[i] == 'E' || str[i] == 'I' || str[i] == 'O' || str[i] == 'U') {
            // Deleting vowels.
            for (j = i; j < len; j++) {
                // Storing string without vowels.
                str[j] = str[j + 1];
            }
            i--;
            len--;
        }
        str[len + 1] = '\0';
    }
   printf("After deleting the vowels, the string will be : %s", str);
   return 0;
}
Output
Enter a string : aaabbbeeeccc

After deleting the vowels, the string will be : bbbccc
Note
The time complexity of above code is O(n^2)
Method 2​ C programming code to remove vowels from a string
Objective: Write a program that will take one string as input. the program will then remove vowels a e i o u

Here we have used pointers to solve the same problem 

Run
#include <stdio.h>
#include <stdlib.h>
#include <string.h>
int find_vowel(char ch) 
{    
    if (ch == 'a' || ch == 'A' || ch == 'e' || ch == 'E' || 
        ch == 'i' || ch == 'I' || ch == 'o' ||
        ch == 'O' || ch == 'u' || ch == 'U')
        return 1;  // It is a vowel
    else
        return 0;  // It is not a vowel
}
int main() {
    char *string, *temp, *strptr, ch, *start;
    int size = 100;

    printf("Enter a string");
    string = (char *)malloc(size);
    getline(&string, &size, stdin);
    temp = string;
    strptr = (char *)malloc(100);
    start = strptr;

    while (*temp) {
        ch = *temp;
        if (!find_vowel(ch)) {
            *strptr = ch;
            strptr++;
        }
        temp++;
    }

    *strptr = '\0';
    strptr = start;

    strcpy(string, strptr);
    free(strptr);

    printf("String after removing vowels: %s", string);
    return 0;

}
Output
Enter a string
Root
String after removing vowels: Rt
