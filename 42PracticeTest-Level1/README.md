# 1. Level 1-1

```
Assignment name  : first_word
Expected files   : first_word.c
Allowed functions: write
--------------------------------------------------------------------------------

Write a program that takes a string and displays its first word, followed by a
newline.

A word is a section of string delimited by spaces/tabs or by the start/end of
the string.

If the number of parameters is not 1, or if there are no words, simply display
a newline.

Examples:

$> ./first_word "FOR PONY" | cat -e
FOR$
$> ./first_word "this        ...       is sparta, then again, maybe    not" | cat -e
this$
$> ./first_word "   " | cat -e
$
$> ./first_word "a" "b" | cat -e
$
$> ./first_word "  lorem,ipsum  " | cat -e
lorem,ipsum$
$>
```

## 1.1. first_word.c

```c
#include <unistd.h>

int main(int argc, char *argv[])
{
    int c;
    
    c = 0;
    if (argc == 2)
    {
        while (argv[1][c] == '\t' || argv[1][c] == ' ')
            c++;
        while (argv[1][c] != '\0' && argv[1][c] != '\t' && argv[1][c] != ' ')
        {
            write(1, &(argv[1][c]), 1);
            c++;
        }
    }
    write(1, "\n", 1);
    return (0);
}
```


# 2. Level 1-2

```
Assignment name  : fizzbuzz
Expected files   : fizzbuzz.c
Allowed functions: write
--------------------------------------------------------------------------------

Write a program that prints the numbers from 1 to 100, each separated by a
newline.

If the number is a multiple of 3, it prints 'fizz' instead.

If the number is a multiple of 5, it prints 'buzz' instead.

If the number is both a multiple of 3 and a multiple of 5, it prints 'fizzbuzz' instead.

Example:

$>./fizzbuzz
1
2
fizz
4
buzz
fizz
7
8
fizz
buzz
11
fizz
13
14
fizzbuzz
[...]
97
98
fizz
buzz
$>
```

## 2.1. fizzbuzz.c

```c
#include <unistd.h>

void ft_write_to_num(int num)
{
    if (num > 9 )
        ft_write_to_num (num / 10);
    write(1, &("0123456789"[num % 10]), 1);
}

int main()
{
    int c;
    
    c = 1;
    while (c <= 100)
    {
        if ((c % 5 == 0) && (c % 3 == 0))
            write(1, "fizzbuzz", 8);
        else if (c % 3 == 0)
            write(1, "fizz", 4);
        else if (c % 5 == 0)
            write(1, "buzz", 4);
        else
            ft_write_to_num(c);
        write(1, "\n", 1);
        c++;
    }
    return (0);
}
```


# 3. Level 1-3

```
Assignment name  : ft_putstr
Expected files   : ft_putstr.c
Allowed functions: write
--------------------------------------------------------------------------------

Write a function that displays a string on the standard output.

The pointer passed to the function contains the address of the string's first
character.

Your function must be declared as follows:

void	ft_putstr(char *str);
```

## 3.1. ft_putstr.c

```c
#include <unistd.h>

void ft_putstr(char *str)
{
    while (*str != '\0')
    {
        write(1, str, 1);
        str++;
    }
}
```

## 3.2. main.c

```c
int main()
{
    char str[] = "testtest";
    char *pstr = str;
    
    ft_putstr(pstr);
    return (0);
}
```

# 4. Level 1-4

```
Assignment name  : ft_strcpy
Expected files   : ft_strcpy.c
Allowed functions: 
--------------------------------------------------------------------------------

Reproduce the behavior of the function strcpy (man strcpy).

Your function must be declared as follows:

char    *ft_strcpy(char *s1, char *s2);
```

## 4.1. ft_strcpy.c

```c
char *ft_strcpy(char *dest, char *src)
{
    int c;
    
    c = 0;
    while(src[c] != '\0')
    {
        dest[c] = src[c];
        c++;
    }
    dest[c] = '\0';
    return (dest);
}
```

## 4.2. main.c

```c
#include <stdio.h>

int main()
{
    char test1[] = "test123";
    char test2[] = "test123456";
    //char *ptest = ft_strcpy(test1, test2);
    
    printf("%s", ft_strcpy(test1,test2));
    return 0;
}
```

# 5. Level 1-5

```
Assignment name  : ft_strlen
Expected files   : ft_strlen.c
Allowed functions: 
--------------------------------------------------------------------------------

Write a function that returns the length of a string.

Your function must be declared as follows:

int	ft_strlen(char *str);
```

## 5.1. ft_strlen.c

```c
int	ft_strlen(char *str)
{
    int c;
    
    c = 0;
    while(str[c])
        c++;
    return (c);
}
```

## 5.2 main.c

```c
int main(void)
{
    char monster[] = "42 KL";
    printf("%s has %d characters", monster, ft_strlen(monster));
    return (0);
}
```

# 6. Level 1 - 6

