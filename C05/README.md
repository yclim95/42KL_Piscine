# Ex00

## ft_iterative_factorial.c

```c
/* ************************************************************************** */
/*                                                                            */
/*                                                        :::      ::::::::   */
/*   ft_iterative_factorial.c                           :+:      :+:    :+:   */
/*                                                    +:+ +:+         +:+     */
/*   By: lyao-che <lyao-che@student.42kl.edu.my>    +#+  +:+       +#+        */
/*                                                +#+#+#+#+#+   +#+           */
/*   Created: 2022/04/14 15:31:39 by lyao-che          #+#    #+#             */
/*   Updated: 2022/04/15 08:05:59 by lyao-che         ###   ########.fr       */
/*                                                                            */
/* ************************************************************************** */

int	ft_iterative_factorial(int nb)
{
	int	factorial;

	factorial = 1;
	if (nb < 0)
		return (0);
	else if (nb <= 1)
		return (1);
	else
	{
		while (nb > 0)
			factorial *= nb--;
	}
	return (factorial);
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
/*   Created: 2022/04/14 15:42:46 by lyao-che          #+#    #+#             */
/*   Updated: 2022/04/14 15:44:09 by lyao-che         ###   ########.fr       */
/*                                                                            */
/* ************************************************************************** */
#include <stdio.h>
int	ft_iterative_factorial(int nb);

int	main(void)
{
	int factorial = ft_iterative_factorial(6);
	printf("%d", factorial);
}
```

# Ex01

## ft_recursive_factorial.c

```c
/* ************************************************************************** */
/*                                                                            */
/*                                                        :::      ::::::::   */
/*   ft_recursive_factorial.c                           :+:      :+:    :+:   */
/*                                                    +:+ +:+         +:+     */
/*   By: lyao-che <lyao-che@student.42kl.edu.my>    +#+  +:+       +#+        */
/*                                                +#+#+#+#+#+   +#+           */
/*   Created: 2022/04/15 07:30:39 by lyao-che          #+#    #+#             */
/*   Updated: 2022/04/15 08:04:27 by lyao-che         ###   ########.fr       */
/*                                                                            */
/* ************************************************************************** */

int	ft_recursive_factorial(int nb)
{
	if (nb < 0)
		return (0);
	else if (nb <= 1)
		return (1);
	else
		return (nb * ft_recursive_factorial(nb - 1));
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
/*   Created: 2022/04/15 07:37:24 by lyao-che          #+#    #+#             */
/*   Updated: 2022/04/15 08:05:09 by lyao-che         ###   ########.fr       */
/*                                                                            */
/* ************************************************************************** */

#include <stdio.h>

int	ft_recursive_factorial(int nb);

int	main(void)
{
	int ans = ft_recursive_factorial(6);
	printf("%d\n",ans);
	return (0);
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
/*   Created: 2022/04/16 08:02:53 by lyao-che          #+#    #+#             */
/*   Updated: 2022/04/16 08:22:39 by lyao-che         ###   ########.fr       */
/*                                                                            */
/* ************************************************************************** */

#include <stdio.h>

int ft_iterative_power(int nb, int power);

int	main(void)
{
	int ans1 = ft_iterative_power(2,3);
	int ans2 = ft_iterative_power(2,-1);
	int ans3 = ft_iterative_power(2,0);
	int ans4 = ft_iterative_power(2,1);
	printf("2 power of 3: %d\n",ans1);
	printf("2 power of -1: %d\n",ans2);
	printf("2 power of 0: %d\n",ans3);
	printf("2 power of 1: %d\n",ans4);
	return (0);
}
```

## ft_iterative_power.c

```c
/* ************************************************************************** */
/*                                                                            */
/*                                                        :::      ::::::::   */
/*   ft_iterative_power.c                               :+:      :+:    :+:   */
/*                                                    +:+ +:+         +:+     */
/*   By: lyao-che <lyao-che@student.42kl.edu.my>    +#+  +:+       +#+        */
/*                                                +#+#+#+#+#+   +#+           */
/*   Created: 2022/04/16 08:00:21 by lyao-che          #+#    #+#             */
/*   Updated: 2022/04/16 08:21:20 by lyao-che         ###   ########.fr       */
/*                                                                            */
/* ************************************************************************** */

int	ft_iterative_power(int nb, int power)
{
	int	temp;

	temp = nb;
	if (power < 0)
		return (0);
	else
	{
		if (power == 0)
			return (1);
		while (power > 1)
		{
			temp *= nb;
			power--;
		}
	}
	return (temp);
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
/*   Created: 2022/04/16 08:38:29 by lyao-che          #+#    #+#             */
/*   Updated: 2022/04/16 08:40:12 by lyao-che         ###   ########.fr       */
/*                                                                            */
/* ************************************************************************** */

#include <stdio.h>

int ft_recursive_power(int nb, int power);

int	main(void)
{
	int ans1 = ft_recursive_power(2,3);
	int ans2 = ft_recursive_power(2,-1);
	int ans3 = ft_recursive_power(2,0);
	int ans4 = ft_recursive_power(2,1);
	printf("2 power of 3: %d\n",ans1);
	printf("2 power of -1: %d\n",ans2);
	printf("2 power of 0: %d\n",ans3);
	printf("2 power of 1: %d\n",ans4);
	return (0);
}
```

## ft_recursive_power.c

