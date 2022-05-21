# Ex00

## main.c

```c
/* ************************************************************************** */
/*                                                                            */
/*                                                        :::      ::::::::   */
/*   main.c                                             :+:      :+:    :+:   */
/*                                                    +:+ +:+         +:+     */
/*   By: lyao-che <lyao-che@student.42kl.edu.my>    +#+  +:+       +#+        */
/*                                                +#+#+#+#+#+   +#+           */
/*   Created: 2022/04/21 13:34:33 by lyao-che          #+#    #+#             */
/*   Updated: 2022/04/21 13:38:53 by lyao-che         ###   ########.fr       */
/*                                                                            */
/* ************************************************************************** */

#include "ft.h"

#include <stdio.h>
#include <unistd.h>

int	main(void)
{
	ft_putchar('c');
	return (0);
}

void	ft_putchar(char c)
{
	write(1, &c, 1);
}

void	ft_swap(int *a, int *b)
{
	int	temp;

	temp = *b;
	*b = *a;
	*a = temp;
}

void	ft_putstr(char *str)
{
	while (*str != '\0')
	{
		write(1, &(*str), 1);
		str++;
	}
}

int	ft_strlen(char *str)
{
	int	counter;

	counter = 0;
	while (str[counter] != '\0')
	{
		counter++;
	}
	return (counter);
}

int	ft_strcmp(char *s1, char *s2)
{
	int	c;

	c = 0;
	while (s1[c] != '\0' && s2[c] != '\0' && s1[c] == s2[c])
		c++;
	return (s1[c] - s2[c]);
}
```

## ft.h

```c
/* ************************************************************************** */
/*                                                                            */
/*                                                        :::      ::::::::   */
/*   ft.h                                               :+:      :+:    :+:   */
/*                                                    +:+ +:+         +:+     */
/*   By: lyao-che <lyao-che@student.42kl.edu.my>    +#+  +:+       +#+        */
/*                                                +#+#+#+#+#+   +#+           */
/*   Created: 2022/04/21 13:29:16 by lyao-che          #+#    #+#             */
/*   Updated: 2022/04/21 13:40:40 by lyao-che         ###   ########.fr       */
/*                                                                            */
/* ************************************************************************** */

#ifndef FT_H
# define FT_H

void	ft_putchar(char c);
void	ft_swap(int *a, int *b);
void	ft_putstr(char *str);
int		ft_strlen(char *str);
int		ft_strcmp(char *s1, char *s2);
#endif
```

# Ex01

## main.c

```c
/* ************************************************************************** */
/*                                                                            */
/*                                                        :::      ::::::::   */
/*   main.c                                             :+:      :+:    :+:   */
/*                                                    +:+ +:+         +:+     */
/*   By: lyao-che <lyao-che@student.42kl.edu.my>    +#+  +:+       +#+        */
/*                                                +#+#+#+#+#+   +#+           */
/*   Created: 2022/04/21 13:52:42 by lyao-che          #+#    #+#             */
/*   Updated: 2022/04/21 15:15:38 by lyao-che         ###   ########.fr       */
/*                                                                            */
/* ************************************************************************** */

#include "ft_boolean.h"

void ft_putstr(char *str)
{
	while (*str)
	write(1, str++, 1);
}

t_bool ft_is_even(int nbr)
{
	return ((EVEN(nbr)) ? TRUE : FALSE);
}

int	main(int argc, char **argv)
{
	(void)argv;
	if (ft_is_even(argc - 1) == TRUE)
		ft_putstr(EVEN_MSG);
	else
		ft_putstr(ODD_MSG);
	return (SUCCESS);
}
```

## ft_boolean.h

```c
/* ************************************************************************** */
/*                                                                            */
/*                                                        :::      ::::::::   */
/*   ft_boolean.h                                       :+:      :+:    :+:   */
/*                                                    +:+ +:+         +:+     */
/*   By: lyao-che <lyao-che@student.42kl.edu.my>    +#+  +:+       +#+        */
/*                                                +#+#+#+#+#+   +#+           */
/*   Created: 2022/04/21 13:50:23 by lyao-che          #+#    #+#             */
/*   Updated: 2022/04/23 08:35:40 by lyao-che         ###   ########.fr       */
/*                                                                            */
/* ************************************************************************** */

#ifndef FT_BOOLEAN_H
# define FT_BOOLEAN_H

# include <unistd.h>

# define EVEN(x) (x % 2 == 0)
# define EVEN_MSG "I have an even number of arguments.\n"
# define ODD_MSG "I have an odd number of arguments.\n"
# define TRUE 1
# define FALSE 0
# define SUCCESS 1

typedef int	t_bool;
#endif
```

# Ex02

## ft_abs.h

