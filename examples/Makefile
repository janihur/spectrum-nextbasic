#IMAGE := $(HOME)/cspect-next-2gb.img
IMAGE := /media/sf_retro-specnext/cspect-next-2gb/cspect-next-2gb.img
IMAGE_DIR := next-basic-examples

BAS := $(patsubst %.txt,%.bas,$(wildcard *.txt))
SPRITES := $(wildcard *.spr)

.PHONY: all
all: $(BAS)

%.bas: %.txt
	txt2bas -t -i $< -o $@

.PHONY: install
install: $(BAS) $(SPRITES)
	hdfmonkey put $(IMAGE) $^ $(IMAGE_DIR)

.PHONY: clean
clean:
	@rm -f *~ *.bas
