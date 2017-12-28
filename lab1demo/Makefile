SHLIB = libcalshared.so
STLIB = libcalstatic.a

CFLAGS = -fpic

OBJS = add.o \
       mul.o \
       sub.o \
       div.o 

all: $(SHLIB) $(STLIB)

shared: $(SHLIB)

static: $(STLIB)

$(SHLIB): $(OBJS)
	gcc -shared $(OBJS) -o $(SHLIB)

$(STLIB): $(OBJS)
	ar rcs $(STLIB) $(OBJS)

add.o: add.c add.h
	gcc -c $(CFLAGS) add.c

mul.o: mul.c mul.h
	gcc -c $(CFLAGS) mul.c

sub.o: sub.c sub.h
	gcc -c $(CFLAGS) sub.c

div.o: div.c div.h
	gcc -c $(CFLAGS) div.c

.PHONY: clean

clean:
	rm -f $(OBJS) $(SHLIB) $(STLIB)
