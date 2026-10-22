# Use /tmp by default, but allow overriding via: make TMPDIR=/scratch/project_xxx/tmp
TMPDIR ?= /tmp
PREFIX := .

CONTAINER_SIF := $(PREFIX)/vgl_base_ubuntu.sif
CONTAINER_DEF := vgl_base_ubuntu.def

.PHONY: all clean

all: $(CONTAINER_SIF)

$(CONTAINER_SIF): $(CONTAINER_DEF) getEglCard eglDebugInfo getX11Display vglrun_wrapper
	@echo "Building $(CONTAINER_SIF) using TMPDIR=$(TMPDIR)"
	@echo "Temporarily unsetting APPTAINER_BIND/SINGULARITY_BIND to avoid host mount conflicts..."
	env -u APPTAINER_BIND -u SINGULARITY_BIND apptainer build --fakeroot --bind=$(TMPDIR):/tmp $@ $<

clean:
	rm -f $(CONTAINER_SIF)