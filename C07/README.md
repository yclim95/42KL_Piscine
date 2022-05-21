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
/*   Created: 2022/04/18 14:26:01 by lyao-che          #+#    #+#             */
/*   Updated: 2022/04/18 14:31:25 by lyao-che         ###   ########.fr       */
/*                                                                            */
/* ************************************************************************** */

#include <stdio.h>
#include <string.h>

char	*ft_strdup(char *src);

int	main(void)
{
	char source[] = "GeeksForGeeks";
	char* target1 = strdup(source);
	char* target2 = ft_strdup(source);
	printf("target1: %s\n", target1);
	printf("target2: %s\n", target2);
	return (0);
}
```

## ft_strdup.c

```c
/* ************************************************************************** */
/*                                                                            */
/*                                                        :::      ::::::::   */
/*   ft_strdup.c                                        :+:      :+:    :+:   */
/*                                                    +:+ +:+         +:+     */
/*   By: lyao-che <lyao-che@student.42kl.edu.my>    +#+  +:+       +#+        */
/*                                                +#+#+#+#+#+   +#+           */
/*   Created: 2022/04/18 14:19:16 by lyao-che          #+#    #+#             */
/*   Updated: 2022/04/18 16:37:05 by lyao-che         ###   ########.fr       */
/*                                                                            */
/* ************************************************************************** */

#include <stdlib.h>

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

	target = (char *)malloc(ft_strlen(src) * sizeof(char));
	if (target)
		return (ft_strcpy(src, target));
	else
		return (target);
}
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
/*   Created: 2022/04/21 07:39:41 by lyao-che          #+#    #+#             */
/*   Updated: 2022/04/21 08:29:16 by lyao-che         ###   ########.fr       */
/*                                                                            */
/* ************************************************************************** */
#include <stdio.h>

int	*ft_range(int min, int max);

void	print_test(int *test, int size)
{
	int i;

	for (i = 0; i < size - 1; i++)
	{
		printf("%d - ", test[i]);
	}
	if (size > 0)
		printf("%d\n", test[size - 1]);
	if (test == NULL)
		printf("NULL\n");
}

int	main(void)
{
	int *test = ft_range(2,5);
	int *test1 = ft_range(6,5);
	int *test2 = ft_range(5,5);
	int *test3 = ft_range(-1,3);
	int *test4 = ft_range(3,-1);
	print_test(test, 3);
	print_test(test1, 0);
	print_test(test2, 0);
	print_test(test3, 4);
	print_test(test4, 0);
	return (0);
}
```

## ft_range.c

```c
/* ************************************************************************** */
/*                                                                            */
/*                                                        :::      ::::::::   */
/*   ft_range.c                                         :+:      :+:    :+:   */
/*                                                    +:+ +:+         +:+     */
/*   By: lyao-che <lyao-che@student.42kl.edu.my>    +#+  +:+       +#+        */
/*                                                +#+#+#+#+#+   +#+           */
/*   Created: 2022/04/20 15:47:56 by lyao-che          #+#    #+#             */
/*   Updated: 2022/04/21 08:30:50 by lyao-che         ###   ########.fr       */
/*                                                                            */
/* ************************************************************************** */
#include <stdlib.h>
int	*ft_range(int min, int max)
{
	int	c;
	int	*range;

	c = 0;
	if (min >= max)
		return (NULL);
	else
	{
		range = (int*)malloc(sizeof(int) * (max - min));
		while (min < max)
			range[c++] = min++;
	}
	return (range);
}
```

# Ex02

## main.c

```c
/* ************************************************************************** */
/*                                                                            */
/*                                                        :::      ::::::::   */
/*   main.c                                             :+:      :+:    :+:   */
/*                                                    +:+ +:+         +:+     */
/*   By: lyao-che <lyao-che@student.42kl.edu.my>    +#+  +:+       +#+        */
/*                                                +#+#+#+#+#+   +#+           */
/*   Created: 2022/04/21 08:47:37 by lyao-che          #+#    #+#             */
/*   Updated: 2022/04/21 08:53:53 by lyao-che         ###   ########.fr       */
/*                                                                            */
/* ************************************************************************** */

#include <stdio.h>
#include <stdlib.h>

int		ft_ultimate_range(int **range, int min, int max);
void	test_ultimate_range_function(int min, int max);
void	print_test(int *test, int size);

int		main(void)
{
	test_ultimate_range_function(3, 5);
	test_ultimate_range_function(0, 11);
	test_ultimate_range_function(8, 2);
	test_ultimate_range_function(2, 2);
	test_ultimate_range_function(10, 20);
	test_ultimate_range_function(20, 15);
	test_ultimate_range_function(99, 99);
	test_ultimate_range_function(1, 12);
	test_ultimate_range_function(-1, 12);
	test_ultimate_range_function(1, -12);
}

