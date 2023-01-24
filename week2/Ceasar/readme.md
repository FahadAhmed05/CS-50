# Ceasar
Understood some new things in this problem

## command line arguments
1. (argv) The first parameter, argc (argument count) is an integer that indicates how many arguments were entered on the command line when the program was started. 
2. The second parameter, argv (argument vector), is an array of pointers to arrays of character objects.

## cs50 manual page
Some of these new header file are used on this manual page
1. #include <stdlib.h> (In this header file we use `atoi`)
### Atoi
atoi is a function in the C programming language that converts a string into an integer numerical representation. 
2. #include <string.h> (In this header file we use `strlen`)
### Strlen
The strlen() function calculates the length of a given string. 
3. #include <ctype.h> (In this header file we use `isalpha`, `isupper`, `islower`)
### isalpha
isalpha(c) is a function in C which can be used to check if the passed character is an alphabet or not. 
### isupper
isupper() function in C programming checks whether the given character is upper case or not. 
### islower
islower() function in C programming checks whether the given character is lower case or not. 


```sh
#include <cs50.h>
#include <stdio.h>
#include <stdlib.h>
#include <string.h>
#include <ctype.h>

int main(int argc, string argv[])
{
    if (argc != 2)
    {
        printf("Usage: ./caesar key\n");
        return 1;
    }
    // check is second arg is digit or not
    for (int i = 0; i < strlen(argv[1]); i++)
    {
        if (!isdigit(argv[1][i]))
        {
            printf("Usage: ./caesar key\n");
            return 1;
        }
    }
    if (argc == 2)
    {
        // covert string into int
        int i = atoi(argv[1]);
        // user Input
        string input = get_string("plaintext: ");
        printf("ciphertext: ");
        for (int j = 0, n = strlen(input); j < n; j++)
        {
            // check is alphabet
            if (isalpha(input[j]))
            {
                // check is uppercase
                if (isupper(input[j]))
                {
                    // check uppercase and then the value given ascii we have -65 for the uppercase
                    // alpha value. and minus input value with -65
                    int x = (int)input[j] - 65;
                    // To find the value of c, we have to do (x + i) % 26 which is taken from given formula
                    int c = (x + i) % 26;
                    // and then plus 65 in the c value to get original value
                    int y = (65 + c);
                    printf("%c", y);
                }
                else
                {
                    // check is lowercase
                    if (islower(input[j]))
                    {
                        // here we use - 97 to the lower case alpha
                        int x = (int)input[j] - 97;
                        int c = (x + i) % 26;
                        int y = (97 + c);
                        printf("%c", y);
                    }
                }
            }
            else
            {
                printf("%c", input[j]);
            }
        }
        printf("\n");
    }
    else
    {
        printf("Error\n");
        return 1;
    }
}
```
