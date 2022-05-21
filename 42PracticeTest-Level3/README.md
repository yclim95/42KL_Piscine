# 1. Level 3 - 1

```
Assignment name  : add_prime_sum
Expected files   : add_prime_sum.c
Allowed functions: write, exit
--------------------------------------------------------------------------------

Write a program that takes a positive integer as argument and displays the sum
of all prime numbers inferior or equal to it followed by a newline.

If the number of arguments is not 1, or the argument is not a positive number,
just display 0 followed by a newline.

Yes, the examples are right.

Examples:

$>./add_prime_sum 5
10
$>./add_prime_sum 7 | cat -e
17$
$>./add_prime_sum | cat -e
0$
$>
```

## 1.1. add_prime_sum.c

```c
#include <unistd.h>

int ft_atoi(char *str)
{
	int result;
	int sign;

	result = 0;
	sign = 1;
	while (*str == ' ' || (*str >= '\t' && *str <= '\r'))
		str++;
	if (*str ==  '-')
		sign = -1;
	while (*str != '\0')
	{
		if (*str >= '0' && *str <= '9')
			result = (*str - '0') + (result * 10);
		str++;
	}
	return (result * sign);
}

void ft_putnbr(int num)
{
	char c;
	if (num < 0)
	{
		num = -num;
		write(1, "-", 1);
	}
	if (num < 10)
	{
		c = num + '0';
		write(1, &c, 1);
	}
	else
	{
		ft_putnbr(num / 10);
		ft_putnbr(num % 10);
	}
}

int ft_is_prime (int num)
{
	int i;
	i = 3;
	if (num <= 1)
		return (0);
	if (num % 2 == 0 && num > 2)
		return (0);
	while (i < (num / 2))
	{
		if (num % i == 0)
			return (0);
		i += 2;
	}
	return (1);
}

int main(int argc, char*argv[])
{
	int num;
	int sum;

	if (argc == 2)
	{
		num = ft_atoi(argv[1]);
		sum = 0;
		while (num > 0)
		{
			if (ft_is_prime(num))
				sum += num;
			num--;
		}
		ft_putnbr(sum);
	}
	else
		write(1, "0\n", 2);
	return (0);
}
```

# 2. Level 3 - 2

```
Assignment name  : epur_str
Expected files   : epur_str.c
Allowed functions: write
--------------------------------------------------------------------------------

Write a program that takes a string, and displays this string with exactly one
space between words, with no spaces or tabs either at the beginning or the end,
followed by a \n.

A "word" is defined as a part of a string delimited either by spaces/tabs, or
by the start/end of the string.

If the number of arguments is not 1, or if there are no words to display, the
program displays \n.

Example:

$> ./epur_str "vous voyez c'est facile d'afficher la meme chose" | cat -e
vous voyez c'est facile d'afficher la meme chose$
$> ./epur_str " seulement          la c'est      plus dur " | cat -e
seulement la c'est plus dur$
$> ./epur_str "comme c'est cocasse" "vous avez entendu, Mathilde ?" | cat -e
$
$> ./epur_str "" | cat -e
$
$>
```

## 2.1. epur_str.c

```c
#include <unistd.h>

int main(int argc, char*argv[])
{
	int c;
	int flg;
	c = 0;

	if (argc == 2)
	{
		while (argv[1][c] == ' ' || argv[1][c] == '\t')
			c++;
		while (argv[1][c])
		{
			if (argv[1][c] == ' ' || argv[1][c] == '\t')
				flg = 1;
			if (argv[1][c] != ' ' &&  argv[1][c] != '\t')
			{
				if (flg)
					write(1, " ", 1);
				flg = 0;
				write(1, &(argv[1][c]), 1);
			}
			c++;
		}
	}
	write(1, "\n", 1);
	return (0);
}
```

# 3. Level 3 - 3

```
Assignment name  : expand_str
Expected files   : expand_str.c
Allowed functions: write
--------------------------------------------------------------------------------

Write a program that takes a string and displays it with exactly three spaces
between each word, with no spaces or tabs either at the beginning or the end,
followed by a newline.

A word is a section of string delimited either by spaces/tabs, or by the
start/end of the string.

If the number of parameters is not 1, or if there are no words, simply display
a newline.

Examples:

$> ./expand_str "vous   voyez   c'est   facile   d'afficher   la   meme   chose" | cat -e
vous   voyez   c'est   facile   d'afficher   la   meme   chose$
$> ./expand_str " seulement          la c'est      plus dur " | cat -e
seulement   la   c'est   plus   dur$
$> ./expand_str "comme c'est cocasse" "vous avez entendu, Mathilde ?" | cat -e
$
$> ./expand_str "" | cat -e
$
$>
```

## 3.1. expand_str.c

```c
#include <unistd.h>

int main(int argc, char *argv[])
{
	int c;
	int flg;

	c = 0;	
	if (argc == 2)
	{
		while (argv[1][c] == ' ' || argv[1][c] == '\t')
			c++;
		while (argv[1][c])
		{
			if (argv[1][c] == ' ' || argv[1][c] == '\t')
				flg = 1;
			if (argv[1][c] != ' ' && argv[1][c] != '\t')
			{
				if (flg)
					write(1, "   ", 3);
				write(1, &(argv[1][c]), 1);
				flg = 0;
			}
			c++;
		}
	}
	write(1, "\n", 1);
	return (0);
}
```

# 4. Level 3 - 4

```
Assignment name  : ft_range
Expected files   : ft_range.c
Allowed functions: malloc
--------------------------------------------------------------------------------

Write the following function:

int     *ft_range(int start, int end);

It must allocate (with malloc()) an array of integers, fill it with consecutive
values that begin at start and end at end (Including start and end !), then
return a pointer to the first value of the array.

Examples:

- With (1, 3) you will return an array containing 1, 2 and 3.
- With (-1, 2) you will return an array containing -1, 0, 1 and 2.
- With (0, 0) you will return an array containing 0.
- With (0, -3) you will return an array containing 0, -1, -2 and -3.
```

## 4.1. ft_range.c

```c
#include <stdio.h>
#include <stdlib.h>

int	*ft_range(int start, int end)
{
	int *p_int;
	int c;
	if (start >= end) 
		return (NULL);
	else
	{
		p_int = malloc(sizeof(int) * (end - start));
		c = 0;
		while (start <= end)
			p_int[c++] = start++;
	}
	return (p_int);
}

int main(void)
{
	int *s;
	s = ft_range(-1,4);
	int c;
	int len = 4 - (-1);
   	c = 0;
	while (c <= len)
	{
		printf("%d\n", s[c]);
		printf("c: %d\n", c);
		c++;
	}
	return (0);
}
```