IDIR =../include
CC=gcc
CFLAGS=-I$(IDIR)

ODIR=obj
LDIR =../libs

LIBS=-lm

_DEPS = #hello_world.h
DEPS = $(patsubst %,$(IDIR)/%,$(_DEPS))
   # $(patsubst pattern,replacement,text)
     #Finds whitespace-separated words in text that match pattern and replaces
     #them with replacement. "%" stands for wild card.

_OBJ = hello_world.o
OBJ = $(patsubst %,$(ODIR)/%,$(_OBJ))

# Below line will generate .o file from .c and .h file
$(ODIR)/%.o: %.c $(DEPS)
	$(CC) -c -o $@ $< $(CFLAGS)
		# -c will just generate the .o file form .c file and
		# -o $@ says put the output of the compilation int the file named on the
		#    left side of the :
		# $< is the first item in the dependencies list..


hello_world: $(OBJ)
	$(CC) -o $@ $^ $(CFLAGS) $(LIBS)
		# these special macro $@ and $^, which are the left and right side of the :


.PHONY: clean

clean:
	rm -f $(ODIR)/*.o *~ core $(INCDIR)/*~
