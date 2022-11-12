CC=gcc

INCLUDE_DIR = ./include
BUILD_DIR = ./build
SRC_DIR = ./src

HEADERS = $(shell find $(INCLUDE_DIR) -name '*.h')
SOURCES = $(shell find $(SRC_DIR) -name '*.c')
OBJ =  $(patsubst $(SRC_DIR)/%.c,$(BUILD_DIR)/%.o,$(SOURCES))

NAME = ../client.exe
RM = rm -fr

all:$(NAME)

$(NAME): $(OBJ)
	$(CC) -o $@ $^ -I$(INCLUDE_DIR)

$(BUILD_DIR)/%.o: $(SRC_DIR)/%.c $(HEADERS)
	$(CC) -c -o $@ $< $(CFLAGS)

.PHONY: clean

clean:
	$(RM) $(BUILD_DIR)/*

fclean:	clean
	$(RM) $(NAME)

debug:
	@echo "includes" $(HEADERS)
	@echo "src" $(SOURCES)
	@echo "objectos" $(OBJ)