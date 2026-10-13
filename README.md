# day--9-c.

1. Write a C program to check whether a given number is a strong number or not.
Code:
#include <stdio.h>
int main()
{
    int n, temp, digit, fact, sum = 0;
    scanf("%d", &n);
    temp = n;
    while (temp > 0)
    {
        digit = temp % 10;
        fact = 1;
        for (int i = 1; i <= digit; i++)
        {
            fact = fact * i;
        }
        sum = sum + fact;
        temp = temp / 10;
    }
    if (sum == n)
        printf("Strong Number");
    else
        printf("Not a Strong Number");=
    return 0;
}

Output:
Input:
145

Output:
Strong Number

2. Write a C program to find the second-largest element in an array without sorting the array.
Code:
#include <stdio.h>

int main()
{
    int n, a[100], largest, second, found = 0;
    scanf("%d", &n);
    if (n < 2 || n > 100)
    {
        printf("Invalid array size");
        return 0;
    }
    for (int i = 0; i < n; i++)
    {
        scanf("%d", &a[i]);
    }
    largest = a[0];
    for (int i = 1; i < n; i++)
    {
        if (a[i] > largest)
            largest = a[i];
    }
    for (int i = 0; i < n; i++)
    {
        if (a[i] != largest)
        {
            if (found == 0 || a[i] > second)
            {
                second = a[i];
                found = 1;
            }
        }
    }
    if (found)
        printf("Second Largest = %d", second);
    else
        printf("Second largest not found");
    return 0;
}

Output:
Input:
5
10 30 20 50 40

Output:
Second Largest = 40

3. Write a C program to check whether a given number is a palindrome number and print the reverse of the number using loops.
Code:
#include <stdio.h>

int main()
{
    int n, temp, digit, rev = 0;
    scanf("%d", &n);
    temp = n;
    while (temp > 0)
    {
        digit = temp % 10;
        rev = rev * 10 + digit;
        temp = temp / 10;
    }
    printf("Reverse = %d\n", rev);
    if (n == rev)
        printf("Palindrome Number");
    else
        printf("Not a Palindrome Number");
    return 0;
}

Output:
Input:
121

Output:
Reverse = 121
Palindrome Number