```
Assignment name  : ft_swap
Expected files   : ft_swap.c
Allowed functions: 
--------------------------------------------------------------------------------

Write a function that swaps the contents of two integers the adresses of which
are passed as parameters.

Your function must be declared as follows:

void	ft_swap(int *a, int *b);
```

## 6.1. ft_swap.c

```c
void	ft_swap(int *a, int *b)
{
    int temp;
    temp = *b;
    *b = *a;
    *a = temp;
}
```

## 6.2 main.c

```c
#include <stdio.h>

int main(void)
{
	int old_age = 223;
	int young_age = 1;
	printf("old_age: %d\nyoung_age: %d\n", old_age, young_age);
	ft_swap(&old_age, &young_age);
	printf("swap them ages!\n");
	printf("old_age: %d\nyoung_age: %d\n", old_age, young_age);
	return (0);
}
```

# 7. Level 1 - 7

```
Assignment name  : repeat_alpha
Expected files   : repeat_alpha.c
Allowed functions: write
--------------------------------------------------------------------------------

Write a program called repeat_alpha that takes a string and display it
repeating each alphabetical character as many times as its alphabetical index,
followed by a newline.

'a' becomes 'a', 'b' becomes 'bb', 'e' becomes 'eeeee', etc...

Case remains unchanged.

If the number of arguments is not 1, just display a newline.

Examples:

$>./repeat_alpha "abc"
abbccc
$>./repeat_alpha "Alex." | cat -e
Alllllllllllleeeeexxxxxxxxxxxxxxxxxxxxxxxx.$
$>./repeat_alpha 'abacadaba 42!' | cat -e
abbacccaddddabba 42!$
$>./repeat_alpha | cat -e
$
$>
$>./repeat_alpha "" | cat -e
$
$>
```

## 7.1. repeat_alpha.c

```c
#include <unistd.h>

int repeat_alpha(char c)
{
    int duplicate;
    
    duplicate = 0;
    if (c >= 'a' && c <= 'z')
        duplicate = c - 'a' + 1;
    else if (c >= 'A' && c <= 'Z')
        duplicate = c - 'A' + 1;
    else
        duplicate = 1;
    return (duplicate);
}

int main(int argc, char*argv[])
{
    int duplicate;
    
    duplicate = 0;
    if (argc == 2)
    {
        while (*argv[1])
        {
            duplicate = repeat_alpha(*argv[1]);
            while (duplicate--)
                write(1, argv[1], 1);
            argv[1]++;
        }
        write(1, "\n", 1);
    }
    return 0;
}
```

# 8. Level 1 - 8

```
Assignment name  : rev_print
Expected files   : rev_print.c
Allowed functions: write
--------------------------------------------------------------------------------

Write a program that takes a string, and displays the string in reverse
followed by a newline.

If the number of parameters is not 1, the program displays a newline.

Examples:

$> ./rev_print "zaz" | cat -e
zaz$
$> ./rev_print "dub0 a POIL" | cat -e
LIOP a 0bud$
$> ./rev_print | cat -e
$
```

## 8.1.  rev_print.c

```c
#include <unistd.h>

int main(int argc, char*argv[])
{
    int c;
    if (argc == 2)
    {
        c = 0;
        while (argv[1][c])
            c++;
        while(c)
            write(1, &(argv[1][--c]), 1);
    }
    write(1, "\n", 1);

    return 0;
}
```

# 9. Level 1 - 9

```
Assignment name  : rot_13
Expected files   : rot_13.c
Allowed functions: write
--------------------------------------------------------------------------------

Write a program that takes a string and displays it, replacing each of its
letters by the letter 13 spaces ahead in alphabetical order.

'z' becomes 'm' and 'Z' becomes 'M'. Case remains unaffected.

The output will be followed by a newline.

If the number of arguments is not 1, the program displays a newline.

Example:

$>./rot_13 "abc"
nop
$>./rot_13 "My horse is Amazing." | cat -e
Zl ubefr vf Nznmvat.$
$>./rot_13 "AkjhZ zLKIJz , 23y " | cat -e
NxwuM mYXVWm , 23l $
$>./rot_13 | cat -e
$
$>
$>./rot_13 "" | cat -e
$
$>
```

## 9.1. rot_13.c

```c
#include <unistd.h>

int main(int argc, char*argv[])
{
    int c;
    if (argc > 1)
    {
        c = 0;
        while (argv[1][c])
        {
            if (argv[1][c] >= 'a' && argv[1][c] <= 'm')
                argv[1][c] += 13;
            else if (argv[1][c] >= 'A' && argv[1][c] <= 'M')
                argv[1][c] += 13;
            else if (argv[1][c] >= 'm' && argv[1][c] <= 'z')
                argv[1][c] -= 13;
            else if (argv[1][c] >= 'M' && argv[1][c] <= 'Z')
                argv[1][c] -= 13;
            write(1, &(argv[1][c]), 1);
            c++;
        }
    }
    write(1, "\n", 1);

    return 0;
}
```