```c
/* ************************************************************************** */
/*                                                                            */
/*                                                        :::      ::::::::   */
/*   ft_abs.h                                           :+:      :+:    :+:   */
/*                                                    +:+ +:+         +:+     */
/*   By: lyao-che <lyao-che@student.42kl.edu.my>    +#+  +:+       +#+        */
/*                                                +#+#+#+#+#+   +#+           */
/*   Created: 2022/04/23 07:46:30 by lyao-che          #+#    #+#             */
/*   Updated: 2022/04/23 07:49:22 by lyao-che         ###   ########.fr       */
/*                                                                            */
/* ************************************************************************** */

#ifndef FT_ABS_H
# define FT_ABS_H

# define ABS(x) (x > 0 ? x : -x)
#endif
```

## main.c

```c
/* ************************************************************************** */
/*                                                                            */
/*                                                        :::      ::::::::   */
/*   main.c                                             :+:      :+:    :+:   */
/*                                                    +:+ +:+         +:+     */
/*   By: lyao-che <lyao-che@student.42kl.edu.my>    +#+  +:+       +#+        */
/*                                                +#+#+#+#+#+   +#+           */
/*   Created: 2022/04/23 07:50:38 by lyao-che          #+#    #+#             */
/*   Updated: 2022/04/23 07:57:08 by lyao-che         ###   ########.fr       */
/*                                                                            */
/* ************************************************************************** */

#include "ft_abs.h"
#include <stdio.h>

int	main(void)
{
	printf("%d", ABS(-4));
	return (0);
}
```

# Ex03

## ft_point.h

```c
/* ************************************************************************** */
/*                                                                            */
/*                                                        :::      ::::::::   */
/*   ft_point.h                                         :+:      :+:    :+:   */
/*                                                    +:+ +:+         +:+     */
/*   By: lyao-che <lyao-che@student.42kl.edu.my>    +#+  +:+       +#+        */
/*                                                +#+#+#+#+#+   +#+           */
/*   Created: 2022/04/23 08:09:37 by lyao-che          #+#    #+#             */
/*   Updated: 2022/04/23 08:13:54 by lyao-che         ###   ########.fr       */
/*                                                                            */
/* ************************************************************************** */

#ifndef FT_POINT_H
# define FT_POINT_H

typedef struct SPOINT
{
	int	x;
	int	y;
}	t_point;
#endif
```

## main.c

```c
/* ************************************************************************** */
/*                                                                            */
/*                                                        :::      ::::::::   */
/*   main.c                                             :+:      :+:    :+:   */
/*                                                    +:+ +:+         +:+     */
/*   By: lyao-che <lyao-che@student.42kl.edu.my>    +#+  +:+       +#+        */
/*                                                +#+#+#+#+#+   +#+           */
/*   Created: 2022/04/23 08:14:22 by lyao-che          #+#    #+#             */
/*   Updated: 2022/04/23 08:30:10 by lyao-che         ###   ########.fr       */
/*                                                                            */
/* ************************************************************************** */

#include "ft_point.h"
#include <stdio.h>

void	set_point(t_point *point)
{
	point->x = 42;
	point->y = 21;
}

int	main(void)
{
	t_point point;
	t_point *p_point;
	set_point(&point);
	p_point = &point;
	printf("point.x: %d\n", point.x);
	printf("point.y: %d\n", point.y);
	printf("point->x: %d\n", p_point->x);
	printf("point->y: %d\n", p_point->y);
	printf("*(point).x %d\n", (*p_point).x);
	printf("*(point).y %d\n", (*p_point).y);
	return (0);
}
```

# Ex04

## ft_stock_str.h

```c
/* ************************************************************************** */
/*                                                                            */
/*                                                        :::      ::::::::   */
/*   ft_stock_str.h                                     :+:      :+:    :+:   */
/*                                                    +:+ +:+         +:+     */
/*   By: lyao-che <lyao-che@student.42kl.edu.my>    +#+  +:+       +#+        */
/*                                                +#+#+#+#+#+   +#+           */
/*   Created: 2022/04/23 10:13:53 by lyao-che          #+#    #+#             */
/*   Updated: 2022/04/23 11:24:07 by lyao-che         ###   ########.fr       */
/*                                                                            */
/* ************************************************************************** */

#ifndef FT_STOCK_STR_H
# define FT_STOCK_STR_H

typedef struct s_stock_str
{
	int		size;
	char	*str;
	char	*copy;
}			t_stock_str;

#endif
```

## ft_strs_to_tab.c

