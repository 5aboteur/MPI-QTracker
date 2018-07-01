NAME := libmpiqtr
OBJS := dump.o gnuplot_i.o plot.o prof.o
CC := mpicc
CFLAGS := -std=gnu99 -Wall -Wextra -Werror -pedantic -O2

INCDIR := inc
SRCDIR := src

#SOURCES := $(wildcard $(SRCDIR)/*.c)
INCLUDES := -I $(INCDIR)

all: dump gnuplot plot prof pack move clean

dump:
	$(CC) $(CFLAGS) $(INCLUDES) -c $(SRCDIR)/dump.c -o dump.o

gnuplot:
	$(CC) $(CFLAGS) $(INCLUDES) -c $(SRCDIR)/gnuplot_i.c -o gnuplot_i.o

plot:
	$(CC) $(CFLAGS) $(INCLUDES) -c $(SRCDIR)/plot.c -o plot.o

prof:
	$(CC) $(CFLAGS) $(INCLUDES) -c $(SRCDIR)/prof.c -o prof.o

pack:
	ar rcs $(NAME).a $(OBJS)
	ranlib $(NAME).a

move:
	mkdir -p lib
	mv $(NAME).a lib

clean:
	rm -f *.o
