# frama-c-path.mk contains variables which are specific to each
# user and should not be versioned, such as the path to the
# frama-c binaries (e.g. FRAMAC and FRAMAC_GUI).
# It is an optional include, unnecessary if frama-c is in the PATH.
-include frama-c-path.mk

include ../fcscripts/frama-c.mk

# Define global parameters
CPPFLAGS  =
FCFLAGS  +=
EVAFLAGS += -slevel-function initBoard:19,addRandom:34 \
-val-slevel-merge-after-loop addRandom

# Export environment variable for Frama-C
export FRAMA_C_MEMORY_FOOTPRINT	= 8

TARGETS=2048
all: $(TARGETS:%=%.eva)
help:
	@echo "targets: $(TARGETS)"
loop: $(TARGETS:%=%.parse.loop) $(TARGETS:%=%.eva.loop)

2048.parse: 2048.c
