# Ex00

## ft_print_program_name.c

```c
/* ************************************************************************** */
/*                                                                            */
/*                                                        :::      ::::::::   */
/*   ft_print_program_name.c                            :+:      :+:    :+:   */
/*                                                    +:+ +:+         +:+     */
/*   By: lyao-che <lyao-che@student.42kl.edu.my>    +#+  +:+       +#+        */
/*                                                +#+#+#+#+#+   +#+           */
/*   Created: 2022/04/14 13:53:58 by lyao-che          #+#    #+#             */
/*   Updated: 2022/04/14 14:22:12 by lyao-che         ###   ########.fr       */
/*                                                                            */
/* ************************************************************************** */

#include <unistd.h>

int	main(int argc, char*argv[])
{
	int	counter;

	counter = 0;
	if (argc > 0)
	{
		while (argv[0][counter] != '\0')
		{
			write(1, &(argv[0][counter]), 1);
			counter++;
		}
		write(1, "\n", 1);
	}
	return (0);
}
```

# Ex01

## ft_print_params.c

```c
/* ************************************************************************** */
/*                                                                            */
/*                                                        :::      ::::::::   */
/*   ft_print_params.c                                  :+:      :+:    :+:   */
/*                                                    +:+ +:+         +:+     */
/*   By: lyao-che <lyao-che@student.42kl.edu.my>    +#+  +:+       +#+        */
/*                                                +#+#+#+#+#+   +#+           */
/*   Created: 2022/04/14 14:15:26 by lyao-che          #+#    #+#             */
/*   Updated: 2022/04/14 15:05:47 by lyao-che         ###   ########.fr       */
/*                                                                            */
/* ************************************************************************** */

#include <unistd.h>

int	main(int argc, char*argv[])
{
	int c1;
	int c2;

	c1 = 1;
	c2 = 0;
	if (argc > 1)
	{
		while (c1 < argc)
		{
			c2 = 0;
			while (argv[c1][c2] != '\0')
			{
				write(1, &(argv[c1][c2]), 1);
				c2++;
			}
			c1++;
			write(1, "\n", 1);
		}
	}
	return (0);
}
```

# Ex02

## ft_rev_params.c

```c
/* ************************************************************************** */
/*                                                                            */
/*                                                        :::      ::::::::   */
/*   ft_rev_params.c                                    :+:      :+:    :+:   */
/*                                                    +:+ +:+         +:+     */
/*   By: lyao-che <lyao-che@student.42kl.edu.my>    +#+  +:+       +#+        */
/*                                                +#+#+#+#+#+   +#+           */
/*   Created: 2022/04/14 15:10:27 by lyao-che          #+#    #+#             */
/*   Updated: 2022/04/14 15:18:20 by lyao-che         ###   ########.fr       */
/*                                                                            */
/* ************************************************************************** */

#include <unistd.h>

int	main(int argc, char*argv[])
{
	int	c1;
	int	c2;

	c1 = argc - 1;
	c2 = 0;
	if (argc > 1)
	{
		while (c1 > 0)
		{
			c2 = 0;
			while (argv[c1][c2] != '\0')
			{
				write(1, &(argv[c1][c2]), 1);
				c2++;
			}
			write(1, "\n", 1);
			c1--;
		}
	}
}
```

# Ex03

##  ft_sort_params.c

```c
/* ************************************************************************** */
/*                                                                            */
/*                                                        :::      ::::::::   */
/*   ft_sort_params.c                                   :+:      :+:    :+:   */
/*                                                    +:+ +:+         +:+     */
/*   By: lyao-che <lyao-che@student.42kl.edu.my>    +#+  +:+       +#+        */
/*                                                +#+#+#+#+#+   +#+           */
/*   Created: 2022/04/14 15:22:41 by lyao-che          #+#    #+#             */
/*   Updated: 2022/04/20 08:06:54 by lyao-che         ###   ########.fr       */
/*                                                                            */
/* ************************************************************************** */
#include <unistd.h>

void	ft_putstr(char *str)
{
	while (*str != '\0')
	{
		write(1, &(*str), 1);
		str++;
	}
	write(1, "\n", 1);
}

int	ft_strcmp(char *s1, char *s2)
{
	int	c;

	c = 0;
	while (s1[c] != '\0' && s2[c] != '\0' && s1[c] == s2[c])
		c++;
	return (s1[c] - s2[c]);
}

void	ft_swap(int *a, int *b)
{
	int	temp;

	temp = *b;
	*b = *a;
	*a = temp;
}

void	execute(int argc, char*argv[])
{
	int	c1;
	int	c2;
	int	c3;
	int	argv2[100];

	c1 = 1;
	c2 = 1;
	while (c1 < argc)
	{
		argv2[c1] = c1;
		c1++;
	}
	while (c2 < argc)
	{
		c3 = c2;
		while (c3 < argc)
		{
			if (ft_strcmp(argv[argv2[c2]], argv[argv2[c3]]) > 0)
				ft_swap(&argv2[c2], &argv2[c3]);
			c3++;
		}
		ft_putstr(argv[argv2[c2++]]);
	}
}

int	main(int argc, char*argv[])
{
	if (argc > 1)
	{
		execute(argc, argv);
	}
	return (0);
}
```