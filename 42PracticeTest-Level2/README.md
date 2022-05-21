# 1. Level 2 - 1

```
Assignment name  : alpha_mirror
Expected files   : alpha_mirror.c
Allowed functions: write
--------------------------------------------------------------------------------

Write a program called alpha_mirror that takes a string and displays this string
after replacing each alphabetical character by the opposite alphabetical
character, followed by a newline.

'a' becomes 'z', 'Z' becomes 'A'
'd' becomes 'w', 'M' becomes 'N'

and so on.

Case is not changed.

If the number of arguments is not 1, display only a newline.

Examples:

$>./alpha_mirror "abc"
zyx
$>./alpha_mirror "My horse is Amazing." | cat -e
Nb slihv rh Znzarmt.$
$>./alpha_mirror | cat -e
$
$>
```

## 1.1. alpha_mirror.c

```c
#include <unistd.h>

void ft_putchar (char c)
{
    write(1, &c, 1);
}

int main(int argc, char*argv[])
{
    int c;
    if (argc == 2)
    {
        c = 0;
        while (argv[1][c])
         {
                if (argv[1][c] >= 'a' && argv[1][c] <= 'z')
                    ft_putchar('z' - argv[1][c] + 'a');
                else if (argv[1][c] >= 'A' && argv[1][c] <= 'Z')
                    ft_putchar('Z' - argv[1][c] + 'A');
                else
                    ft_putchar(argv[1][c]);
            c++;
        }
    }
    write(1, "\n", 1);
    return 0;
}
```


# Level 2 - 2

```
Assignment name  : do_op
Expected files   : *.c, *.h
Allowed functions: atoi, printf, write
--------------------------------------------------------------------------------

Write a program that takes three strings:
- The first and the third one are representations of base-10 signed integers
  that fit in an int.
- The second one is an arithmetic operator chosen from: + - * / %

The program must display the result of the requested arithmetic operation,
followed by a newline. If the number of parameters is not 3, the program
just displays a newline.

You can assume the string have no mistakes or extraneous characters. Negative
numbers, in input or output, will have one and only one leading '-'. The
result of the operation fits in an int.

Examples:

$> ./do_op "123" "*" 456 | cat -e
56088$
$> ./do_op "9828" "/" 234 | cat -e
42$
$> ./do_op "1" "+" "-43" | cat -e
-42$
$> ./do_op | cat -e
$```
```

## 2.1. header.h

```c
#ifndef HEADER_H
# define HEADER_H
#include <stdlib.h>
#include <stdio.h>
#endif
```

## 2.2. main.c 

```c
#include "header.h"

int main(int argc, char*argv[])
{   
    int c;
    if (argc == 4)
    {
        c = 0;
        while (argv[1][c] && argv[3][c])
         {
                if (argv[2][c] == '+')
                    printf("%d", atoi(argv[1]) + atoi(argv[3]));
                else if (argv[2][c] == '-')
                   printf("%d", atoi(argv[1]) - atoi(argv[3]));
                else if (argv[2][c] == '*')
                   printf("%d", atoi(argv[1]) * atoi(argv[3]));
               else if (argv[2][c] == '/')
                   printf("%d", atoi(argv[1]) / atoi(argv[3]));
                else if (argv[2][c] == '*')
                   printf("%d", atoi(argv[1]) % atoi(argv[3]));
            c++;
        }
    }
    printf("\n");
    return 0;
}
```

# 3. Level 2 - 3

```
Assignment name  : ft_atoi
Expected files   : ft_atoi.c
Allowed functions: None
--------------------------------------------------------------------------------

Write a function that converts the string argument str to an integer (type int)
and returns it.

It works much like the standard atoi(const char *str) function, see the man.

Your function must be declared as follows:

int	ft_atoi(const char *str);
```

## 3.1. ft_atoi.c

```c
int	ft_atoi(const char *str)
{
    int num;
    int sign;
    
    num = 0;
    sign = 1;
    
    while (*str == ' ' || (*str >= '\t' && *str <= '\r'))
		str++;
    if (*str == '-')
        sign = -1;
    while (*str != '\0')
    {
        if (*str >= '0' && *str <= '9')
            num = (*str - '0') + (num * 10);
        str++;
    }
    return (num * sign);
}
```

## 3.2. main.c

```c
#include <stdio.h>

int main(int argc, char*argv[])
{   
    char num[] = "-1 2   3";
    printf("%d", ft_atoi(num));
    return 0;
}
```

# 4. Level 2 - 4

```
Assignment name  : ft_strcmp
Expected files   : ft_strcmp.c
Allowed functions: 
--------------------------------------------------------------------------------

Reproduce the behavior of the function strcmp (man strcmp).

