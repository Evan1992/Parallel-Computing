CC1 = gcc
CC2 = mpicc
CFLAGS = -lm

all: serial mpi_data_parallelism

# $^ refer to all the dependencies, serial.c fft.o utilities.o
serial: serial.c fft.o utilities.o
	$(CC1) -o serial $^ $(CFLAGS)

mpi_data_parallelism: mpi_data_parallelism.c fft.o utilities.o
	$(CC2) -o mpi_data_parallelism $^ $(CFLAGS)

fft.o: fft.c
	$(CC1) -c fft.c

utilities.o: utilities.c
	$(CC1) -c utilities.c

clean:
	rm *.o serial mpi_data_parallelism

