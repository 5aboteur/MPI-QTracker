NAME := nto1
OBJS := nto1.o

LIBDIR := ../../qtracker/lib

CC := mpicc
CFLAGS := -std=gnu99 -Wall -Wextra -Werror -pedantic -O2
EXEC := mpiexec
LDFLAGS := -lm -lpthread -L $(LIBDIR) -lmpiqtr

all: name

name:
	$(CC) $(CFLAGS) $(NAME).c $(LDFLAGS) -o $(NAME)

clean:
	rm -f $(OBJS) gnuplot_tmpdatafile* $(NAME)

run:
	$(EXEC) -np 4 ./$(NAME) 100 --eager