Your function must be declared as follows:

int    ft_strcmp(char *s1, char *s2);
```

## 4.1. ft_strcmp.c

```c
int    ft_strcmp(char *s1, char *s2)
{
    while (*s1 != '\0' && *s2 != '\0' && *s1 == *s2)
    {
        s1++;
        s2++;
    }
    return (*s1 - *s2);
}
```

## 4.2. main.c

```c
#include <stdio.h>

int main(int argc, char*argv[])
{   
    char a1[] = "";
    char a2[] = "321";
    printf("%d", ft_strcmp(a1, a2));
    return 0;
}
```

# 5. Level 2 - 5

```
Assignment name  : inter
Expected files   : inter.c
Allowed functions: write
--------------------------------------------------------------------------------

Write a program that takes two strings and displays, without doubles, the
characters that appear in both strings, in the order they appear in the first
one.

The display will be followed by a \n.

If the number of arguments is not 2, the program displays \n.

Examples:

$>./inter "padinton" "paqefwtdjetyiytjneytjoeyjnejeyj" | cat -e
padinto$
$>./inter ddf6vewg64f gtwthgdwthdwfteewhrtag6h4ffdhsd | cat -e
df6ewg4$
$>./inter "rien" "cette phrase ne cache rien" | cat -e
rien$
$>./inter | cat -e
$
```

## inter.c

```c
#include <unistd.h>

int scan(char *or, char s, int num)
{
    while (num >= 0)
    {
        if (or[num] == s)
            return (0);
        num--;
    }
    return (1);
}

int main(int argc, char *argv[])
{
    int c1;
    int c2;
    
    c1 = 0;
    if (argc == 3)
    {
        while (argv[1][c1])
        {
            c2 = 0;
            while(argv[2][c2])
            {
                if (argv[1][c1] == argv[2][c2])
                {
                    if (scan(argv[1], argv[1][c1], c1 - 1))
                        write(1, &(argv[1][c1]), 1);
                    break;
                }
                c2++;
            }
            c1++;
        }
    }
    write(1, "\n", 1);
    return 0;
}
```

# 6. Level 2 - 6

```
Assignment name	: ft_strcspn
Expected files	: ft_strcspn.c
Allowed functions: None
---------------------------------------------------------------

Reproduce exactly the behavior of the function strcspn
(man strcspn).

The function should be prototyped as follows:

size_t	ft_strcspn(const char *s, const char *reject);
```

## 6.1. ft_strcspn.c

```c
**size_t	ft_strcspn(const char *s, const char *reject)
{
    size_t i;
    size_t j;
    i = 0;
    while (s[i] != '\0')
    {
        j = 0;
        while (reject[j] != '\0')
        {
            if (s[i] == reject[j])
                return (i);
            j++;
        }
        i++;
    }
    return (i);
}
```

## 6.2. main.c

```c
#include <stdio.h>
#include <string.h>

int main(void)
{
    char s[] = "geeksforgeeks";
    char reject[] = "dhkfc";
    printf("%ld\n", ft_strcspn(s,reject));
    printf("%ld\n", strcspn(s,reject));
    return 0;
}
```

# 7. Level 2 - 7

```
Assignment name  : ft_strdup
Expected files   : ft_strdup.c
Allowed functions: malloc
--------------------------------------------------------------------------------

Reproduce the behavior of the function strdup (man strdup).

Your function must be declared as follows:

char    *ft_strdup(char *src);
```

## 7.1. ft_strdup.c

```c
#include <stdlib.h>

int ft_strlen(char *src)
{
    int c;
    c = 0;
    while (src[c])
        c++;
    return (c);
}

char    *ft_strcpy(char *src, char *dest)
{
    int c;
    c = 0;
    dest = malloc(sizeof(src) * ft_strlen(src) + 1);
    
    while (src[c])
    {
        dest[c] = src[c];
        c++;
    }
    dest[c] = '\0';
    return (dest);
}

char    *ft_strdup(char *src)
{
    char *dest;
    
    if (src)
        dest = ft_strcpy(src, dest);
    return (dest);
}
```

## 7.2. main.c

```c
#include <stdio.h>

int main()
{
    char *p_test;
    p_test = "12321adca ad";
    printf("%s\n", p_test);

    return 0;
}
```

# 8. Level 2 - 8

```
Assignment name  : ft_strrev
Expected files   : ft_strrev.c
Allowed functions: 
--------------------------------------------------------------------------------

Write a function that reverses (in-place) a string.

It must return its parameter.

Your function must be declared as follows:

char    *ft_strrev(char *str);
```

## 8.1. ft_strrev.c

```c
int ft_strlen(char *src)
{
    int c;
    c = 0;
    while (src[c])
        c++;
    return (c);
}