void	test_ultimate_range_function(int min, int max)
{
	int size;
	int *test;

	size = ft_ultimate_range(&test, min, max);
	printf("\nsize = %d\n", size);
	print_test(test, size);
	free(test);
}

void	print_test(int *test, int size)
{
	int i;

	for (i = 0; i < size - 1; i++)
	{
		printf("%d - ", test[i]);
	}
	if (size > 0)
		printf("%d\n", test[size - 1]);
}
```

## ft_ultimate_range.c

```c
/* ************************************************************************** */
/*                                                                            */
/*                                                        :::      ::::::::   */
/*   ft_ultimate_range.c                                :+:      :+:    :+:   */
/*                                                    +:+ +:+         +:+     */
/*   By: lyao-che <lyao-che@student.42kl.edu.my>    +#+  +:+       +#+        */
/*                                                +#+#+#+#+#+   +#+           */
/*   Created: 2022/04/21 08:40:15 by lyao-che          #+#    #+#             */
/*   Updated: 2022/04/21 08:55:58 by lyao-che         ###   ########.fr       */
/*                                                                            */
/* ************************************************************************** */
#include <stdlib.h>

int	ft_ultimate_range(int **range, int min, int max)
{
	int	*prange;
	int	c;

	c = 0;
	if (min >= max)
	{
		*range = (void *)0;
		return (0);
	}
	prange = (int *) malloc(sizeof(int) * (max - min));
	while (min < max)
		prange[c++] = min++;
	*range = prange;
	return (c);
}
```

# Ex03

## main.c

```c
/* ************************************************************************** */
/*                                                                            */
/*                                                        :::      ::::::::   */
/*   main.c                                             :+:      :+:    :+:   */
/*                                                    +:+ +:+         +:+     */
/*   By: lyao-che <lyao-che@student.42kl.edu.my>    +#+  +:+       +#+        */
/*                                                +#+#+#+#+#+   +#+           */
/*   Created: 2022/04/21 10:05:16 by lyao-che          #+#    #+#             */
/*   Updated: 2022/04/21 11:34:31 by lyao-che         ###   ########.fr       */
/*                                                                            */
/* ************************************************************************** */
#include <stdio.h>
#include <stdlib.h>

char	*ft_strjoin(int size, char **strs, char *sep);

int	main(void)
{
	char    **array;

    array = (char **)malloc(sizeof(char *) * 4);
    array[0] = "Hello";
    array[1] = "42 !!!";
    array[2] = "We love";
    array[3] = "You!!!";

    printf("Result <%s>", ft_strjoin(2, array, " "));
}
```

## ft_strjoin.c

```c
/* ************************************************************************** */
/*                                                                            */
/*                                                        :::      ::::::::   */
/*   ft_strjoin.c                                       :+:      :+:    :+:   */
/*                                                    +:+ +:+         +:+     */
/*   By: lyao-che <lyao-che@student.42kl.edu.my>    +#+  +:+       +#+        */
/*                                                +#+#+#+#+#+   +#+           */
/*   Created: 2022/04/21 09:16:36 by lyao-che          #+#    #+#             */
/*   Updated: 2022/04/21 11:34:59 by lyao-che         ###   ########.fr       */
/*                                                                            */
/* ************************************************************************** */

#include <stdlib.h>
#include <stdio.h>

int	ft_total_size(int size, char **strs)
{
	int	crow;
	int	ccol;
	int	sep_num;
	int	strs_num;

	crow = 0;
	strs_num = 0;
	while (crow < size)
	{
		ccol = 0;
		while (strs[crow][ccol] != '\0')
			ccol++;
		strs_num += ccol;
		crow++;
	}
	sep_num = (size - 1) * 1;
	return (strs_num + sep_num);
}

char	*ft_check(char *ps, int size, char **strs)
{
	int		total_size;

	if (size == 0)
	{
		ps = malloc(sizeof(char));
		*ps = 0;
		return (ps);
	}
	if (size >= 1)
	{
		total_size = ft_total_size(size, strs);
		ps = malloc(sizeof(char) * total_size);
	}
	return (ps);
}

char	*ft_strjoin(int size, char **strs, char *sep)
{
	int		crow;
	int		ccol;
	char	*ps;
	int		i;

	ps = NULL;
	ps = ft_check(ps, size, strs);
	crow = 0;
	i = 0;
	if (!(ps) && size < 0)
		return (NULL);
	while (i < size)
	{
		ccol = 0;
		while (strs[i][ccol] != '\0')
			ps[crow++] = strs[i][ccol++];
		ccol = 0;
		while (sep[ccol] != '\0' && i != size - 1)
			ps[crow++] = sep[ccol++];
		i++;
	}
	ps[crow] = '\0';
	return (ps);
}
```