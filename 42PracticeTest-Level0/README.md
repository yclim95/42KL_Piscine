# 1. Level 0-1

```
Assignment name  : aff_a
Expected files   : aff_a.c
Allowed functions: write
--------------------------------------------------------------------------------

Write a program that takes a string, and displays the first 'a' character it
encounters in it, followed by a newline. If there are no 'a' characters in the
string, the program just writes a newline. If the number of parameters is not
1, the program displays 'a' followed by a newline.

Example:

$> ./aff_a "abc" | cat -e
a$
$> ./aff_a "dubO a POIL" | cat -e
a$
$> ./aff_a "zz sent le poney" | cat -e
$
$> ./aff_a | cat -e
a$
```

## 1.1. aff_a.c

```c
#include <unistd.h>

int main(int argc, char*argv[])
{
    int c;
    
    c = 0;
    if (argc == 2)
    {
        while(argv[1][c] != '\0')
        {
            if (argv[1][c] == 'a')
            {
                write(1,"a\n",2);
                break;
            }
            else
            {
                write(1,"\n",1);
                break;
            }
            c++;
        }
    }
    else
        write(1,"a\n",2);
    return (0);
}
```

# 2. Level 0-2  

```
Assignment name  : aff_first_param
Expected files   : aff_first_param.c
Allowed functions: write
--------------------------------------------------------------------------------

Write a program that takes strings as arguments, and displays its first
argument followed by a \n.

If the number of arguments is less than 1, the program displays \n.

Example:

$> ./aff_first_param vincent mit "l'ane" dans un pre et "s'en" vint | cat -e
vincent$
$> ./aff_first_param "j'aime le fromage de chevre" | cat -e
j'aime le fromage de chevre$
$> ./aff_first_param
$
```

## 2.1. aff_first_param.c

```c
#include <unistd.h>

int main(int argc, char*argv[])
{
    int c;
    
    c = -1;
    if (argc > 1)
    {
        while(argv[1][++c])
            write(1,&(argv[1][c]),1);
    }
    write(1,"\n",1);
    return (0);
}
```

# 3. Level 0-3

```
Assignment name  : aff_last_param
Expected files   : aff_last_param.c
Allowed functions: write
--------------------------------------------------------------------------------

Write a program that takes strings as arguments, and displays its last
argument followed by a newline.

If the number of arguments is less than 1, the program displays a newline.

Examples:

$> ./aff_last_param "zaz" "mange" "des" "chats" | cat -e
chats$
$> ./aff_last_param "j'aime le savon" | cat -e
j'aime le savon$
$> ./aff_last_param
$
```

## 3.1. aff_last_param.c

```c
#include <unistd.h>

int main(int argc, char*argv[])
{
    int c;
    
    c = -1;
    if (argc > 1)
    {
        while(argv[argc-1][++c])
            write(1,&(argv[argc-1][c]),1);
    }
    write(1,"\n",1);
    return (0);
}
```


# 4. Level 0-4

```
Assignment name  : aff_z
Expected files   : aff_z.c
Allowed functions: write
--------------------------------------------------------------------------------

Write a program that takes a string, and displays the first 'z'
character it encounters in it, followed by a newline. If there are no
'z' characters in the string, the program writes 'z' followed
by a newline. If the number of parameters is not 1, the program displays
'z' followed by a newline.

Example:

$> ./aff_z "abc" | cat -e
z$
$> ./aff_z "dubO a POIL" | cat -e
z$
$> ./aff_z "zaz sent le poney" | cat -e
z$
$> ./aff_z | cat -e
z$
```

## 4.1. aff_z.c

```c
#include <unistd.h>

int main(int argc, char*argv[])
{
    (void) argc;
    (void) argv;
    write(1,"z\n",2);
    return (0);
}
```


# 5. Level 0-5

```
Assignment name  : ft_countdown
Expected files   : ft_countdown.c
Allowed functions: write
--------------------------------------------------------------------------------

Write a program that displays all digits in descending order, followed by a
newline.

Example:
$> ./ft_countdown | cat -e
9876543210$
$>
```

## ft_countdown.c

```c
#include <unistd.h>

int main()
{
    int i;
    
    i = '9';
    while (i >= '0')
    {
        write(1, &i , 1);
        i--;
    }
    write(1, "\n", 1);
    return (0);
}
```


# 6. Level 0-6

```
Assignment name  : ft_print_numbers
Expected files   : ft_print_numbers.c
Allowed functions: write
--------------------------------------------------------------------------------

Write a function that displays all digits in ascending order.

Your function must be declared as follows:

void	ft_print_numbers(void);
```

## 6.1. ft_print_numbers.c

```c
#include <unistd.h>

void	ft_print_numbers(void)
{
    int i;
    
    i = '0';
    while (i <= '9')
    {
        write(1, &i, 1);
        i++;
    }
    write(1, "\n", 1);
}
```


# 7. Level 0-7

```
Assignment name  : hello
Expected files   : hello.c
Allowed functions: write
--------------------------------------------------------------------------------

Write a program that displays "Hello World!" followed by a \n.

Example:

$>./hello
Hello World!
$>./hello | cat -e
Hello World!$
$>
```

# 6.1. hello.c

```c
#include <unistd.h>

int main()
{
    write(1, "Hello World!\n", 13);
    return (0);
}
```


# 8. Level 0-8

```
Assignment name  : maff_alpha
Expected files   : maff_alpha.c
Allowed functions: write
--------------------------------------------------------------------------------

Write a program that displays the alphabet, with even letters in uppercase, and
odd letters in lowercase, followed by a newline.

Example:

$> ./maff_alpha | cat -e
aBcDeFgHiJkLmNoPqRsTuVwXyZ$
```

## 8.1.  maff_alpha.c

```c
#include <unistd.h>

int main()
{
    char odd_c = 'a';
    char even_c = 'B';
    
    while (even_c <= 'Z')
    {
        write(1, &odd_c, 1);
        write (1, &even_c, 1);
        even_c += 2;
        odd_c += 2;
    }
    write(1, "\n", 1);
    return (0);
}
```


# 9. Level 0-9

```
Assignment name  : maff_revalpha
Expected files   : maff_revalpha.c
Allowed functions: write
--------------------------------------------------------------------------------

Write a program that displays the alphabet in reverse, with even letters in
uppercase, and odd letters in lowercase, followed by a newline.

Example:

$> ./maff_revalpha | cat -e
zYxWvUtSrQpOnMlKjIhGfEdCbA$
```

## 9.1. maff_revalpha.c

```c
#include <unistd.h>

int main()
{
    char odd_c = 'z';
    char even_c = 'Y';
    
    while (even_c >= 'A')
    {
        write(1, &odd_c, 1);
        write (1, &even_c, 1);
        even_c -= 2;
        odd_c -= 2;
    }
    write(1, "\n", 1);
    return (0);
}
```

# 10. Level 0-10

```
Assignment name  : only_a
Expected files   : only_a.c
Allowed functions: write
--------------------------------------------------------------------------------

Write a program that displays a 'a' character on the standard output.
```

## 10.1. only_a.c

```c
#include <unistd.h>

int main()
{
    write(1, "a", 1);
    return (0);
}
```

# 10. Level 0-11

```
Assignment name  : only_z
Expected files   : only_z.c
Allowed functions: write
--------------------------------------------------------------------------------

Write a program that displays a 'z' character on the standard output.
```

# 10.1. only_z.c

```c
#include <unistd.h>

int main()
{
    write(1, "z", 1);
    return (0);
}
```