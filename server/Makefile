CC=gcc
CFLAGS=-I./include

CLIENT_PATH = client


OBJ_DIR=obj

HEADERS = $(shell find $(CLIENT_PATH)/include -name '*.h')
SOURCES = $(shell find $(CLIENT_PATH)/src -name '*.c')
OBJ =  $(patsubst client/src/%.c,client/build/%.o,$(SOURCES))

client.exe: $(OBJ)
	$(CC) -o $@ $^ $(CFLAGS)

client/build/%.o: client/src/%.c $(HEADERS)
	$(CC) -c -o $@ $< $(CFLAGS)

.PHONY: clean

clean:
	rm -fr $(CLIENT_PATH)/build/

debug:
	@echo "includes" $(HEADERS)
	@echo "src" $(SOURCES)
	@echo "objectos" $(OBJ)