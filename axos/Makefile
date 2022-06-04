GPPPARAMS = -m32
ASPARAMS = -m32
LDPARAMS = -melf_i386

objects = loader.o kernel.o

%.o: %.cpp
	g++ $(GPPPARAMS) -o $@ -c $<

%.o: %.s
	g++ $(ASPARAMS) -o $@ -c $<

mykernel.bin: linker.ld $(objects)
	ld $(LDPARAMS) -T $< -o $@ $(objects)

install: mykernel.bin 
	sudo cp $< /boot/mykernel.bin
	g++ $(GPPPARAMS) -o $@ -c $<