```c
/* ************************************************************************** */
/*                                                                            */
/*                                                        :::      ::::::::   */
/*   ft_recursive_power.c                               :+:      :+:    :+:   */
/*                                                    +:+ +:+         +:+     */
/*   By: lyao-che <lyao-che@student.42kl.edu.my>    +#+  +:+       +#+        */
/*                                                +#+#+#+#+#+   +#+           */
/*   Created: 2022/04/16 08:34:32 by lyao-che          #+#    #+#             */
/*   Updated: 2022/04/16 08:54:23 by lyao-che         ###   ########.fr       */
/*                                                                            */
/* ************************************************************************** */

int	ft_recursive_power(int nb, int power)
{
	int	temp;

	temp = nb;
	if (power < 0)
		return (0);
	else if (power == 0)
		return (1);
	else if (power > 1)
		return (temp * ft_recursive_power(temp, power - 1));
	else
		return (temp);
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
/*   Created: 2022/04/17 16:21:36 by lyao-che          #+#    #+#             */
/*   Updated: 2022/04/17 16:25:03 by lyao-che         ###   ########.fr       */
/*                                                                            */
/* ************************************************************************** */

#include <stdio.h>

int	ft_fibonacci(int index);

int	main(void)
{
	int fibonacci = ft_fibonacci(6);
	printf("%d\n", fibonacci);
	return (0);
}
```

## ft_fibonacci.c

```c
/* ************************************************************************** */
/*                                                                            */
/*                                                        :::      ::::::::   */
/*   ft_fibonacci.c                                     :+:      :+:    :+:   */
/*                                                    +:+ +:+         +:+     */
/*   By: lyao-che <lyao-che@student.42kl.edu.my>    +#+  +:+       +#+        */
/*                                                +#+#+#+#+#+   +#+           */
/*   Created: 2022/04/17 14:38:44 by lyao-che          #+#    #+#             */
/*   Updated: 2022/04/17 16:24:30 by lyao-che         ###   ########.fr       */
/*                                                                            */
/* ************************************************************************** */

int	ft_fibonacci(int index)
{
	if (index < 0) 
		return (-1);
	else if (index == 0) 
		return (0);
	else if (index == 1)
		return (1);
	else if (index > 0)
		return (ft_fibonacci(index - 1) + ft_fibonacci(index - 2));
	else
		return (-1);
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
/*   Created: 2022/04/18 07:35:40 by lyao-che          #+#    #+#             */
/*   Updated: 2022/04/20 11:20:58 by lyao-che         ###   ########.fr       */
/*                                                                            */
/* ************************************************************************** */
#include <stdio.h>
int	ft_sqrt(int nb);

int	main(void)
{
	int negative = ft_sqrt(-1);
	int positive = ft_sqrt(1);
	int rational_num = ft_sqrt(4);
	int irrational_num = ft_sqrt(2);
	int max_num = ft_sqrt(46340);
	printf("negative num: %d\n", negative);
	printf("positive num: %d\n", positive);
	printf("rational num: %d\n", rational_num);
	printf("irrational num: %d\n", irrational_num);
	printf("Maximum num: %d\n", max_num);
	return (0);
}
```

## ft_sqrt.c

```c
/* ************************************************************************** */
/*                                                                            */
/*                                                        :::      ::::::::   */
/*   ft_sqrt.c                                          :+:      :+:    :+:   */
/*                                                    +:+ +:+         +:+     */
/*   By: lyao-che <lyao-che@student.42kl.edu.my>    +#+  +:+       +#+        */
/*                                                +#+#+#+#+#+   +#+           */
/*   Created: 2022/04/18 07:24:41 by lyao-che          #+#    #+#             */
/*   Updated: 2022/04/20 11:16:28 by lyao-che         ###   ########.fr       */
/*                                                                            */
/* ************************************************************************** */

int	ft_sqrt(int nb)
{
	int	c;

	c = 1;
	if (nb == 0)
		return (0);
	while ((c * c) < nb && nb < 46341)
		c++;
	if ((c * c) == nb)
		return (c);
	else
		return (0);
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
/*   Created: 2022/04/18 08:03:43 by lyao-che          #+#    #+#             */
/*   Updated: 2022/04/18 08:08:30 by lyao-che         ###   ########.fr       */
/*                                                                            */
/* ************************************************************************** */

#include <stdio.h>

int	ft_is_prime(int nb);

int	main(void)
{
	int zero = ft_is_prime(0);
	int negative = ft_is_prime(-1);
	int isprime = ft_is_prime(2);
	int isnotprime = ft_is_prime(4);
	printf("zero: %d\n",zero);
	printf("negative: %d\n",negative);
	printf("is prime: %d\n",isprime);
	printf("is not prime: %d\n",isnotprime);
	return (0);
}
```

## ft_is_prime.c

```c
/* ************************************************************************** */
/*                                                                            */
/*                                                        :::      ::::::::   */
/*   ft_is_prime.c                                      :+:      :+:    :+:   */
/*                                                    +:+ +:+         +:+     */
/*   By: lyao-che <lyao-che@student.42kl.edu.my>    +#+  +:+       +#+        */
/*                                                +#+#+#+#+#+   +#+           */
/*   Created: 2022/04/18 08:00:52 by lyao-che          #+#    #+#             */
/*   Updated: 2022/04/18 08:10:22 by lyao-che         ###   ########.fr       */
/*                                                                            */
/* ************************************************************************** */

int	ft_is_prime(int nb)
{
	int	i;

	i = 2;
	if (nb <= 1)
		return (0);
	while (i <= (nb / i))
	{
		if (nb % i == 0)
			return (0);
		i++;
	}
	return (1);
}
```