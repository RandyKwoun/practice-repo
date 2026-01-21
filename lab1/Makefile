CXX := g++
CXXFLAGS := -g -Wall -std=c++17

BREW_PREFIX := $(shell brew --prefix)

library.o: library.cpp
	$(CXX) $(CXXFLAGS) -c $< -o $@

test: test.cpp library.o
	$(CXX) $(CXXFLAGS) -I$(BREW_PREFIX)/include $^ -L$(BREW_PREFIX)/lib \
		-lgtest_main -lgtest -pthread -o $@

all: test

run: test
	./test

.PHONY: clean
clean:
	rm -f *.o test