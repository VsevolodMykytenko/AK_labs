ifneq ($(KERNELRELEASE),)
# kbuild part of makefile
obj-m   := Lab6.o
ccflags-y += -g
else
# normal makefile
KDIR ?= /lib/modules/`uname -r`/build

default:
	$(MAKE) -C $(KDIR) M=$$PWD
	cp Lab6.ko Lab6.ko.unstripped
	$(CROSS_COMPILE)strip -dS Lab6.o
clean:
	$(MAKE) -C $(KDIR) M=$$PWD clean
endif