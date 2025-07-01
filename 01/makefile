# Makefile for C program debugging
# Author: User
# Date: $(shell date)

# Compiler and flags
CC = gcc
CFLAGS = -Wall -Wextra -std=c99
DEBUG_FLAGS = -g -DDEBUG
RELEASE_FLAGS = -O2 -DNDEBUG

# Source and target files
SRC = hello.c
DEBUG_TARGET = hello_debug
RELEASE_TARGET = hello_release

# Default target
all: debug

# Debug build with debugging symbols
debug: $(DEBUG_TARGET)

$(DEBUG_TARGET): $(SRC)
	$(CC) $(CFLAGS) $(DEBUG_FLAGS) -o $(DEBUG_TARGET) $(SRC)
	@echo "Debug build completed: $(DEBUG_TARGET)"

# Release build with optimizations
release: $(RELEASE_TARGET)

$(RELEASE_TARGET): $(SRC)
	$(CC) $(CFLAGS) $(RELEASE_FLAGS) -o $(RELEASE_TARGET) $(SRC)
	@echo "Release build completed: $(RELEASE_TARGET)"

# Run the debug version
run-debug: debug
	./$(DEBUG_TARGET)

# Run the release version
run-release: release
	./$(RELEASE_TARGET)

# Debug with GDB (if available)
gdb-debug: debug
	gdb ./$(DEBUG_TARGET)

# Debug with LLDB (macOS default)
lldb-debug: debug
	lldb ./$(DEBUG_TARGET)

# Clean build artifacts
clean:
	rm -f $(DEBUG_TARGET) $(RELEASE_TARGET) a.out
	rm -rf *.dSYM
	@echo "Clean completed"

# Show help
help:
	@echo "Available targets:"
	@echo "  debug      - Build with debug symbols (default)"
	@echo "  release    - Build optimized release version"
	@echo "  run-debug  - Build and run debug version"
	@echo "  run-release- Build and run release version"
	@echo "  gdb-debug  - Build and start GDB debugger"
	@echo "  lldb-debug - Build and start LLDB debugger"
	@echo "  clean      - Remove all build artifacts"
	@echo "  help       - Show this help message"

# Phony targets
.PHONY: all debug release run-debug run-release gdb-debug lldb-debug clean help
