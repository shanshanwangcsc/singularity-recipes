TMPDIR ?= /tmp
PREFIX := .

CONTAINER_SIF := $(PREFIX)/dlc_ubuntu.sif
CONTAINER_DEF := dlc_ubuntu.def

.PHONY: all
all: $(CONTAINER_SIF)

$(CONTAINER_SIF): $(CONTAINER_DEF) ../visualization/vgl_base_ubuntu.sif
	@echo "Building $(CONTAINER_SIF) using TMPDIR=$(TMPDIR)"
	@echo "Temporarily unsetting APPTAINER_BIND/SINGULARITY_BIND to avoid host mount conflicts..."
	env -u APPTAINER_BIND -u SINGULARITY_BIND apptainer build --fakeroot --bind=$(TMPDIR):/tmp $@ $<

.PHONY: clean
clean:
	rm -f $(CONTAINER_SIF)