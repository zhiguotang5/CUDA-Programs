################################################################################
# Simple MakeFile for examples for the book Programming in Parallel with CUDA
# Note customised files for each example are not provided
# please use "make build NAME=gpusum" etc. to provide program names as necessary
#
# This Makefile is for C++ only
################################################################################

# default program name. Note use command line option NAME=... as neceessary
NAME := defaultname

# change these to match your installation
CUDA_PATH := /usr/local/cuda-11.8
# assumes CUDA samles installed in ~/samples
NVCUDASAMPLES_ROOT := ~/samples/cuda-samples/Common
# assumes examples installed in directory ~/CudaBook 
CX_ROOT := ~/Projects/CUDA-Programs/include


# Target rules
all: build

build: $(NAME)

$(NAME): $(NAME).o 
	g++ -o $(NAME)  $(NAME).o
	cp $(NAME) ../../Linux/
	
$(NAME).o: $(NAME).cpp
	g++ -c -O2 -I $(CX_ROOT) -I $(NVCUDASAMPLES_ROOT) $(NAME).cpp
    
run: build
	$(EXEC) ./$(NAME)

testrun: build

clean:
	rm -f    $(NAME) $(NAME).o
	rm -rf ../../Linux/$(NAME)
echo:
	$(info NAME is $(NAME))
#
