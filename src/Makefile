#.SILENT: run
.PHONY: clean
IDIR =../include
BDIR := ./build
ODIR=obj
#LDIR =../lib
LIBS=-lm
CC=gcc
CFLAGS=-I$(IDIR)

_DEPS = incFile.h
DEPS = $(patsubst %,$(IDIR)/%,$(_DEPS))

_OBJ = mainFile.o incFile.o 
OBJ = $(patsubst %,$(ODIR)/%,$(_OBJ))


$(ODIR)/%.o: %.c $(DEPS)
	@$(CC) -c -o $@ $< $(CFLAGS)

$(BDIR)/mainFile: $(OBJ)
	@$(CC) -o $@ $^ $(CFLAGS) $(LIBS)


run: $(BDIR)/mainFile
	@$(BDIR)/mainFile
clean:
	rm -rf $(ODIR)/*.o $(BDIR)/*
