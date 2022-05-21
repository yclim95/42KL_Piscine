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
/*   Created: 2022/04/12 07:17:44 by lyao-che          #+#    #+#             */
/*   Updated: 2022/04/12 07:25:47 by lyao-che         ###   ########.fr       */
/*                                                                            */
/* ************************************************************************** */

#include <stdio.h>

char	*ft_strcpy(char *dest, char *src);

int main(void)
{
	char srcS []= "Source string";
	char destS [] = "Destination string";
	char *pdest;

	printf("Before:\n\tSource String: %s\n", srcS);
	printf("\tDestination String: %s\n", destS);
	pdest = ft_strcpy(destS, srcS);
	printf("After: \n\tSource String: %s\n", srcS);
	printf("\tDestination String: %s\n", pdest);
}
```

## ft_strcpy.c

```c
/* ************************************************************************** */
/*                                                                            */
/*                                                        :::      ::::::::   */
/*   ft_strcpy.c                                        :+:      :+:    :+:   */
/*                                                    +:+ +:+         +:+     */
/*   By: lyao-che <lyao-che@student.42kl.edu.my>    +#+  +:+       +#+        */
/*                                                +#+#+#+#+#+   +#+           */
/*   Created: 2022/04/11 17:46:15 by lyao-che          #+#    #+#             */
/*   Updated: 2022/04/12 07:17:35 by lyao-che         ###   ########.fr       */
/*                                                                            */
/* ************************************************************************** */