```c
/* ************************************************************************** */
/*                                                                            */
/*                                                        :::      ::::::::   */
/*   ft_strs_to_tab.c                                   :+:      :+:    :+:   */
/*                                                    +:+ +:+         +:+     */
/*   By: lyao-che <lyao-che@student.42kl.edu.my>    +#+  +:+       +#+        */
/*                                                +#+#+#+#+#+   +#+           */
/*   Created: 2022/04/23 10:10:07 by lyao-che          #+#    #+#             */
/*   Updated: 2022/04/24 12:09:51 by lyao-che         ###   ########.fr       */
/*                                                                            */
/* ************************************************************************** */
#include <stdlib.h>
#include <stdio.h>
#include "ft_stock_str.h"

int	ft_strlen(char *src)
{
	int	i;

	i = 0;
	while (src[i])
		i++;
	return (i);
}

char	*ft_strcpy(char *src, char *dest)
{
	int	i;

	i = 0;
	while (src[i])
	{
		dest[i] = src[i];
		i++;
	}
	dest[i] = '\0';
	return (dest);
}

char	*ft_strdup(char *src)
{
	char	*target;

	target = malloc(sizeof(src) * (ft_strlen(src) + 1));
	if (target)
		return (ft_strcpy(src, target));
	else
		return (target);
}

struct s_stock_str	*ft_strs_to_tab(int ac, char **av)
{
	t_stock_str		*p_str;
	int				c;

	p_str = malloc(sizeof(t_stock_str) * (ac + 1));
	if (p_str == NULL)
		return (NULL);
	c = 0;
	while (c < ac)
	{
		p_str[c].str = av[c];
		p_str[c].copy = ft_strdup(av[c]);
		p_str[c].size = ft_strlen(av[c]);
		c++;
	}
	p_str[c].str = 0;
	p_str[c].copy = 0;
	p_str[c].size = 0;
	return (p_str);
}
```

## main.c

```c
/* ************************************************************************** */
/*                                                                            */
/*                                                        :::      ::::::::   */
/*   main.c                                             :+:      :+:    :+:   */
/*                                                    +:+ +:+         +:+     */
/*   By: lyao-che <lyao-che@student.42kl.edu.my>    +#+  +:+       +#+        */
/*                                                +#+#+#+#+#+   +#+           */
/*   Created: 2022/04/23 10:42:38 by lyao-che          #+#    #+#             */
/*   Updated: 2022/04/24 07:27:00 by lyao-che         ###   ########.fr       */
/*                                                                            */
/* ************************************************************************** */

#include "ft_stock_str.h"
#include <stdio.h>
struct	s_stock_str	*ft_strs_to_tab(int ac, char **av);
void	ft_show_tab(struct s_stock_str *par);


#include <unistd.h>

void	ft_putchar(char c)
{
	write(1, &c, 1);
}

void	ft_putstr(char *str)
{
	while (*str != '\0')
	{
		write(1, &(*str), 1);
		str++;
	}
}

void	ft_putnbr(int nb)
{
	if (nb < 0)
	{
		ft_putchar('-');
		nb *= -1;
	}
	if (nb < 10)
	{
		ft_putchar(nb + 48);
		return ;
	}
	else
		ft_putnbr(nb / 10);
	ft_putnbr(nb % 10);
}

void ft_show_tab(struct s_stock_str *par)
{
	int	c;

	c = 0;

	while (par[c].str != 0)
	{
		ft_putstr(par[c].str);
		ft_putchar('\n');
		ft_putnbr(par[c].size);
		ft_putchar('\n');
		ft_putstr(par[c].copy);
		ft_putchar('\n');
		c++;
	}
}

int	main(int argc, char **argv)
{
	/*
	struct s_stock_str *strs= ft_strs_to_tab(argc, argv);
	int i = 0;
	while(i < 3)
	{
		printf("%s\n",strs[i].str);
		printf("%s\n",strs[i].copy);
		printf("%i\n",strs[i].size);
		i++;
	}
	*/
	ft_show_tab(ft_strs_to_tab(argc, argv));
}
```

# Ex05

## ft_stock_str.h

```c
/* ************************************************************************** */
/*                                                                            */
/*                                                        :::      ::::::::   */
/*   ft_stock_str.h                                     :+:      :+:    :+:   */
/*                                                    +:+ +:+         +:+     */
/*   By: lyao-che <lyao-che@student.42kl.edu.my>    +#+  +:+       +#+        */
/*                                                +#+#+#+#+#+   +#+           */
/*   Created: 2022/04/23 10:13:53 by lyao-che          #+#    #+#             */
/*   Updated: 2022/04/23 11:24:07 by lyao-che         ###   ########.fr       */
/*                                                                            */
/* ************************************************************************** */

#ifndef FT_STOCK_STR_H
# define FT_STOCK_STR_H

typedef struct s_stock_str
{
	int		size;
	char	*str;
	char	*copy;
}			t_stock_str;

#endif
```


## ft_strs_to_tab.c

