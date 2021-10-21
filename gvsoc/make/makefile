#
# MIT License
#
# Copyright(c) 2011-2020 The Maintainers of Nanvix
#
# Permission is hereby granted, free of charge, to any person obtaining a copy
# of this software and associated documentation files (the "Software"), to deal
# in the Software without restriction, including without limitation the rights
# to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
# copies of the Software, and to permit persons to whom the Software is
# furnished to do so, subject to the following conditions:
#
# The above copyright notice and this permission notice shall be included in all
# copies or substantial portions of the Software.
#
# THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
# IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
# FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
# AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
# LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
# OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
# SOFTWARE.
#

#===============================================================================
# Target Configuration
#===============================================================================

export TARGET    ?= gvsoc
export PROCESSOR := riscv32
export CLUSTER   := riscv32-cluster
export CORE      := rv32imcxgap8 

export CFLAGS := -D __qemu_riscv32__    # Target
export CFLAGS += -D __riscv32__         # Processor
export CFLAGS += -D __wolfe__ # Cluster
export CFLAGS += -D __ri5cy__          # Core

#===============================================================================
# Toolchain Configuration
#===============================================================================

# Toolchain Directory
export TOOLCHAIN_DIR ?= /home/reinaldo/workspace/riscv/bin

# Toolchain

export CC := $(TOOLCHAIN_DIR)/riscv32-unknown-elf-gcc
export LD := $(TOOLCHAIN_DIR)/riscv32-unknown-elf-ld
export AR := $(TOOLCHAIN_DIR)/riscv32-unknown-elf-ar
# Timeout Variable
export TIMEOUT ?= 120

# Compiler Options
export CFLAGS += -march=rv32imcxgap8  -mabi=ilp32 -mcmodel=medany
export CFLAGS += -ffunction-sections -fdata-sections
export CFLAGS += -nostdlib -nostdinc -ffreestanding
export CFLAGS += -pedantic-errors
export CFLAGS += -Wstack-usage=4096
export CFLAGS += -Wno-error=type-limits
export CFLAGS += -D __HAS_HW_DIVISION=1 -D__HAS_HW_MULTIPLICATION=1
export CFLAGS += -MMD -MP -march=rv32imcxgap9 -mPE=8 -mFC=1  -Os -g  - -fdata-sections -ffunction-sections -include pos/chips/pulp/config.h -I/home/reinaldo/workspace/pulp-sdk/rtos/pulpos/pulp/include/pos/chips/pulp -I/home/reinaldo/workspace/pulp-sdk/ext_libs/include  -fno-jump-tables -fno-tree-loop-distribute-patterns  -I/home/reinaldo/workspace/pulp-sdk/rtos/pulpos/common/lib/libc/minimal/include -I/home/reinaldo/workspace/pulp-sdk/rtos/pulpos/common/include -I/home/reinaldo/workspace/pulp-sdk/rtos/pulpos/common/kernel -I/home/reinaldo/workspace/pulp-sdk/rtos/pulpos/pulp_archi/include -I/home/reinaldo/workspace/pulp-sdk/rtos/pulpos/pulp_hal/include -I/home/reinaldo/workspace/pulp-sdk/rtos/pmsis/pmsis_api/include -I/home/reinaldo/workspace/pulp-sdk/rtos/pulpos/pulp/include -I/home/reinaldo/workspace/pulp-sdk/rtos/pmsis/pmsis_bsp/include

# Linker Options
#export LDFLAGS := -march=rv32imac  -mabi=ilp32 -mcmodel=medany
export LDFLAGS := -march=rv32imcxgap8  -mabi=ilp32 -mcmodel=medany
export LDFLAGS += -Wl,--nmagic -Wl,--gc-sections
export LDFLAGS += -nostdlib -nostdinc -ffreestanding

# Suffix for Objects
export OBJ_SUFFIX := gvsoc

#===============================================================================
# Libraries
#===============================================================================

export THEIR_LIBS := -lgcc
export LIBLWIP :=
