CC=gcc
DB=lldb
EXE=caveview.exe
SRC=cave_main.c cave_mesher.c cave_parse.c cave_render.c
LIB=-lmingw32 -lSDL2main -lSDL2 -lopengl32 -lGlu32
INCLUDE=-I../..
WARNFLAGS=-Wno-int-conversion -Wno-implicit-function-declaration -Wno-incompatible-pointer-types
CFLAGS=-Wl,-subsystem,windows -m32
ARGS=#

#USER: add header/library directories here
#SDLROOT=C:/dev/SDL2/SDL2-2.0.12_mingw/x86_64-w64-mingw32
SDLROOT=C:/dev/SDL2/SDL2-2.0.12_mingw/i686-w64-mingw32
LIBINCLUDEDIR=-I$(SDLROOT)/include/SDL2
LIBDIR=-L$(SDLROOT)/lib/

make: $(EXE)
	#

$(EXE): $(SRC)
	$(CC) $(INCLUDE) $(LIBINCLUDEDIR) $(LIBDIR) $(CFLAGS) $(WARNFLAGS) $(SRC) $(LIB) -o $(EXE)

$(EXE).dSYM:
	$(CC) $(INCLUDE) $(LIBINCLUDEDIR) $(LIBDIR) $(CFLAGS) $(WARNFLAGS) -ggdb3 $(SRC) $(LIB) -o $(EXE)

run: $(EXE)
	./$(EXE)

debug: $(EXE).dSYM
	$(DB) -- ./$(EXE) $(ARGS)

build: $(EXE)
	#

builddebug: $(EXE).dSYM
	#

tags:
	ctags ./*

clean:
	if [ -f $(EXE) ];      then rm    $(EXE);      fi
	if [ -d $(EXE).dSYM ]; then rm -r $(EXE).dSYM; fi

