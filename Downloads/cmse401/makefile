all: process 

main_process_parallel.o: main_process_parallel.c
	gcc -fopenmp -c main_process_parallel.c 

png_util.o: png_util.c
	gcc -l lpng16 -c png_util.c

process: main_process_parallel.o png_util.o
	gcc -fopenmp -o process -lm -l png16 main_process_parallel.o png_util.o

test: process 
	./process ./images/cube.png test.png

clean:
	rm *.o
	rm process 
