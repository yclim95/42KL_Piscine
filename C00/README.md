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
/*   Created: 2022/04/11 07:29:09 by lyao-che          #+#    #+#             */
/*   Updated: 2022/04/11 07:29:48 by lyao-che         ###   ########.fr       */
/*                                                                            */
/* ************************************************************************** */

/* ************************************************************************** */
/*                                                                            */
/*                                                        :::      ::::::::   */
/*   ft_putchar.c                                       :+:      :+:    :+:   */
/*                                                    +:+ +:+         +:+     */
/*   By: YC <lyao-che@student.42kl.edu.my>      +#+  +:+       +#+        */
/*                                                +#+#+#+#+#+   +#+           */
/*   Created: 07/04/2022 07:10:15 by YC           #+#    #+#             */
/*   Updated: 07/04/2022 09:41:38 by YC          ###   ########.fr       */
/*                                                                            */
/* ************************************************************************** */

#include <unistd.h>

void	ft_putchar(char c);

int	main(void)
{
	ft_putchar('c');
	return (0);
}
```

## ft_purchar.c

```c
/* ************************************************************************** */
/*                                                                            */
/*                                                        :::      ::::::::   */
/*   ft_putchar.c                                       :+:      :+:    :+:   */
/*                                                    +:+ +:+         +:+     */
/*   By: YC <lyao-che@student.42kl.edu.my>      +#+  +:+       +#+        */
/*                                                +#+#+#+#+#+   +#+           */
/*   Created: 07/04/2022 07:10:15 by YC           #+#    #+#             */
/*   Updated: 2022/04/11 07:32:28 by lyao-che         ###   ########.fr       */
/*                                                                            */
/* ************************************************************************** */

#include <unistd.h>

void	ft_putchar(char c)
{
	write(1, &c, 1);
}
```

# Ex01

## ft_print_alphabet.c

```c
/* ************************************************************************** */
/*                                                                            */
/*                                                        :::      ::::::::   */
/*   ft_print_alphabet.c                                :+:      :+:    :+:   */
/*                                                    +:+ +:+         +:+     */
/*   By: YC <lyao-che@student.42kl.edu.my>      +#+  +:+       +#+        */
/*                                                +#+#+#+#+#+   +#+           */
/*   Created: 07/04/2022 07:10:15 by YC           #+#    #+#             */
/*   Updated: 2022/04/11 07:51:44 by lyao-che         ###   ########.fr       */
/*                                                                            */
/* ************************************************************************** */

#include <unistd.h>