# Level 1 - 10

```
Assignment name  : rotone
Expected files   : rotone.c
Allowed functions: write
--------------------------------------------------------------------------------

Write a program that takes a string and displays it, replacing each of its
letters by the next one in alphabetical order.

'z' becomes 'a' and 'Z' becomes 'A'. Case remains unaffected.

The output will be followed by a \n.

If the number of arguments is not 1, the program displays \n.

Example:

$>./rotone "abc"
bcd
$>./rotone "Les stagiaires du staff ne sentent pas toujours tres bon." | cat -e
Mft tubhjbjsft ev tubgg of tfoufou qbt upvkpvst usft cpo.$
$>./rotone "AkjhZ zLKIJz , 23y " | cat -e
BlkiA aMLJKa , 23z $
$>./rotone | cat -e
$
$>
$>./rotone "" | cat -e
$
$>
```

## 10.1. rotone.c

```c
#include <unistd.h>

void ft_putchar (char c)
{
    write(1, &c, 1);
}

int main(int argc, char*argv[])
{
    int c;
    if (argc > 1)
    {
        c = 0;
        while (argv[1][c])
        {
            if (argv[1][c] == 'z')
               ft_putchar('a');
            else if (argv[1][c] == 'Z')
                ft_putchar('A');
            else if (argv[1][c] >= 'a' && argv[1][c] <= 'y')
                ft_putchar(argv[1][c] + 1);
            else if (argv[1][c] >= 'A' && argv[1][c] <= 'Y')
                ft_putchar(argv[1][c] + 1);
            else
                ft_putchar(argv[1][c]);
            c++;
        }
    }
    write(1, "\n", 1);
    return 0;
}
```

# Level 1 - 11

```
Assignment name  : search_and_replace
Expected files   : search_and_replace.c
Allowed functions: write, exit
--------------------------------------------------------------------------------

Write a program called search_and_replace that takes 3 arguments, the first 
arguments is a string in which to replace a letter (2nd argument) by
another one (3rd argument).

If the number of arguments is not 3, just display a newline.

If the second argument is not contained in the first one (the string)
then the program simply rewrites the string followed by a newline.

Examples:
$>./search_and_replace "Papache est un sabre" "a" "o"
Popoche est un sobre
$>./search_and_replace "zaz" "art" "zul" | cat -e
$
$>./search_and_replace "zaz" "r" "u" | cat -e
zaz$
$>./search_and_replace "jacob" "a" "b" "c" "e" | cat -e
$
$>./search_and_replace "ZoZ eT Dovid oiME le METol." "o" "a" | cat -e
ZaZ eT David aiME le METal.$
$>./search_and_replace "wNcOre Un ExEmPle Pas Facilw a Ecrirw " "w" "e" | cat -e
eNcOre Un ExEmPle Pas Facile a Ecrire $
```

## 11.1. search_and_replace.c

```c
#include <unistd.h>

void ft_putchar (char c)
{
    write(1, &c, 1);
}

int main(int argc, char*argv[])
{
    int c;
    if (argc == 4)
    {
        c = 0;
        if (!argv[2][1] && !argv[3][1])
        {
          while (argv[1][c])
          {
                if (argv[1][c] == argv[2][0])
                    ft_putchar(argv[3][0]);
                else
                    ft_putchar(argv[1][c]);
            c++;
          }
        }
    }
    write(1, "\n", 1);
    return 0;
}
```

## Level 1 - 12

```
Assignment name  : ulstr
Expected files   : ulstr.c
Allowed functions: write
--------------------------------------------------------------------------------

Write a program that takes a string and reverses the case of all its letters.
Other characters remain unchanged.

You must display the result followed by a '\n'.

If the number of arguments is not 1, the program displays '\n'.

Examples :

$>./ulstr "L'eSPrit nE peUt plUs pRogResSer s'Il staGne et sI peRsIsTent VAnIte et auto-justification." | cat -e
l'EspRIT Ne PEuT PLuS PrOGrESsER S'iL STAgNE ET Si PErSiStENT vaNiTE ET AUTO-JUSTIFICATION.$
$>./ulstr "S'enTOuRer dE sECreT eSt uN sIGnE De mAnQuE De coNNaiSSanCe.  " | cat -e
s'ENtoUrER De SecREt EsT Un SigNe dE MaNqUe dE COnnAIssANcE.  $
$>./ulstr "3:21 Ba  tOut  moUn ki Ka di KE m'en Ka fe fot" | cat -e
3:21 bA  ToUT  MOuN KI kA DI ke M'EN kA FE FOT$
$>./ulstr | cat -e
$
```

## 12.1 . ulstr.c

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
                    ft_putchar(argv[1][c] - 32);
                else if (argv[1][c] >= 'A' && argv[1][c] <= 'Z')
                    ft_putchar(argv[1][c] + 32);
                else
                    ft_putchar(argv[1][c]);
            c++;
        }
    }
    write(1, "\n", 1);
    return 0;
}
```