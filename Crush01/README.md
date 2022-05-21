## main.c

```c
/* ************************************************************************** */
/*                                                                            */
/*                                                        :::      ::::::::   */
/*   main.c                                             :+:      :+:    :+:   */
/*                                                    +:+ +:+         +:+     */
/*   By: lyao-che <lyao-che@student.42kl.edu.my>    +#+  +:+       +#+        */
/*                                                +#+#+#+#+#+   +#+           */
/*   Created: 2022/04/16 07:43:37 by lyao-che          #+#    #+#             */
/*   Updated: 2022/04/17 11:12:39 by lyao-che         ###   ########.fr       */
/*                                                                            */
/* ************************************************************************** */

#include "header.h"

int	main(int argc, char*argv[])
{
	int	**puzzle;

	puzzle = NULL;
	if (argc == 1 || argc > 2)
		write (1, "Error\n", 7);
	if (argc == 2)
	{
		execute(argv, puzzle);
	}
	return (0);
}

int	**ft_create_puzzle(char **argv)
{
	int	**puzzle;
	int	i;
	int	j;

	i = 0;
	j = 0;
	puzzle = (int **)malloc(ROW_NUM * sizeof(int *));
	if (puzzle == NULL)
		exit(0);
	while (i < ROW_NUM)
	{
		puzzle[i] = (int *)malloc(COL_NUM * sizeof(int));
		if (argv[i] == NULL)
		{
			write(1, "Reserving space\n", 16);
		}
		i++;
	}
	i = 0;
	puzzle = ft_assign_puzzle(i, j, puzzle);
	return (puzzle);
}

void	ft_print_puzzle(int **puzzle)
{
	int	i;
	int	j;

	i = 0;
	j = 0;
	while (i < ROW_NUM)
	{
		j = 0;
		while (j < COL_NUM)
		{
			ft_convert_char_to_num(puzzle[i][j]);
			ft_putchar(' ');
			j++;
		}
		ft_putchar('\n');
		i++;
	}
}

void	execute(char **argv, int **puzzle)
{
	if ((ft_strlen(argv) % 4 == 0))
	{
		if (ft_checknum(argv))
		{
			puzzle = ft_create_puzzle(argv);
			if (puzzle != NULL)
			{
				ft_print_puzzle(puzzle);
				ft_free_memory(puzzle);
			}
		}
		else
			write(1, "Please enter in number format\n", 29);
	}
	else
		write(1, "Invalid dimension\n", 18);
}

int	**ft_assign_puzzle(int row_counter, int col_counter, int **puzzle)
{
	while (row_counter < ROW_NUM)
	{
		col_counter = 0;
		while (col_counter < COL_NUM)
		{
			puzzle[row_counter][col_counter] = 0;
			col_counter++;
		}
		row_counter++;
	}
	return (puzzle);
}
```

## extra.c

```c
/* ************************************************************************** */
/*                                                                            */
/*                                                        :::      ::::::::   */
/*   extra.c                                            :+:      :+:    :+:   */
/*                                                    +:+ +:+         +:+     */
/*   By: lyao-che <lyao-che@student.42kl.edu.my>    +#+  +:+       +#+        */
/*                                                +#+#+#+#+#+   +#+           */
/*   Created: 2022/04/17 09:33:51 by lyao-che          #+#    #+#             */
/*   Updated: 2022/04/17 11:05:47 by lyao-che         ###   ########.fr       */
/*                                                                            */
/* ************************************************************************** */

#include "header.h"

void	ft_putchar(char c)
{
	write(1, &c, 1);
}

void	ft_convert_char_to_num(int nb)
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
		ft_convert_char_to_num(nb / 10);
	ft_convert_char_to_num(nb % 10);
}

int	ft_strlen(char **argv)
{
	int	i;

	i = 0;
	while (argv[1][i] != '\0')
		i++;
	return (i);
}

int	ft_checknum(char **argv)
{
	int	i;
	int	valid;

	i = 0;
	valid = 0;
	while (argv[1][i] != '\0')
	{
		if (argv[1][i] >= '0' && argv[1][i] <= '9')
			valid = 1;
		else
			valid = 0;
		i++;
	}
	return (valid);
}

void	ft_free_memory(int **puzzle)
{
	int	i;

	i = 0;
	while (i < ROW_NUM)
	{
		free(puzzle[i]);
		i++;
	}
	free(puzzle);
}
```

## header.h

```c
/* ************************************************************************** */
/*                                                                            */
/*                                                        :::      ::::::::   */
/*   header.h                                           :+:      :+:    :+:   */
/*                                                    +:+ +:+         +:+     */
/*   By: lyao-che <lyao-che@student.42kl.edu.my>    +#+  +:+       +#+        */
/*                                                +#+#+#+#+#+   +#+           */
/*   Created: 2022/04/17 10:07:26 by lyao-che          #+#    #+#             */
/*   Updated: 2022/04/17 11:32:47 by lyao-che         ###   ########.fr       */
/*                                                                            */
/* ************************************************************************** */

#ifndef HEADER_H
# define HEADER_H
# include <unistd.h>
# include <stdlib.h>

# define ROW_NUM 4
# define COL_NUM 4

void	ft_putchar(char c);
void	ft_convert_char_to_num(int nb);
int		**ft_create_puzzle(char **argv);
void	ft_print_puzzle(int **puzzle);
void	ft_free_memory(int **puzzle);
int		ft_strlen(char **argv);
int		ft_checknum(char **argv);
void	execute(char **argv, int **puzzle);
int		**ft_assign_puzzle(int row_counter, int col_counter, int **puzzle);

#endif
```