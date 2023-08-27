# **************************************************************************** #
#                                                                              #
#                                                         :::      ::::::::    #
#    Makefile                                           :+:      :+:    :+:    #
#                                                     +:+ +:+         +:+      #
#    By: nuferron <nuferron@student.42barcel>       +#+  +:+       +#+         #
#                                                 +#+#+#+#+#+   +#+            #
#    Created: 2023/01/10 18:05:14 by nuferron          #+#    #+#              #
#    Updated: 2023/05/05 21:41:15 by nuferron         ###   ########.fr        #
#                                                                              #
# **************************************************************************** #

SRCS = ft_isalpha.c ft_isdigit.c ft_isalnum.c ft_isascii.c ft_isprint.c \
       ft_strlen.c ft_memset.c ft_bzero.c ft_memcpy.c ft_memmove.c \
	   ft_strlcpy.c ft_strlcat.c ft_toupper.c ft_tolower.c ft_strchr.c \
	   ft_strrchr.c ft_strncmp.c ft_memchr.c ft_memcmp.c ft_strnstr.c \
	   ft_atoi.c ft_calloc.c ft_strdup.c ft_substr.c ft_strjoin.c ft_strtrim.c \
	   ft_split.c ft_itoa.c ft_strmapi.c ft_striteri.c ft_putchar_fd.c \
	   ft_putstr_fd.c ft_putendl_fd.c ft_putnbr_fd.c \

SRCSBONUS = ft_lstnew_bonus.c ft_lstadd_front_bonus.c ft_lstsize_bonus.c \
			ft_lstlast_bonus.c ft_lstadd_back_bonus.c ft_lstdelone_bonus.c \
			ft_lstclear_bonus.c ft_lstiter_bonus.c ft_lstmap_bonus.c \

#aqui passem els srcs a objs canviant l'extensio de .c a .o
OBJS = ${SRCS:.c=.o}


HEADER = libft.h
NAME = libft.a
CC = cc
RM = rm -f
CFLAGS = -Wall -Wextra -Werror
OBJSBONUS = ${SRCSBONUS:.c=.o}


#quan fem una conversio de .c a .o, aqui mirem si el header ha estat modificat
%.o: %.c $(HEADER)
	${CC} ${CFLAGS} -I libft.h -c $< -o ${<:.c=.o}


all: 		${NAME}

#primer mirem si els OBJS son mes nous que el NAME; si ho son, s'executa el comando que hi ha a sota i, si no, no s'executa res.
${NAME}:	${OBJS} 
		ar rcs ${NAME} ${OBJS}
		ranlib ${NAME}

bonus:		${OBJS} ${OBJSBONUS} $(HEADER)
			ar rcs ${NAME} ${OBJS} ${OBJSBONUS}
			ranlib ${NAME}
			@touch $@
clean: 		
		${RM} ${OBJS} ${OBJSBONUS} 

fclean: 	clean
		${RM} ${NAME}
		${RM} bonus

re:		fclean all

#li especifiquem el nom de les normes que no volem que confongui amb arxius que puguin tenir el mateix nom.
.PHONY: all clean fclean re