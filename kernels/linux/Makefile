KDIR ?= /lib/modules/`uname -r`/build
SDIR ?= /lib/modules/`uname -r`/source

default:
	$(MAKE) -C $(KDIR) M=$(PWD)

signed: default
	$(SDIR)/scripts/sign-file sha512 $(SDIR)/certs/signing_key.pem $(SDIR)/certs/signing_key.x509 tense.ko

clean:
	$(RM) tense.mod.c
	$(RM) tense.mod.o
	$(RM) tense.mod
	$(RM) tense.ko
	$(RM) tense.o
	$(RM) main.o
