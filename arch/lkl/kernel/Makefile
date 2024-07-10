extra-y := vmlinux.lds

obj-y = setup.o threads.o irq.o time.o syscalls.o misc.o console.o \
	syscalls_32.o cpu.o atomic.o signal.o

ifeq ($(OUTPUT_FORMAT),mach-o-x86-64)
extra-y += mach-o-linker.o vmlinux-mach-o.lds vmlinux-mach-o.o
endif

$(obj)/vmlinux-mach-o.o: $(src)/vmlinux-mach-o.lds FORCE
	$(Q)$(AS) -c -o $@ $<

CFLAGS_console.o = -Wno-int-conversion
