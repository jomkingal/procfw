TARGET = fast_recovery
OBJS = main.o rain.o imports.o syscall.o ../PXE/Launcher/launcher_patch_offset.o ../Common/utils.o
LIBS =
CFLAGS = -Os -G0 -Wall -I ../Common -I ../include
CXXFLAGS = $(CFLAGS)
ASFLAGS = $(CFLAGS)
LDFLAGS =
ENCRYPT=1

ifeq ($(DEBUG), 1)
CFLAGS += -DDEBUG=1
OBJS += ../Common/printk.o
else
endif

ifeq ($(CONFIG_620), 1)
CFLAGS += -DCONFIG_620=1
PSP_FW_VERSION = 620
PSP_EBOOT_TITLE = 6.20
endif

ifeq ($(CONFIG_635), 1)
CFLAGS += -DCONFIG_635=1
PSP_FW_VERSION = 635
PSP_EBOOT_TITLE = 6.35
endif

ifeq ($(CONFIG_639), 1)
CFLAGS += -DCONFIG_639=1
OBJS += ../PXE/Launcher/kxp_639.o
PSP_FW_VERSION = 639
PSP_EBOOT_TITLE = 6.39
endif

ifeq ($(CONFIG_660), 1)
CFLAGS += -DCONFIG_660=1
OBJS += ../PXE/Launcher/kxp_660.o
PSP_FW_VERSION = 660
PSP_EBOOT_TITLE = 6.60
endif

ifeq ($(CONFIG_661), 1)
CFLAGS += -DCONFIG_661=1
OBJS += ../PXE/Launcher/kxp_660.o
PSP_FW_VERSION = 661
PSP_EBOOT_TITLE = 6.61
endif

BUILD_PRX = 1
PSP_EBOOT_TITLE += PRO-C Fast Recovery

EXTRA_TARGETS = EBOOT.PBP
PSP_EBOOT_ICON = ICON0.PNG

PSPSDK=$(shell psp-config --pspsdk-path)
include $(PSPSDK)/lib/build.mak