char    *ft_strrev(char *str)
{
    char temp;
    int c;
    int len;
    
    c = 0;
    if (str)
    {
        len = ft_strlen(str);
        while(c < (len - 1))
        {
            temp = str[len - 1];
            str[len - 1] = str[c];
            str[c] = temp;
            c++;
            len--;
        }
    }
    return (str);
}
```

## 8.2. main.c

```c
int main()
{
    char p_test [] = "12321adca ad";
    printf("%s\n", ft_strrev(p_test));
    return 0;
}
```

# 9.0 Level 2 - 9

```
Assignment name  : is_power_of_2
Expected files   : is_power_of_2.c
Allowed functions: None
--------------------------------------------------------------------------------

Write a function that determines if a given number is a power of 2.

This function returns 1 if the given number is a power of 2, otherwise it returns 0.

Your function must be declared as follows:

int	    is_power_of_2(unsigned int n);
```

## 9.1. is_power_of_2.c

```c
int	    is_power_of_2(unsigned int n)
{
    if (n == 0)
        return (0);
    while (n % 2 == 0)
        n /= 2;
    return (n == 1) ? 1 : 0;
}
```

## 9.2. main.c

```c
int main(void)
{
    printf("%d\n", is_power_of_2(2));
    printf("%d\n", is_power_of_2(0));
    printf("%d\n", is_power_of_2(-2));
    printf("%d\n", is_power_of_2(3));
    return 0;
}
```

# 10. Level 2 - 10

```
Assignment name  : last_word
Expected files   : last_word.c
Allowed functions: write
--------------------------------------------------------------------------------

Write a program that takes a string and displays its last word followed by a \n.

A word is a section of string delimited by spaces/tabs or by the start/end of
the string.

If the number of parameters is not 1, or there are no words, display a newline.

Example:

$> ./last_word "FOR PONY" | cat -e
PONY$
$> ./last_word "this        ...       is sparta, then again, maybe    not" | cat -e
not$
$> ./last_word "   " | cat -e
$
$> ./last_word "a" "b" | cat -e
$
$> ./last_word "  lorem,ipsum  " | cat -e
lorem,ipsum$
$>
```

## 10.1. last_word.c

```c
#include <unistd.h>

int main(int argc, char*argv[])
{
    int i;
    int j;
    
    i = 0;
    j = 0;
    if (argc == 2)
    {
        while (argv[1][i])
        {
            if (argv[1][i] == ' ' && argv[1][i + 1] >= 33  && argv[1][i + 1] <= 127)
                j = i + 1;
            i++;
        }
        while (argv[1][j] >= 33 && argv[1][j] <= 127)
        {
            write(1, &(argv[1][j]), 1);
            j++;
        }
    }
    write(1, "\n", 1);
    return 0;
}
```

## 11. Level 2 - 11

```
Assignment name  : max
Expected files   : max.c
Allowed functions: 
--------------------------------------------------------------------------------

Write the following function:

int		max(int* tab, unsigned int len);

The first parameter is an array of int, the second is the number of elements in
the array.

The function returns the largest number found in the array.

If the array is empty, the function returns 0.
```

## 11.1. max.c

```c
int		max(int* tab, unsigned int len)
{
    int max; 
    max = len - 1;
    while (len--)
    {
        if (tab[len] > max)
            max = tab[len];
    }
    return (max);
}
```

## 11.2. main.c

```c
int main(void)
{
    int num[] = {1,2,3,4,5};
    int num2[] = {1,2,3,4,5,-1,8,10,-1};
    printf("%d\n", max(num,5));
    printf("%d\n", max(num2,9));
    return (0);
}
```

# 12 Level 2 - 12

```
Assignment name  : print_bits
Expected files   : print_bits.c
Allowed functions: write
--------------------------------------------------------------------------------

Write a function that takes a byte, and prints it in binary WITHOUT A NEWLINE
AT THE END.

Your function must be declared as follows:

void	print_bits(unsigned char octet);

Example, if you pass 2 to print_bits, it will print "00000010"
```

## 12.1. print_bits.c

```c
void	print_bits(unsigned char octet)
{
    int byte;
    int num;
    byte = 128;
    num = octet;
    
    while (byte != 0)
    {
        if (byte <= num)
        {
            write(1, "1", 1);
            num %= byte;
        }
        else
            write(1, "0", 1);
        byte /= 2;
    }
}
```

## 12.2. main.c

```c
int main(void)
{
    print_bits(5);
    return 0;
}
```

# 13. Level 2 - 13

```
Assignment name  : reverse_bits
Expected files   : reverse_bits.c
Allowed functions:
--------------------------------------------------------------------------------

