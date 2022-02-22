DIRS=$(shell cat commands | awk '{print $$1}')

ARCH=\
     amd64 \
     386 \
     arm \
     arm64

TOP=$(PWD)/../../../
HERE=$(PWD)

.PHONY: all
all: 
	echo $(TOP)
	$(foreach var,$(ARCH),mkdir -p $(TOP)/$(var)/bin;)
	$(foreach var,$(DIRS),echo $(var);)
	$(foreach targ,$(DIRS),$(foreach arch,$(ARCH),echo arch $(arch) dir $(targ);))
	$(foreach targ,$(DIRS),$(foreach arch,$(ARCH),(cd ${targ}  && GOOS=plan9 CGO_ENABLED=0 go build -o $(TOP)/${arch}/bin) ;))

.PHONY: targs
list:
	echo $(DIRS)
