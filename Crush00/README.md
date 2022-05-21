## main.c

```c
/* ************************************************************************** */
/*                                                                            */
/*                                                        :::      ::::::::   */
/*   main.c                                             :+:      :+:    :+:   */
/*                                                    +:+ +:+         +:+     */
/*   By: lyao-che <lyao-che@student.42kl.edu.my>    +#+  +:+       +#+        */
/*                                                +#+#+#+#+#+   +#+           */
/*   Created: 2022/04/09 07:22:42 by lyao-che          #+#    #+#             */
/*   Updated: 2022/04/09 17:34:22 by lyao-che         ###   ########.fr       */
/*                                                                            */
/* ************************************************************************** */

#include <unistd.h>

void	rush(int x, int y);

int	main(void)
{
	rush(5, 3); // x - width of the pattern, y - length of pattern
	return (0);
}
```

## ft_putchar.c

```c
/* ************************************************************************** */
/*                                                                            */
/*                                                        :::      ::::::::   */
/*   ft_putchar.c                                       :+:      :+:    :+:   */
/*                                                    +:+ +:+         +:+     */
/*   By: lyao-che <lyao-che@student.42kl.edu.my>    +#+  +:+       +#+        */
/*                                                +#+#+#+#+#+   +#+           */
/*   Created: 2022/04/09 08:21:37 by lyao-che          #+#    #+#             */
/*   Updated: 2022/04/09 08:22:34 by lyao-che         ###   ########.fr       */
/*                                                                            */
/* ************************************************************************** */

#include <unistd.h>

void	ft_putchar(char c)
{
	write(1, &c, 1);
}
```

## rush02.c 

```c
/* ************************************************************************** */
/*                                                                            */
/*                                                        :::      ::::::::   */
/*   rush02.c                                           :+:      :+:    :+:   */
/*                                                    +:+ +:+         +:+     */
/*   By: lyao-che <lyao-che@student.42kl.edu.my>    +#+  +:+       +#+        */
/*                                                +#+#+#+#+#+   +#+           */
/*   Created: 2022/04/09 09:14:30 by lyao-che          #+#    #+#             */
/*   Updated: 2022/04/09 17:33:29 by lyao-che         ###   ########.fr       */
/*                                                                            */
/* ************************************************************************** */

#include <unistd.h>

#define UPPER_CORNER 'A'  // Constant variable & unable to reassign a value later on using '='
#define LOWER_CORNER 'C'  // Constant variable & unable to reassign a value later on using '='

void	ft_putchar(char a);
void	decision(int cx, int cy, int x, int y);

void	rush(int x, int y)
{
	int	cx;
	int	cy;

	cy = 1;
	cx = 0;
	if (x <= 0 || y <= 0) // If x equal to 0 / less than 0 (-1,-2...)
		return ;
	decision(cx, cy, x, y);
}

void	decision(int cx, int cy, int x, int y)
{
	while (cy <= y)
	{
		cx = 1;
		while (cx <= x)
		{
			if ((cx == 1 && cy == 1) || (cy == 1 && cx == x))
				ft_putchar(UPPER_CORNER); // print A  -  Top Left & Right Corner
			else if ((cx == 1 && cy == y) || (cx == x && cy == y))
				ft_putchar(LOWER_CORNER); // print C -  Bottom Left & Right Corner
			else if ((cx == 1) || (cx == x) || (cy == 1) || (cy == y))
				ft_putchar('B'); // Print B for 1st & last (row & column)
			else
				ft_putchar(' '); // Print a Space in the middle
			cx++;
		}
		cy++;
		write(1, "\n", 1);
	}
}
```

## rush00.c (Bonus Q)

```c
/* ************************************************************************** */
/*                                                                            */
/*                                                        :::      ::::::::   */
/*   rush00.c                                           :+:      :+:    :+:   */
/*                                                    +:+ +:+         +:+     */
/*   By: lyao-che <lyao-che@student.42kl.edu.my>    +#+  +:+       +#+        */
/*                                                +#+#+#+#+#+   +#+           */
/*   Created: 2022/04/09 15:36:00 by lyao-che          #+#    #+#             */
/*   Updated: 2022/04/09 17:00:23 by lyao-che         ###   ########.fr       */
/*                                                                            */
/* ************************************************************************** */

#include <unistd.h>

#define CORNER 'o'  // Constant variable & unable to reassign a value later on using '='
#define HLINE '-'   // Constant variable & unable to reassign a value later on using '='
#define VLINE '|'   // Constant variable & unable to reassign a value later on using '='

void	ft_putchar(char a);
void	decision(int cx, int cy, int x, int y);

void	rush(int x, int y)
{
	int	cx;
	int	cy;

	cy = 1;
	cx = 0;
	if (x <= 0 || y <= 0)
		return ;
	decision(cx, cy, x, y);
}

void	decision(int cx, int cy, int x, int y)
{
	while (cy <= y)
	{
		cx = 1;
		while (cx <= x)
		{
			if ((cx == 1 && cy == 1) || (cx == x && cy == y))
				ft_putchar(CORNER); // print o : top corner
			else if ((cx == 1 && cy == y) || (cx == x && cy == 1))
				ft_putchar(CORNER); // print o : bottom corner
			else if (cy == 1 || cy == y)
				ft_putchar(HLINE); // print - : top middle
			else if (cx == 1 || cx == x)
				ft_putchar(VLINE); // print | : 
			else
				ft_putchar(' ');
			cx++;
		}
		cy++;
		write(1, "\n", 1);
	}
}
```

## Execute.sh

```sh
gcc -Wall -Wextra -Werror main.c rush00.c ft_putchar.c -o rush02_output00;
norminette -R CheckForbiddenSourceHeader main.c rush00.c ft_putchar.c
```


## Challenges faced
1. Understanding the pattern to printed
2. Analyzing the constant patterns & listing down in what condition need to print what pattern like 'A' / 'B' / 'C' / ' ' / 'o' / '-' / '|'
3. Convert understanding into Code
	- We break down the code by solving one pattern at the same time
4. Error: MISALIGNED_VAR_DECL  (line:  24, col:   9):    Misaligned variable declaration
	- Remove everything & rewrite the code again