# EX00

## main.c 

```c
/* ************************************************************************** */
/*                                                                            */
/*                                                        :::      ::::::::   */
/*   main.c                                             :+:      :+:    :+:   */
/*                                                    +:+ +:+         +:+     */
/*   By: lyao-che <lyao-che@student.42kl.edu.my>    +#+  +:+       +#+        */
/*                                                +#+#+#+#+#+   +#+           */
/*   Created: 2022/04/13 07:16:53 by lyao-che          #+#    #+#             */
/*   Updated: 2022/04/13 07:31:20 by lyao-che         ###   ########.fr       */
/*                                                                            */
/* ************************************************************************** */

#include <stdio.h>
#include <string.h>

int	ft_strcmp(char *s1, char *s2);

int	main(void)
{
	char s1[] = "testing123";
	char s2[] = "testing123";
	int strcmp_r = strcmp(s1,s2);
	int ft_strcmp_r = ft_strcmp(s1,s2);

	printf("strcmp() function: %d\n", strcmp_r);
	printf("ft_strcmp() function: %d\n", ft_strcmp_r);
	return (0);
}
```

## ft_strcmp.c

```c
/* ************************************************************************** */
/*                                                                            */
/*                                                        :::      ::::::::   */
/*   ft_strcmp.c                                        :+:      :+:    :+:   */
/*                                                    +:+ +:+         +:+     */
/*   By: lyao-che <lyao-che@student.42kl.edu.my>    +#+  +:+       +#+        */
/*                                                +#+#+#+#+#+   +#+           */
/*   Created: 2022/04/13 07:13:02 by lyao-che          #+#    #+#             */
/*   Updated: 2022/04/13 07:16:46 by lyao-che         ###   ########.fr       */
/*                                                                            */
/* ************************************************************************** */

int	ft_strcmp(char *s1, char *s2)
{
	int	c;

	c = 0;
	while (s1[c] != '\0' && s2[c] != '\0' && s1[c] == s2[c])
		c++;
	return (s1[c] - s2[c]);
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
/*   Created: 2022/04/13 08:20:00 by lyao-che          #+#    #+#             */
/*   Updated: 2022/04/18 07:18:12 by lyao-che         ###   ########.fr       */
/*                                                                            */
/* ************************************************************************** */

#include <stdio.h>
#include <string.h>

int	ft_strncmp(char *s1, char *s2, unsigned int n);

int	main(void)
{
	char s1[] = "abc123";
	char s2[] = "1";
	int strncmp_r;
	strncmp_r = ft_strncmp(s1,s2,8);

	printf("strncmp() function: %d\n", strncmp(s1,s2,8));
	//printf("ft_strncmp() function: %d\n", ft_strncmp(s1,s2,8));
	printf("%d\n", strncmp_r);
	return (0);
}
```

## ft_strncmp.c

```c
/* ************************************************************************** */
/*                                                                            */
/*                                                        :::      ::::::::   */
/*   ft_strncmp.c                                       :+:      :+:    :+:   */
/*                                                    +:+ +:+         +:+     */
/*   By: lyao-che <lyao-che@student.42kl.edu.my>    +#+  +:+       +#+        */
/*                                                +#+#+#+#+#+   +#+           */
/*   Created: 2022/04/13 07:49:55 by lyao-che          #+#    #+#             */
/*   Updated: 2022/04/18 07:15:29 by lyao-che         ###   ########.fr       */
/*                                                                            */
/* ************************************************************************** */
int	ft_strncmp(char *s1, char *s2, unsigned int n)
{
	unsigned int	c;
	unsigned int	cmp;

	c = 0;
	cmp = 0;
	while (!cmp && (c < n) && (s1[c] != '\0') && (s2[c] != '\0'))
	{
		cmp = s1[c] - s2[c];
		c++;
	}
	if (!cmp && c < n && (s1[c] == '\0' || s2[c] == '\0'))
		cmp = s1[c] - s2[c];
	return (cmp);
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
/*   Created: 2022/04/13 11:46:27 by lyao-che          #+#    #+#             */
/*   Updated: 2022/04/13 14:23:28 by lyao-che         ###   ########.fr       */
/*                                                                            */
/* ************************************************************************** */
#include <stdio.h>
#include <string.h>

char	*ft_strcat(char *dest, char *src);

int main(void)
{
	char test1[100] = "test1234";
	char test2[] = " bla";
	ft_strcat(test1, test2);
	strcat(test1,test2);
	printf("strcat() function: %s\n", test1);
	printf("ft_strcat function: %s\n", test1);
	return (0);
}
```

## ft_strcat.c

```c
/* ************************************************************************** */
/*                                                                            */
/*                                                        :::      ::::::::   */
/*   ft_strcat.c                                        :+:      :+:    :+:   */
/*                                                    +:+ +:+         +:+     */
/*   By: lyao-che <lyao-che@student.42kl.edu.my>    +#+  +:+       +#+        */
/*                                                +#+#+#+#+#+   +#+           */
/*   Created: 2022/04/13 11:42:02 by lyao-che          #+#    #+#             */
/*   Updated: 2022/04/14 10:45:18 by lyao-che         ###   ########.fr       */
/*                                                                            */
/* ************************************************************************** */
int	ft_strlen(char *str)
{
	int	c;

	c = 0;
	while (*str != '\0')
	{
		c++;
		str++;
	}
	return (c);
}

char	*ft_strcat(char *dest, char *src)
{
	int	c;

	c = ft_strlen(dest);
	while (*src != '\0')
	{
		dest[c] = *src;
		c++;
		src++;
	}
	dest[c] = '\0';
	return (dest);
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
/*   Created: 2022/04/13 14:34:43 by lyao-che          #+#    #+#             */
/*   Updated: 2022/04/13 14:49:36 by lyao-che         ###   ########.fr       */
/*                                                                            */
/* ************************************************************************** */

#include <stdio.h>
#include <string.h>

char *ft_strncat(char *dest, char *src, unsigned int nb);

int main(void)
{
	char test1[10] = "Hello";
	char test2[] = " 42 KL";
	strncat(test1,test2,3);
	//ft_strncat(test1,test2,3);
	printf("strncat() function: %s\n", test1);
	printf("ft_strncat() function: %s\n", test1);
}
```

## ft_strncat.c

```c
/* ************************************************************************** */
/*                                                                            */
/*                                                        :::      ::::::::   */
/*   ft_strncat.c                                       :+:      :+:    :+:   */
/*                                                    +:+ +:+         +:+     */
/*   By: lyao-che <lyao-che@student.42kl.edu.my>    +#+  +:+       +#+        */
/*                                                +#+#+#+#+#+   +#+           */
/*   Created: 2022/04/13 14:34:07 by lyao-che          #+#    #+#             */
/*   Updated: 2022/04/14 11:05:48 by lyao-che         ###   ########.fr       */
/*                                                                            */
/* ************************************************************************** */

char	*ft_strncat(char *dest, char *src, unsigned int nb)
{
	unsigned int	c1;
	unsigned int	c2;

	c1 = 0;
	c2 = 0;
	while (dest[c1] != '\0')
		c1++;
	while (src[c2] != '\0' && c2 < nb)
	{
		dest[c1 + c2] = src[c2];
		c2++;
	}
	dest[c1 + c2] = '\0';
	return (dest);
}
```