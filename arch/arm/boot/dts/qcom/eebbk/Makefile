#
# SPDX-FileCopyrightText: The LineageOS Project
# SPDX-License-Identifier: Apache-2.0
#

dtb-$(CONFIG_MACH_EEBBK_H7000) += sda660-mtp-H7000.dtb

ifeq ($(CONFIG_ARM64),y)
always          := $(dtb-y)
always          += $(dtbo-y)
subdir-y        := $(dts-dirs)
else
targets += dtbs
targets += $(addprefix ../, $(dtb-y))

$(obj)/../%.dtb: $(src)/%.dts FORCE
	$(call if_changed_dep,dtc)

dtbs: $(addprefix $(obj)/../,$(dtb-y))
endif
clean-files := *.dtbo *.dtb
