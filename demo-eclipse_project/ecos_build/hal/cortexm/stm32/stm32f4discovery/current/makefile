# eCos makefile

# This is a generated file - do not edit

export PREFIX := /home/sontd/workspace/Sem7/RT/final/ecos-tools-bin-110209.i386linux/ecos_install
export COMMAND_PREFIX := arm-eabi-
export CC := $(COMMAND_PREFIX)gcc
export OBJCOPY := $(COMMAND_PREFIX)objcopy
export HOST := UNIX
export AR := $(COMMAND_PREFIX)ar

export REPOSITORY := /home/sontd/workspace/Sem7/RT/final/ecos/packages
PACKAGE := hal/cortexm/stm32/stm32f4discovery/current
OBJECT_PREFIX := hal_cortexm_stm32_stm32f4discovery
CFLAGS := -Wall -Wpointer-arith -Wstrict-prototypes -Wundef -Woverloaded-virtual -Wno-write-strings -mcpu=cortex-m3 -mthumb -g -O2 -ffunction-sections -fdata-sections -fno-rtti -fno-exceptions -Werror
LDFLAGS := -mcpu=cortex-m3 -mthumb -Wl,--gc-sections -Wl,-static -Wl,-n -g -nostdlib
VPATH := $(REPOSITORY)/$(PACKAGE)
INCLUDE_PATH := $(INCLUDE_PATH) -I$(PREFIX)/include $(foreach dir,$(VPATH),-I$(dir) -I$(dir)/src -I$(dir)/tests) -I.
MLT := $(wildcard $(REPOSITORY)/$(PACKAGE)/include/pkgconf/mlt*.ldi $(REPOSITORY)/$(PACKAGE)/include/pkgconf/mlt*.h)
TESTS := tests/gpio

build: headers libtarget.a.stamp

LIBRARY := libtarget.a
COMPILE := src/stm32f4discovery_misc.c
OBJECTS := $(COMPILE:.cxx=.o.d)
OBJECTS := $(OBJECTS:.cpp=.o.d)
OBJECTS := $(OBJECTS:.c=.o.d)
OBJECTS := $(OBJECTS:.S=.o.d)

$(LIBRARY).stamp: $(OBJECTS)
	$(AR) rcs $(PREFIX)/lib/$(@:.stamp=) $(foreach obj,$?,$(if $(obj:%.o=),$(dir $(obj))$(OBJECT_PREFIX)_$(notdir $(obj:.o.d=.o)),$(obj)))
	@cat $(foreach obj,$^,$(obj:.o=.o.d)) > $(@:.stamp=.deps)
	@touch $@

headers: mlt_headers $(PREFIX)/include/cyg/hal/plf_io.h $(PREFIX)/include/cyg/hal/plf_arch.h $(PREFIX)/include/cyg/hal/plf_intr.h

$(PREFIX)/include/cyg/hal/plf_io.h: $(REPOSITORY)/$(PACKAGE)/include/plf_io.h
	@mkdir -p $(dir $@)
	@cp $< $@
	@chmod u+w $@

$(PREFIX)/include/cyg/hal/plf_arch.h: $(REPOSITORY)/$(PACKAGE)/include/plf_arch.h
	@mkdir -p $(dir $@)
	@cp $< $@
	@chmod u+w $@

$(PREFIX)/include/cyg/hal/plf_intr.h: $(REPOSITORY)/$(PACKAGE)/include/plf_intr.h
	@mkdir -p $(dir $@)
	@cp $< $@
	@chmod u+w $@

include $(REPOSITORY)/pkgconf/rules.mak