void	ft_print_alphabet(void)
{
	char	alphabet;

	alphabet = 'a';
	while (alphabet <= 'z')
	{
		write(1, &alphabet, 1);
		alphabet++;
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
/*   Created: 2022/04/11 07:48:09 by lyao-che          #+#    #+#             */
/*   Updated: 2022/04/11 07:48:24 by lyao-che         ###   ########.fr       */
/*                                                                            */
/* ************************************************************************** */

#include <unistd.h>

void	ft_print_alphabet(void);

int	main(void)
{
	ft_print_alphabet();
	return (0);
}
```


# Ex02

## ft_print_reverse_alphabet.c

```c
/* ************************************************************************** */
/*                                                                            */
/*                                                        :::      ::::::::   */
/*   ft_print_reverse_alphabet.c                        :+:      :+:    :+:   */
/*                                                    +:+ +:+         +:+     */
/*   By: YC <lyao-che@student.42kl.edu.my>      +#+  +:+       +#+        */
/*                                                +#+#+#+#+#+   +#+           */
/*   Created: 07/04/2022 07:10:15 by YC           #+#    #+#             */
/*   Updated: 2022/04/11 07:54:32 by lyao-che         ###   ########.fr       */
/*                                                                            */
/* ************************************************************************** */

#include <unistd.h>

void	ft_print_reverse_alphabet(void)
{
	char	alphabet;

	alphabet = 'z';
	while (alphabet >= 'a')
	{
		write(1, &alphabet, 1);
		alphabet--;
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
/*   Created: 2022/04/11 07:53:32 by lyao-che          #+#    #+#             */
/*   Updated: 2022/04/11 07:54:55 by lyao-che         ###   ########.fr       */
/*                                                                            */
/* ************************************************************************** */

#include <unistd.h>

void	ft_print_reverse_alphabet(void);

int	main(void)
{
	ft_print_reverse_alphabet();
	return (0);
}
```


# Ex03

## ft_print_numbers.c

```c
/* ************************************************************************** */
/*                                                                            */
/*                                                        :::      ::::::::   */
/*   ft_print_numbers.c                                 :+:      :+:    :+:   */
/*                                                    +:+ +:+         +:+     */
/*   By: YC <lyao-che@student.42kl.edu.my>      +#+  +:+       +#+        */
/*                                                +#+#+#+#+#+   +#+           */
/*   Created: 07/04/2022 07:10:15 by YC           #+#    #+#             */
/*   Updated: 2022/04/11 07:57:23 by lyao-che         ###   ########.fr       */
/*                                                                            */
/* ************************************************************************** */

#include <unistd.h>

void	ft_print_numbers(void)
{
	char	num;

	num = '0';
	while (num <= '9')
	{
		write(1, &num, 1);
		num++;
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
/*   Created: 2022/04/11 07:57:26 by lyao-che          #+#    #+#             */
/*   Updated: 2022/04/11 07:57:34 by lyao-che         ###   ########.fr       */
/*                                                                            */
/* ************************************************************************** */

#include <unistd.h>

void	ft_print_numbers(void);

int	main(void)
{
	ft_print_numbers();
	return (0);
}
```


# Ex04

## ft_is_negative.c

```c
/* ************************************************************************** */
/*                                                                            */
/*                                                        :::      ::::::::   */
/*   ft_is_negative.c                                   :+:      :+:    :+:   */
/*                                                    +:+ +:+         +:+     */
/*   By: YC <lyao-che@student.42kl.edu.my>      +#+  +:+       +#+        */
/*                                                +#+#+#+#+#+   +#+           */
/*   Created: 07/04/2022 07:10:15 by YC           #+#    #+#             */
/*   Updated: 2022/04/11 08:02:54 by lyao-che         ###   ########.fr       */
/*                                                                            */
/* ************************************************************************** */

#include <unistd.h>

void	ft_is_negative(int n)
{
	char	positive;
	char	negative;

	positive = 'P';
	negative = 'N';
	if (n >= 0)
	{
		write(1, &positive, 1);
	}
	else
	{
		write(1, &negative, 1);
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
/*   Created: 2022/04/11 07:59:36 by lyao-che          #+#    #+#             */
/*   Updated: 2022/04/11 08:04:04 by lyao-che         ###   ########.fr       */
/*                                                                            */
/* ************************************************************************** */

#include <unistd.h>

void	ft_is_negative(int n);

int	main(void)
{
	ft_is_negative(-2);
	ft_is_negative(2);
	ft_is_negative(0);
	return (0);
}
```


# Ex05

## ft_print_comb.c

```c
/* ************************************************************************** */
/*                                                                            */
/*                                                        :::      ::::::::   */
/*   ft_print_comb.c                                    :+:      :+:    :+:   */
/*                                                    +:+ +:+         +:+     */
/*   By: YC <lyao-che@student.42kl.edu.my>      +#+  +:+       +#+        */
/*                                                +#+#+#+#+#+   +#+           */
/*   Created: 07/04/2022 07:10:15 by YC           #+#    #+#             */
/*   Updated: 2022/04/11 08:16:39 by lyao-che         ###   ########.fr       */
/*                                                                            */
/* ************************************************************************** */

#include <unistd.h>

void	write_3num(char comb1, char comb2, char comb3)
{
	write(1, &comb1, 1);
	write(1, &comb2, 1);
	write(1, &comb3, 1);
	if (comb1 != '7' || comb2 != '8' || comb3 != '9')
	{
		write(1, ", ", 2);
	}
}

void	ft_print_comb(void)
{
	char	comb1;
	char	comb2;
	char	comb3;

	comb1 = '0';
	while (comb1 <= '7')
	{
		comb2 = comb1 + 1;
		while (comb2 <= '8')
		{
			comb3 = comb2 + 1;
			while (comb3 <= '9')
			{
				write_3num(comb1, comb2, comb3);
				comb3++;
			}
			comb2++;
		}
		comb1++;
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
/*   Created: 2022/04/11 08:12:55 by lyao-che          #+#    #+#             */
/*   Updated: 2022/04/11 08:13:05 by lyao-che         ###   ########.fr       */
/*                                                                            */
/* ************************************************************************** */

#include <unistd.h>

void	ft_print_comb(void);

int	main(void)
{
	ft_print_comb();
	return (0);
}
```


# Ex06

## ft_print_comb2.c

```c
/* ************************************************************************** */
/*                                                                            */
/*                                                        :::      ::::::::   */
/*   ft_print_comb2.c                                   :+:      :+:    :+:   */
/*                                                    +:+ +:+         +:+     */
/*   By: YC <lyao-che@student.42kl.edu.my>      +#+  +:+       +#+        */
/*                                                +#+#+#+#+#+   +#+           */
/*   Created: 07/04/2022 07:10:15 by YC           #+#    #+#             */
/*   Updated: 2022/04/11 08:23:58 by lyao-che         ###   ########.fr       */
/*                                                                            */
/* ************************************************************************** */

#include <unistd.h>

void	ft_putchar(char c)
{
	write(1, &c, 1);
}

void	ft_print_comb2(void)
{
	int	num;
	int	counter;

	num = 0;
	counter = 0;
	while (num < 100)
	{
		counter = num + 1;
		while (counter < 100)
		{
			ft_putchar(num / 10 + '0');
			ft_putchar(num % 10 + '0');
			ft_putchar(' ');
			ft_putchar(counter / 10 + '0');
			ft_putchar(counter % 10 + '0');
			if ((num / 10 != 9) || (num % 10 != 8))
			{
				ft_putchar(',');
				ft_putchar(' ');
			}
			counter++;
		}
		num++;
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
/*   Created: 2022/04/11 08:23:27 by lyao-che          #+#    #+#             */
/*   Updated: 2022/04/11 08:23:31 by lyao-che         ###   ########.fr       */
/*                                                                            */
/* ************************************************************************** */

#include <unistd.h>

void	ft_print_comb2(void);

int	main(void)
{
	ft_print_comb2();
	return (0);
}
```