Write a function that takes a byte, reverses it, bit by bit (like the
example) and returns the result.

Your function must be declared as follows:

unsigned char	reverse_bits(unsigned char octet);

Example:

  1 byte
_____________
 0010  0110
	 ||
	 \/
 0110  0100
```

## 13.1. reverse_bits.c

```c
unsigned char	reverse_bits(unsigned char octet)
{
    unsigned char rev;
    int i;
    rev = 0;
    i = 8;
    
    while (i > 0)
    {
        rev = (rev * 2) + (octet % 2);
        octet /= 2;
        i--;
    }
    return (rev);
}
```

## 13.2. main.c

```c
int     main(void)
{
	printf("%d\n", reverse_bits(38));
	return (0);
}
```

# Level 2 - 14 

```
Assignment name  : swap_bits
Expected files   : swap_bits.c
Allowed functions:
--------------------------------------------------------------------------------

Write a function that takes a byte, swaps its halves (like the example) and
returns the result.

Your function must be declared as follows:

unsigned char	swap_bits(unsigned char octet);

Example:

  1 byte
_____________
 0100 | 0001
     \ /
     / \
 0001 | 0100
```

## 14.1. swap_bits.c

```c
unsigned char	swap_bits(unsigned char octet)
{
    return ((octet >> 4) | (octet << 4));
}
```

## 14.2. main.c

```c
int     main(void)
{
	printf("%d\n", swap_bits(2));
	return (0);
}
```

# 15. Level 2 - 15 

```
Assignment name  : union
Expected files   : union.c
Allowed functions: write
--------------------------------------------------------------------------------

Write a program that takes two strings and displays, without doubles, the
characters that appear in either one of the strings.

The display will be in the order characters appear in the command line, and
will be followed by a \n.

If the number of arguments is not 2, the program displays \n.

Example:

$>./union zpadinton "paqefwtdjetyiytjneytjoeyjnejeyj" | cat -e
zpadintoqefwjy$
$>./union ddf6vewg64f gtwthgdwthdwfteewhrtag6h4ffdhsd | cat -e
df6vewg4thras$
$>./union "rien" "cette phrase ne cache rien" | cat -e
rienct phas$
$>./union | cat -e
$
$>
$>./union "rien" | cat -e
$
$>
```

## 15.1. union.c

```c
#include <unistd.h>

int scan (char *s, char c, int pos)
{
    int i;
    i = 0;
    while (pos > i)
    {
        if (s[i] == c)
            return (0);
        i++;
    }
    return (1);
}

void ft_union (char *av1, char *av2)
{
    int i;
    int j;
    
    i = 0;
    while (av1[i])
    {
        if(scan(av1, av1[i], i))
            write(1, &(av1[i]), 1);
        i++;
    }
    j = 0;
    while (av2[j])
    {
        if(scan(av1, av2[j], i) && scan(av2, av2[j], j))
            write(1, &(av2[j]), 1);
        j++;
    }
}

int main (int argc, char*argv[])
{
    if (argc == 3)
        ft_union(argv[1], argv[2]);
    write(1, "\n", 1);
    return 0;
}
```

# 16. Level 2 - 16

```
Assignment name  : wdmatch
Expected files   : wdmatch.c
Allowed functions: write
--------------------------------------------------------------------------------

Write a program that takes two strings and checks whether it's possible to
write the first string with characters from the second string, while respecting
the order in which these characters appear in the second string.

If it's possible, the program displays the string, followed by a \n, otherwise
it simply displays a \n.

If the number of arguments is not 2, the program displays a \n.

Examples:

$>./wdmatch "faya" "fgvvfdxcacpolhyghbreda" | cat -e
faya$
$>./wdmatch "faya" "fgvvfdxcacpolhyghbred" | cat -e
$
$>./wdmatch "quarante deux" "qfqfsudf arzgsayns tsregfdgs sjytdekuoixq " | cat -e
quarante deux$
$>./wdmatch "error" rrerrrfiiljdfxjyuifrrvcoojh | cat -e
$
$>./wdmatch | cat -e
$
```

## 16.1. wdmatch.c

```c
#include <unistd.h>

int ft_len(char *av1)
{
    int c;
    c = 0;
    while (av1[c])
        c++;
    return (c);
}

void wdmatch(char *av1, char *av2)
{
    int i;
    int j;
    int len;
    
    i = 0;
    j = 0;
    len = ft_len(av1);
    while (av2[j])
    {
        if (av2[j++] == av1[i])
            i += 1;
    }
    if (len == i)
        write(1, av1, len);
}

int main(int argc, char*argv[])
{
    if (argc == 3)
        wdmatch(argv[1],argv[2]);
    write(1, "\n", 1);
    return 0;
}
```