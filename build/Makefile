# Makefile

# Name of Output Executable
OUTPUT=sfml-app
# Compiler/Linker Flags
CC=g++
CFLAGS=-g -O2 -Wall -Wextra -std=c++11
LDFLAGS=-lsfml-graphics -lsfml-window -lsfml-system

# Modify these if you change the project's directory structure
ROOTDIR=../
OUTDIR=$(ROOTDIR)bin/
OBJECTDIR=$(OUTDIR)objects/
SOURCEDIR=$(ROOTDIR)src/
EXECUTABLE=$(OUTDIR)$(OUTPUT)

# Gets file paths of headers, sources, and generated objects
SOURCES:=$(wildcard $(SOURCEDIR)*.cpp)
HEADERS=$(wildcard $(SOURCEDIR)*.h)
OBJECTS=$(patsubst $(SOURCEDIR)%.cpp,$(OBJECTDIR)%.o,$(SOURCES))

all: $(OBJECTDIR) $(EXECUTABLE)

$(EXECUTABLE): $(OBJECTS) $(HEADERS)
	$(CC) -o $@ $(OBJECTS) $(LDFLAGS)

$(OBJECTDIR):
	mkdir -p $(OBJECTDIR)

$(OBJECTDIR)%.o: $(SOURCEDIR)%.cpp $(HEADERS)
	$(CC) -c -o $@ $< $(CFLAGS)

clean:
	-rm $(EXECUTABLE)
	-rm -rf $(OBJECTDIR)
# The starting - suppresses output value from rm (which fails if files don't exist)

.PHONY: all clean

# End Makefile