hex2v: hex2v.c
	gcc hex2v.c -o hex2v

sindata: sindata.c
	gcc sindata.c -o sindata -lm

sindata.hex: sindata
	./sindata >sindata.hex

%.hex: %.asm
	gpasm $<
	sed -i '1d' $@

%.rom: %.hex hex2v
	./hex2v $< >$@

.PHONY: all clean sim doc

doc:
	cd ../doc
	sphinx-build -b pdf .
	sphinx-build -b html .
	cd ../dv

sim: basic.rom dds.rom sindata.hex
	iverilog test.v ../rtl/cpu.v ../rtl/alu.v ../rtl/regs.v ../rtl/idec.v exp.v ../rtl/dram.v pram.v
	./a.out

all: hex2v sindata basic.rom dds.rom sindata.hex sim

clean:
	rm -f basic.lst dds.lst basic.cod dds.cod basic.hex dds.hex hex2v sindata a.out basic.rom dds.rom risc8.vcd sindata.hex ../doc/images/risc8.jpg
