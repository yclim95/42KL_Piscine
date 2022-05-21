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
/*   Created: 2022/04/11 09:00:00 by lyao-che          #+#    #+#             */
/*   Updated: 2022/04/11 09:11:52 by lyao-che         ###   ########.fr       */
/*                                                                            */
/* ************************************************************************** */

#include <stdio.h>

void	ft_ft(int *nbr);

int	main(void)
{
	int	*nbr;
	int	integer;

	integer = 24;
	nbr = &integer;
	ft_ft(nbr);
	printf("%d\n", integer);
	return (0);
}
```

## ft_ft.c 
```c
/* ************************************************************************** */
/*                                                                            */
/*                                                        :::      ::::::::   */
/*   ft_ft.c                                            :+:      :+:    :+:   */
/*                                                    +:+ +:+         +:+     */
/*   By: lyao-che <lyao-che@student.42kl.edu.my>    +#+  +:+       +#+        */
/*                                                +#+#+#+#+#+   +#+           */
/*   Created: 2022/04/11 09:02:50 by lyao-che          #+#    #+#             */
/*   Updated: 2022/04/11 09:03:46 by lyao-che         ###   ########.fr       */
/*                                                                            */
/* ************************************************************************** */

void	ft_ft(int *nbr)
{
	*nbr = 42;
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
/*   Created: 2022/04/11 09:35:12 by lyao-che          #+#    #+#             */
/*   Updated: 2022/04/11 10:49:03 by lyao-che         ###   ########.fr       */
/*                                                                            */
/* ************************************************************************** */

#include <stdio.h>

void	ft_ultimate_ft(int *********nbr);

int	main(void)
{
	int	*********pnbr;
	int	********pnbr2;
	int	*******pnbr3;
	int	******pnbr4;
	int	*****pnbr5;
	int	****pnbr6;
	int	***pnbr7;
	int	**pnbr8;
	int	*pnbr9;
	int	nbr;

	nbr = 24;
	pnbr9 = &nbr;
	pnbr8 = &pnbr9;
	pnbr7 = &pnbr8;
	pnbr6 = &pnbr7;
	pnbr5 = &pnbr6;
	pnbr4 = &pnbr5;
	pnbr3 = &pnbr4;
	pnbr2 = &pnbr3;
	pnbr = &pnbr2;

	printf("%d\n", nbr);
	ft_ultimate_ft(pnbr);
	printf("%d\n", nbr);
}
```

## ft_print_comb.c
```c
/* ************************************************************************** */
/*                                                                            */
/*                                                        :::      ::::::::   */
/*   ft_ultimate_ft.c                                   :+:      :+:    :+:   */
/*                                                    +:+ +:+         +:+     */
/*   By: lyao-che <lyao-che@student.42kl.edu.my>    +#+  +:+       +#+        */
/*                                                +#+#+#+#+#+   +#+           */
/*   Created: 2022/04/11 09:30:26 by lyao-che          #+#    #+#             */
/*   Updated: 2022/04/11 09:34:33 by lyao-che         ###   ########.fr       */
/*                                                                            */
/* ************************************************************************** */

void	ft_ultimate_ft(int *********nbr)
{
	*********nbr = 42;
}
```

# Excercise 02

## main.c
```c
/* ************************************************************************** */
/*                                                                            */
/*                                                        :::      ::::::::   */
/*   main.c                                             :+:      :+:    :+:   */
/*                                                    +:+ +:+         +:+     */
/*   By: lyao-che <lyao-che@student.42kl.edu.my>    +#+  +:+       +#+        */
/*                                                +#+#+#+#+#+   +#+           */
/*   Created: 2022/04/11 11:03:47 by lyao-che          #+#    #+#             */
/*   Updated: 2022/04/11 11:18:35 by lyao-che         ###   ########.fr       */
/*                                                                            */
/* ************************************************************************** */

#include <stdio.h>

void	ft_swap(int *a, int *b);

int	main(void)
{
	int	tempa;
	int	tempb;
	int	*pa;
	int	*pb;

	tempa = 24;
	tempb = 42;
	pa = &tempa;
	pb = &tempb;
	ft_swap(pa, pb);
	printf("pa should be 42: %d\n", *pa);
	printf("pb should be 24: %d\n", *pb);
}
```

## ft_swap.c

```c
/* ************************************************************************** */
/*                                                                            */
/*                                                        :::      ::::::::   */
/*   ft_swap.c                                          :+:      :+:    :+:   */
/*                                                    +:+ +:+         +:+     */
/*   By: lyao-che <lyao-che@student.42kl.edu.my>    +#+  +:+       +#+        */
/*                                                +#+#+#+#+#+   +#+           */
/*   Created: 2022/04/11 11:01:50 by lyao-che          #+#    #+#             */
/*   Updated: 2022/04/11 11:19:10 by lyao-che         ###   ########.fr       */
/*                                                                            */
/* ************************************************************************** */

#include <stdio.h>

void	ft_swap(int *a, int *b)
{
	int	temp;

	temp = *b;
	*b = *a;
	*a = temp;
}
```

# Ex03

```c
/* ************************************************************************** */
/*                                                                            */
/*                                                        :::      ::::::::   */
/*   main.c                                             :+:      :+:    :+:   */
/*                                                    +:+ +:+         +:+     */
/*   By: lyao-che <lyao-che@student.42kl.edu.my>    +#+  +:+       +#+        */
/*                                                +#+#+#+#+#+   +#+           */
/*   Created: 2022/04/11 12:50:58 by lyao-che          #+#    #+#             */
/*   Updated: 2022/04/11 13:12:44 by lyao-che         ###   ########.fr       */
/*                                                                            */
/* ************************************************************************** */

#include <stdio.h>

void	ft_div_mod(int a, int b, int *div, int *mod);

int	main(void)
{
	int	a = 15;
	int	b = 2;
	int	*div = &a;
	int	*mod = &b;

	ft_div_mod(a, b, div, mod);
	printf("a: %d\n", a);
	printf("b: %d\n", b);
	printf ("a/b: %d\n", *div);
	printf("a\%%b: %d\n", *mod);
}
```

## ft_div_mod.c

```c
/* ************************************************************************** */
/*                                                                            */
/*                                                        :::      ::::::::   */
/*   ft_div_mod.c                                       :+:      :+:    :+:   */
/*                                                    +:+ +:+         +:+     */
/*   By: lyao-che <lyao-che@student.42kl.edu.my>    +#+  +:+       +#+        */
/*                                                +#+#+#+#+#+   +#+           */
/*   Created: 2022/04/11 12:11:30 by lyao-che          #+#    #+#             */
/*   Updated: 2022/04/11 12:50:49 by lyao-che         ###   ########.fr       */
/*                                                                            */
/* ************************************************************************** */

void	ft_div_mod(int a, int b, int *div, int *mod)
{
	if (b != 0)
	{
		*div = a / b;
		*mod = a % b;
	}
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
/*   Created: 2022/04/11 14:31:03 by lyao-che          #+#    #+#             */
/*   Updated: 2022/04/12 09:02:36 by lyao-che         ###   ########.fr       */
/*                                                                            */
/* ************************************************************************** */

#include <stdio.h>

void	ft_ultimate_div_mod(int *a, int *b);

int	main(void)
{
	int tempa = 20;
	int tempb = 50;
	int *a = &tempa;
	int *b = &tempb;

	ft_ultimate_div_mod(a,b);

	printf("*a / *b: %d\n", *a);
	printf("*a %% *b: %d\n", *b);
}
```

## ft_ultimate_div_mod.c

```c
/* ************************************************************************** */
/*                                                                            */
/*                                                        :::      ::::::::   */
/*   ft_ultimate_div_mod.c                              :+:      :+:    :+:   */
/*                                                    +:+ +:+         +:+     */
/*   By: lyao-che <lyao-che@student.42kl.edu.my>    +#+  +:+       +#+        */
/*                                                +#+#+#+#+#+   +#+           */
/*   Created: 2022/04/11 14:26:47 by lyao-che          #+#    #+#             */
/*   Updated: 2022/04/12 09:00:15 by lyao-che         ###   ########.fr       */
/*                                                                            */
/* ************************************************************************** */

void	ft_ultimate_div_mod(int *a, int *b)
{
	int	tempa;
	int	tempb;

	if (*b != 0)
	{
		tempa = *a / *b;
		tempb = *a % *b;
		*a = tempa;
		*b = tempb;
	}
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
/*   Created: 2022/04/11 16:47:23 by lyao-che          #+#    #+#             */
/*   Updated: 2022/04/11 16:57:56 by lyao-che         ###   ########.fr       */
/*                                                                            */
/* ************************************************************************** */

void	ft_putstr(char *str);

int	main(void)
{
	char tempS [] = "42 KL";
	char *pTempS = tempS;

	ft_putstr(pTempS);
}
```

## ft_putstr.c

```c
/* ************************************************************************** */
/*                                                                            */
/*                                                        :::      ::::::::   */
/*   ft_putstr.c                                        :+:      :+:    :+:   */
/*                                                    +:+ +:+         +:+     */
/*   By: lyao-che <lyao-che@student.42kl.edu.my>    +#+  +:+       +#+        */
/*                                                +#+#+#+#+#+   +#+           */
/*   Created: 2022/04/11 16:27:16 by lyao-che          #+#    #+#             */
/*   Updated: 2022/04/11 16:56:16 by lyao-che         ###   ########.fr       */
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
/*   Created: 2022/04/11 17:19:55 by lyao-che          #+#    #+#             */
/*   Updated: 2022/04/11 17:22:52 by lyao-che         ###   ########.fr       */
/*                                                                            */
/* ************************************************************************** */

#include <stdio.h>

int	ft_strlen(char *str);

int main(void)
{
	char testS [] = "Hello 42 KL";

	int count = ft_strlen(testS);
	printf("The number of characters is: %d", count);
}
```

## ft_strlen.c

```c
/* ************************************************************************** */
/*                                                                            */
/*                                                        :::      ::::::::   */
/*   ft_strlen.c                                        :+:      :+:    :+:   */
/*                                                    +:+ +:+         +:+     */
/*   By: lyao-che <lyao-che@student.42kl.edu.my>    +#+  +:+       +#+        */
/*                                                +#+#+#+#+#+   +#+           */
/*   Created: 2022/04/11 17:16:29 by lyao-che          #+#    #+#             */
/*   Updated: 2022/04/11 17:19:47 by lyao-che         ###   ########.fr       */
/*                                                                            */
/* ************************************************************************** */

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
```