```c
/* ************************************************************************** */
/*                                                                            */
/*                                                        :::      ::::::::   */
/*   ft_strs_to_tab.c                                   :+:      :+:    :+:   */
/*                                                    +:+ +:+         +:+     */
/*   By: lyao-che <lyao-che@student.42kl.edu.my>    +#+  +:+       +#+        */
/*                                                +#+#+#+#+#+   +#+           */
/*   Created: 2022/04/23 10:10:07 by lyao-che          #+#    #+#             */
/*   Updated: 2022/04/24 08:31:03 by lyao-che         ###   ########.fr       */
/*                                                                            */
/* ************************************************************************** */
#include <stdlib.h>
#include <stdio.h>
#include "ft_stock_str.h"

int	ft_strlen(char *src)
{
	int	i;

	i = 0;
	while (src[i] != '\0')
		i++;
	return (i);
}

char	*ft_strcpy(char *src, char *dest)
{
	int	i;

	i = 0;
	while (src[i] != '\0')
	{
		dest[i] = src[i];
		i++;
	}
	dest[i] = '\0';
	return (dest);
}

char	*ft_strdup(char *src)
{
	char	*target;

	target = (char *)malloc(ft_strlen(src) * sizeof(char) + 1);
	if (target)
		return (ft_strcpy(src, target));
	else
		return (target);
}

struct s_stock_str	*ft_strs_to_tab(int ac, char **av)
{
	t_stock_str		*p_str;
	int				c;
	int 			i;

	p_str = malloc(sizeof(t_stock_str) * ac);
	if (p_str == NULL)
		return (NULL);
	c = 0;
	i = 1;
	while (c < ac - 1)
	{
		p_str[c].str = av[i];
		p_str[c].copy = ft_strdup(av[i]);
		p_str[c].size = ft_strlen(av[i]);
		c++;
		i++;
	}
	p_str[c].str = 0;
	p_str[c].copy = 0;
	p_str[c].size = 0;
	return (p_str);
}
```

## ft_show_tab.c

```c
/* ************************************************************************** */
/*                                                                            */
/*                                                        :::      ::::::::   */
/*   ft_show_tab.c                                      :+:      :+:    :+:   */
/*                                                    +:+ +:+         +:+     */
/*   By: lyao-che <lyao-che@student.42kl.edu.my>    +#+  +:+       +#+        */
/*                                                +#+#+#+#+#+   +#+           */
/*   Created: 2022/04/23 11:52:28 by lyao-che          #+#    #+#             */
/*   Updated: 2022/04/24 08:17:53 by lyao-che         ###   ########.fr       */
/*                                                                            */
/* ************************************************************************** */

#include <unistd.h> 
#include "ft_stock_str.h"

void	ft_putchar(char c)
{
	write(1, &c, 1);
}

void	ft_putstr(char *str)
{
	while (*str != '\0')
	{
		write(1, &(*str), 1);
		str++;
	}
}

void	ft_putnbr(int nb)
{
	if (nb < 0)
	{
		ft_putchar('-');
		nb *= -1;
	}
	if (nb < 10)
	{
		ft_putchar(nb + 48);
		return ;
	}
	else
		ft_putnbr(nb / 10);
	ft_putnbr(nb % 10);
}

void	ft_show_tab(struct s_stock_str *par)
{
	int	c;

	c = 0;
	while (par[c].str != 0)
	{
		ft_putstr(par[c].str);
		ft_putchar('\n');
		ft_putnbr(par[c].size);
		ft_putchar('\n');
		ft_putstr(par[c].copy);
		ft_putchar('\n');
		c++;
	}
}
```

## main.c

```c
/* ************************************************************************** */
/*                                                                            */
/*                                                        :::      ::::::::   */
/*   main.c                                             :+:      :+:    :+:   */
/*                                                    +:+ +:+         +:+     */
/*   By: lyao-che <lyao-che@student.42kl.edu.my>    +#+  +:+       +#+        */
/*                                                +#+#+#+#+#+   +#+           */
/*   Created: 2022/04/23 13:26:28 by lyao-che          #+#    #+#             */
/*   Updated: 2022/04/24 08:32:01 by lyao-che         ###   ########.fr       */
/*                                                                            */
/* ************************************************************************** */

#include "ft_stock_str.h"
#include <unistd.h>
struct	s_stock_str	*ft_strs_to_tab(int ac, char **av);
void	ft_show_tab(struct s_stock_str *par);

int	main(int argc, char*argv[])
{
	/*
	char	*str1 = "42";
	char	*str2 = "I";
	char	*str3 = "love";
	char	*str4 = "You !";
	int		size;
	char	*strs[4];
	strs[0] = str1;
	strs[1] = str2;
	strs[2] = str3;
	strs[3] = str4;
	size = 4;
	*/
	ft_show_tab(ft_strs_to_tab(argc, argv));
}
```