char	*ft_strcpy(char *dest, char *src)
{
	int	counter;

	counter = 0;
	while (src[counter] != '\0')
	{
		dest[counter] = src[counter];
		counter++;
	}
	dest[counter] = '\0';
	return (dest);
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
/*   Created: 2022/04/12 07:17:44 by lyao-che          #+#    #+#             */
/*   Updated: 2022/04/12 14:52:30 by lyao-che         ###   ########.fr       */
/*                                                                            */
/* ************************************************************************** */

#include <stdio.h>

char	*ft_strncpy(char *dest, char *src, unsigned int n);

int main(void)
{
	char srcS []= "Source string";
	char destS [] = "Destination string";
	char *pdest;
	unsigned int n = 3;

	printf("Before:\n\tSource String: %s\n", srcS);
	printf("\tDestination String: %s\n", destS);
	pdest = ft_strncpy(destS, srcS, n);
	printf("After: \n\tSource String: %s\n", srcS);
	printf("\tDestination String: %s\n", pdest);
}
```

## ft_strncpy.c

```c
/* ************************************************************************** */
/*                                                                            */
/*                                                        :::      ::::::::   */
/*   ft_strncpy.c                                       :+:      :+:    :+:   */
/*                                                    +:+ +:+         +:+     */
/*   By: lyao-che <lyao-che@student.42kl.edu.my>    +#+  +:+       +#+        */
/*                                                +#+#+#+#+#+   +#+           */
/*   Created: 2022/04/11 17:46:15 by lyao-che          #+#    #+#             */
/*   Updated: 2022/04/12 17:47:33 by lyao-che         ###   ########.fr       */
/*                                                                            */
/* ************************************************************************** */

char	*ft_strncpy(char *dest, char *src, unsigned int n)
{
	unsigned int	counter;

	counter = 0;
	while (src[counter] != '\0' && counter < n)
	{
		dest[counter] = src[counter];
		counter++;
	}
	while (counter < n)
	{
		dest[counter] = '\0';
		counter++;
	}
	return (dest);
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
/*   Created: 2022/04/12 08:24:53 by lyao-che          #+#    #+#             */
/*   Updated: 2022/04/12 09:10:37 by lyao-che         ###   ########.fr       */
/*                                                                            */
/* ************************************************************************** */

#include <stdio.h>

int	ft_str_is_alpha(char *str);

int main(void)
{
	char alphac[] = "ABCDEFGHIJKLMNOPQRSTUVWXYZabcdefghijklmnopqrstuvwxyz";
	char specialc[] = "ABC abc áéíóú àèìòù âêîôû äëïöü \'\"(){}[]!?@#$&* wxyz WXYZ";
	char emptyc[] = "";
	char *palphac = alphac;
	char *pspecialc = specialc;
	char *pempty = emptyc;

	printf("String ONLY contains alphabet characters: 1\n");
	printf("String does not contains only alpahabet characters: 0\n");
	printf("String contains empty character: 1\n");
	printf("\nAlphabet characters: %d", ft_str_is_alpha(palphac));
	printf("\nNon-alphabet: %d", ft_str_is_alpha(pspecialc));
	printf("\nEmpty character: %d", ft_str_is_alpha(pempty));
}
```

## ft_str_is_alpha.c

```c
/* ************************************************************************** */
/*                                                                            */
/*                                                        :::      ::::::::   */
/*   ft_str_is_alpha.c                                  :+:      :+:    :+:   */
/*                                                    +:+ +:+         +:+     */
/*   By: lyao-che <lyao-che@student.42kl.edu.my>    +#+  +:+       +#+        */
/*                                                +#+#+#+#+#+   +#+           */
/*   Created: 2022/04/12 08:16:50 by lyao-che          #+#    #+#             */
/*   Updated: 2022/04/12 09:11:07 by lyao-che         ###   ########.fr       */
/*                                                                            */
/* ************************************************************************** */

int	ft_str_is_alpha(char *str)
{
	int	c;

	c = 0;
	while (str[c] != '\0')
	{
		if ((str[c] < 'A' || str[c] > 'Z') && (str[c] < 'a' || str[c] > 'z'))
			return (0);
		c++;
	}
	return (1);
}
```

## Ex03

## main.c

```c
/* ************************************************************************** */
/*                                                                            */
/*                                                        :::      ::::::::   */
/*   main.c                                             :+:      :+:    :+:   */
/*                                                    +:+ +:+         +:+     */
/*   By: lyao-che <lyao-che@student.42kl.edu.my>    +#+  +:+       +#+        */
/*                                                +#+#+#+#+#+   +#+           */
/*   Created: 2022/04/12 08:24:53 by lyao-che          #+#    #+#             */
/*   Updated: 2022/04/12 09:24:23 by lyao-che         ###   ########.fr       */
/*                                                                            */
/* ************************************************************************** */

#include <stdio.h>

int	ft_str_is_numeric(char *str);

int main(void)
{
	char numeric[] = "0123456789";
	char specialc[] = "0123456789_";
	char emptyc[] = "";
	char *pnumeric = numeric;
	char *pspecialc = specialc;
	char *pempty = emptyc;

	printf("String ONLY contains numeric characters: 1\n");
	printf("String does not contains only numeric characters: 0\n");
	printf("String contains empty character: 1\n");
	printf("\nNumeric characters: %d", ft_str_is_numeric(pnumeric));
	printf("\nNon-numeric: %d", ft_str_is_numeric(pspecialc));
	printf("\nEmpty character: %d", ft_str_is_numeric(pempty));
}
```

## ft_str_is_numeric.c

```c
/* ************************************************************************** */
/*                                                                            */
/*                                                        :::      ::::::::   */
/*   ft_str_is_numeric.c                                :+:      :+:    :+:   */
/*                                                    +:+ +:+         +:+     */
/*   By: lyao-che <lyao-che@student.42kl.edu.my>    +#+  +:+       +#+        */
/*                                                +#+#+#+#+#+   +#+           */
/*   Created: 2022/04/12 09:17:21 by lyao-che          #+#    #+#             */
/*   Updated: 2022/04/12 09:22:23 by lyao-che         ###   ########.fr       */
/*                                                                            */
/* ************************************************************************** */

int	ft_str_is_numeric(char *str)
{
	int	c;

	c = 0;
	while (str[c] != '\0')
	{
		if (str[c] < '0' || str[c] > '9')
			return (0);
		c++;
	}
	return (1);
}
```


# Ex04

## main.c

```c
/* ************************************************************************** */
/*                                                                            */
/*                                                        :::      ::::::::   */
/*   main.c                                             :+:      :+:    :+:   */
/*                                                    +:+ +:+         +:+     */
/*   By: lyao-che <lyao-che@student.42kl.edu.my>    +#+  +:+       +#+        */
/*                                                +#+#+#+#+#+   +#+           */
/*   Created: 2022/04/12 09:38:13 by lyao-che          #+#    #+#             */
/*   Updated: 2022/04/12 09:40:43 by lyao-che         ###   ########.fr       */
/*                                                                            */
/* ************************************************************************** */

#include <stdio.h>

int	ft_str_is_lowercase(char *str);

int main(void)
{
	char alphac[] = "abcdefghijklmnopqrstuvwxyz";
	char specialc[] = "ABcdefghijklmnopqrstuvwxyz_";
	char emptyc[] = "";
	char *palphac = alphac;
	char *pspecialc = specialc;
	char *pempty = emptyc;

	printf("String ONLY contains numeric characters: 1\n");
	printf("String does not contains only numeric characters: 0\n");
	printf("String contains empty character: 1\n");
	printf("\nNumeric characters: %d", ft_str_is_lowercase(palphac));
	printf("\nNon-numeric: %d", ft_str_is_lowercase(pspecialc));
	printf("\nEmpty character: %d", ft_str_is_lowercase(pempty));
}
```

## ft_str_is_lowercase.c

```c
/* ************************************************************************** */
/*                                                                            */
/*                                                        :::      ::::::::   */
/*   ft_str_is_lowercase.c                              :+:      :+:    :+:   */
/*                                                    +:+ +:+         +:+     */
/*   By: lyao-che <lyao-che@student.42kl.edu.my>    +#+  +:+       +#+        */
/*                                                +#+#+#+#+#+   +#+           */
/*   Created: 2022/04/12 09:36:55 by lyao-che          #+#    #+#             */
/*   Updated: 2022/04/12 09:41:43 by lyao-che         ###   ########.fr       */
/*                                                                            */
/* ************************************************************************** */

int	ft_str_is_lowercase(char *str)
{
	int	c;

	c = 0;
	while (str[c] != '\0')
	{
		if (str[c] < 'a' || str[c] > 'z')
			return (0);
		c++;
	}
	return (1);
}
```

# Ex05

## main.c

```c
/* ************************************************************************** */
/*                                                                            */
/*                                                        :::      ::::::::   */
/*   main.c                                             :+:      :+:    :+:   */
/*                                                    +:+ +:+         +:+     */
/*   By: lyao-che <lyao-che@student.42kl.edu.my>    +#+  +:+       +#+        */
/*                                                +#+#+#+#+#+   +#+           */
/*   Created: 2022/04/12 09:51:01 by lyao-che          #+#    #+#             */
/*   Updated: 2022/04/12 09:52:57 by lyao-che         ###   ########.fr       */
/*                                                                            */
/* ************************************************************************** */

#include <stdio.h>

int	ft_str_is_uppercase(char *str);

int main(void)
{
	char alphac[] = "ABCDEFGHIJKLMNOPQRSTUVWXYZ";
	char specialc[] = "abcdefghijklmnopqrstuvwxyz_";
	char emptyc[] = "";
	char *palphac = alphac;
	char *pspecialc = specialc;
	char *pempty = emptyc;

	printf("String ONLY contains numeric characters: 1\n");
	printf("String does not contains only numeric characters: 0\n");
	printf("String contains empty character: 1\n");
	printf("\nNumeric characters: %d", ft_str_is_uppercase(palphac));
	printf("\nNon-numeric: %d", ft_str_is_uppercase(pspecialc));
	printf("\nEmpty character: %d", ft_str_is_uppercase(pempty));
}
```

## ft_str_is_uppercase.c

```c
/* ************************************************************************** */
/*                                                                            */
/*                                                        :::      ::::::::   */
/*   ft_str_is_uppercase.c                              :+:      :+:    :+:   */
/*                                                    +:+ +:+         +:+     */
/*   By: lyao-che <lyao-che@student.42kl.edu.my>    +#+  +:+       +#+        */
/*                                                +#+#+#+#+#+   +#+           */
/*   Created: 2022/04/12 09:50:13 by lyao-che          #+#    #+#             */
/*   Updated: 2022/04/12 09:50:41 by lyao-che         ###   ########.fr       */
/*                                                                            */
/* ************************************************************************** */

int	ft_str_is_uppercase(char *str)
{
	int	c;

	c = 0;
	while (str[c] != '\0')
	{
		if (str[c] < 'A' || str[c] > 'Z')
			return (0);
		c++;
	}
	return (1);
}
```

# Ex06

## main.c

```c
/* ************************************************************************** */
/*                                                                            */
/*                                                        :::      ::::::::   */
/*   main.c                                             :+:      :+:    :+:   */
/*                                                    +:+ +:+         +:+     */
/*   By: lyao-che <lyao-che@student.42kl.edu.my>    +#+  +:+       +#+        */
/*                                                +#+#+#+#+#+   +#+           */
/*   Created: 2022/04/12 10:04:40 by lyao-che          #+#    #+#             */
/*   Updated: 2022/04/12 10:07:37 by lyao-che         ###   ########.fr       */
/*                                                                            */
/* ************************************************************************** */

#include <stdio.h>

int	ft_str_is_printable(char *str);

int main(void)
{
	char alphac[] = "printable text";
	char specialc[] = "unprintable text: \t \a ";
	char emptyc[] = "";
	char *palphac = alphac;
	char *pspecialc = specialc;
	char *pempty = emptyc;

	printf("String ONLY contains printable characters: 1\n");
	printf("String does not contains only printable characters: 0\n");
	printf("String contains empty character: 1\n");
	printf("\nNumeric characters: %d", ft_str_is_printable(palphac));
	printf("\nNon-numeric: %d", ft_str_is_printable(pspecialc));
	printf("\nEmpty character: %d", ft_str_is_printable(pempty));
}
```

## ft_str_is_printable.c

```c
/* ************************************************************************** */
/*                                                                            */
/*                                                        :::      ::::::::   */
/*   ft_str_is_printable.c                              :+:      :+:    :+:   */
/*                                                    +:+ +:+         +:+     */
/*   By: lyao-che <lyao-che@student.42kl.edu.my>    +#+  +:+       +#+        */
/*                                                +#+#+#+#+#+   +#+           */
/*   Created: 2022/04/12 10:02:59 by lyao-che          #+#    #+#             */
/*   Updated: 2022/04/12 10:04:03 by lyao-che         ###   ########.fr       */
/*                                                                            */
/* ************************************************************************** */

int	ft_str_is_printable(char *str)
{
	int	c;

	c = 0;
	while (str[c] != '\0')
	{
		if (str[c] < 32 || str[c] > 127)
			return (0);
		c++;
	}
	return (1);
}
```

# Ex07

## main.c

```c
/* ************************************************************************** */
/*                                                                            */
/*                                                        :::      ::::::::   */
/*   main.c                                             :+:      :+:    :+:   */
/*                                                    +:+ +:+         +:+     */
/*   By: lyao-che <lyao-che@student.42kl.edu.my>    +#+  +:+       +#+        */
/*                                                +#+#+#+#+#+   +#+           */
/*   Created: 2022/04/12 12:04:00 by lyao-che          #+#    #+#             */
/*   Updated: 2022/04/12 12:07:40 by lyao-che         ###   ########.fr       */
/*                                                                            */
/* ************************************************************************** */

#include <stdio.h>

char	*ft_strupcase(char *str);

int	main(void)
{
	char lowcase[] = "abcdefghijklmnopqrstuvwxyz";
	char *plowcase = lowcase;

	ft_strupcase(plowcase);
	printf("to uppercase: %s\n", plowcase);
}
```

## ft_strupcase.c

```c
/* ************************************************************************** */
/*                                                                            */
/*                                                        :::      ::::::::   */
/*   ft_strupcase.c                                     :+:      :+:    :+:   */
/*                                                    +:+ +:+         +:+     */
/*   By: lyao-che <lyao-che@student.42kl.edu.my>    +#+  +:+       +#+        */
/*                                                +#+#+#+#+#+   +#+           */
/*   Created: 2022/04/12 11:56:00 by lyao-che          #+#    #+#             */
/*   Updated: 2022/04/12 12:08:46 by lyao-che         ###   ########.fr       */
/*                                                                            */
/* ************************************************************************** */

char	*ft_strupcase(char *str)
{
	int	c;

	c = 0;
	while (str[c] != '\0')
	{
		if (str[c] >= 'a' && str[c] <= 'z')
			str[c] -= 32;
		c++;
	}
	return (str);
}
```

# Ex08

## main.c

```c
/* ************************************************************************** */
/*                                                                            */
/*                                                        :::      ::::::::   */
/*   main.c                                             :+:      :+:    :+:   */
/*                                                    +:+ +:+         +:+     */
/*   By: lyao-che <lyao-che@student.42kl.edu.my>    +#+  +:+       +#+        */
/*                                                +#+#+#+#+#+   +#+           */
/*   Created: 2022/04/12 12:20:26 by lyao-che          #+#    #+#             */
/*   Updated: 2022/04/12 12:22:35 by lyao-che         ###   ########.fr       */
/*                                                                            */
/* ************************************************************************** */

#include <stdio.h>

char	*ft_strlowcase(char *str);

int	main(void)
{
	char lowcase[] = "ABCD";
	char *plowcase = lowcase;

	ft_strlowcase(plowcase);
	printf("to lowcase: %s\n", plowcase);
}
```

## ft_strlowcase.c

```c
/* ************************************************************************** */
/*                                                                            */
/*                                                        :::      ::::::::   */
/*   ft_strlowcase.c                                    :+:      :+:    :+:   */
/*                                                    +:+ +:+         +:+     */
/*   By: lyao-che <lyao-che@student.42kl.edu.my>    +#+  +:+       +#+        */
/*                                                +#+#+#+#+#+   +#+           */
/*   Created: 2022/04/12 12:19:29 by lyao-che          #+#    #+#             */
/*   Updated: 2022/04/12 12:22:58 by lyao-che         ###   ########.fr       */
/*                                                                            */
/* ************************************************************************** */

char	*ft_strlowcase(char *str)
{
	int	c;

	c = 0;
	while (str[c] != '\0')
	{
		if (str[c] >= 'A' && str[c] <= 'Z')
			str[c] += 32;
		c++;
	}
	return (str);
}
```

# Ex09

## main.c

```c
/* ************************************************************************** */
/*                                                                            */
/*                                                        :::      ::::::::   */
/*   main.c                                             :+:      :+:    :+:   */
/*                                                    +:+ +:+         +:+     */
/*   By: lyao-che <lyao-che@student.42kl.edu.my>    +#+  +:+       +#+        */
/*                                                +#+#+#+#+#+   +#+           */
/*   Created: 2022/04/12 14:18:22 by lyao-che          #+#    #+#             */
/*   Updated: 2022/04/12 14:29:43 by lyao-che         ###   ########.fr       */
/*                                                                            */
/* ************************************************************************** */

#include <stdio.h>

char	*ft_strcapitalize(char *str);

int	main(void)
{
	char original[] = "salut, comment tu vas ? 42mots quarante-deux; cinquante+et+un";
	
	printf("Original string: %s\n", original);
	printf("Changes made: %s\n", ft_strcapitalize(original));
	return (0);
}
```

## ft_strcapatalize.c 

```c
/* ************************************************************************** */
/*                                                                            */
/*                                                        :::      ::::::::   */
/*   ft_strcapitalize.c                                 :+:      :+:    :+:   */
/*                                                    +:+ +:+         +:+     */
/*   By: lyao-che <lyao-che@student.42kl.edu.my>    +#+  +:+       +#+        */
/*                                                +#+#+#+#+#+   +#+           */
/*   Created: 2022/04/12 14:06:51 by lyao-che          #+#    #+#             */
/*   Updated: 2022/04/12 17:52:58 by lyao-che         ###   ########.fr       */
/*                                                                            */
/* ************************************************************************** */

char	*ft_strcapitalize(char *str)
{
	int	c;
	int	i;

	c = 0;
	i = 0;
	while (str[c] != '\0')
	{
		if (i == 0 && str[c] >= 'a' && str[c] <= 'z')
		{
			str[c] -= 32;
			i++;
		}
		else if (i > 0 && str[c] >= 'A' && str[c] <= 'Z')
			str[c] += 32;
		else if (i > 0 && str[c] == ' ')
			i = 0;
		else
			i++;
		c++;
	}
	return (str);
}
```