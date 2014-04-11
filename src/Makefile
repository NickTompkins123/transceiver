CC=gcc
CFLAGS=-Wall -Werror -g -Wextra -Wno-unused-parameter

all: gpio.o bits.o spi.o bang_registers.o strobe.o status_byte.o xosc.o freq_synth_config.o chip_reset.o simulate

simulate: gpio.h bits.h spi.h bang_registers.h strobe.h status_byte.h xosc.h freq_synth_config.h chip_reset.h simulate.c
	$(CC) gpio.o bits.o spi.o bang_registers.o strobe.o simulate.c -o simulate

gpio.o: gpio.h gpio.c
	$(CC) $(CFLAGS) -c gpio.c

bits.o: bits.h bits.c
	$(CC) $(CFLAGS) -c bits.c

spi.o: gpio.h bits.h spi.h spi.c
	$(CC) $(CFLAGS) -c spi.c

bang_registers.o: bits.h spi.h bang_registers.h bang_registers.c
	$(CC) $(CFLAGS) -c bang_registers.c

strobe.o: bits.h spi.h strobe.h strobe.c
	$(CC) $(CFLAGS) -c strobe.c

status_byte.o: bits.h bang_registers.h status_byte.h status_byte.c
	$(CC) $(CFLAGS) -c status_byte.c

xosc.o: bits.h bang_registers.h xosc.h xosc.c
	$(CC) $(CFLAGS) -c xosc.c

freq_synth_config.o: bits.h bang_registers.h freq_synth_config.h freq_synth_config.c
	$(CC) $(CFLAGS) -c freq_synth_config.c

chip_reset.o: strobe.h chip_reset.h chip_reset.c
	$(CC) $(CFLAGS) -c chip_reset.c

clean:
	rm -rf simulate gpio.o bits.o spi.o bang_registers.o strobe.o status_byte.o xosc.o freq_synth_config.o chip_reset.o