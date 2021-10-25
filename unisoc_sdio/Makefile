ccflags-y += -DOTT_UWE
ccflags-y += -Wno-unused-function

ifneq ($(UNISOC_BSP_INCLUDE),)
ccflags-y += -I$(UNISOC_BSP_INCLUDE)
endif

obj-m += sprdbt_tty.o
sprdbt_tty-objs := tty.o \
                   rfkill.o \
                   lpm.o \
                   alignment/sitm.o \
                   dump.o

modules:
	$(MAKE) ARCH=$(ARCH) -C $(KDIR) M=$(CURDIR) $@

clean:
	rm -f *.o  .*.o.cmd modules.order Module.symvers *.ko *.mod.c .*.ko.cmd
	rm -rf .tmp_versions
	rm -f alignment/*.o alignment/.*.o.cmd


kernelrelease:
	$(MAKE) ARCH=$(ARCH) -C $(KDIR) $@
