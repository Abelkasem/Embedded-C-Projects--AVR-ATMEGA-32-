################################################################################
# Automatically-generated file. Do not edit!
################################################################################

-include ../makefile.init

RM := rm -rf

# All of the sources participating in the build are defined here
-include sources.mk
-include subdir.mk
-include objects.mk

ifneq ($(MAKECMDGOALS),clean)
ifneq ($(strip $(ASM_DEPS)),)
-include $(ASM_DEPS)
endif
ifneq ($(strip $(S_DEPS)),)
-include $(S_DEPS)
endif
ifneq ($(strip $(S_UPPER_DEPS)),)
-include $(S_UPPER_DEPS)
endif
ifneq ($(strip $(C_DEPS)),)
-include $(C_DEPS)
endif
endif

-include ../makefile.defs

# Add inputs and outputs from these tool invocations to the build variables 
LSS += \
TWI_D3.lss \

FLASH_IMAGE += \
TWI_D3.hex \

EEPROM_IMAGE += \
TWI_D3.eep \

SIZEDUMMY += \
sizedummy \


# All Target
all: TWI_D3.elf secondary-outputs

# Tool invocations
TWI_D3.elf: $(OBJS) $(USER_OBJS)
	@echo 'Building target: $@'
	@echo 'Invoking: AVR C Linker'
	avr-gcc -Wl,-Map,TWI_D3.map -mmcu=atmega32 -o "TWI_D3.elf" $(OBJS) $(USER_OBJS) $(LIBS)
	@echo 'Finished building target: $@'
	@echo ' '

TWI_D3.lss: TWI_D3.elf
	@echo 'Invoking: AVR Create Extended Listing'
	-avr-objdump -h -S TWI_D3.elf  >"TWI_D3.lss"
	@echo 'Finished building: $@'
	@echo ' '

TWI_D3.hex: TWI_D3.elf
	@echo 'Create Flash image (ihex format)'
	-avr-objcopy -R .eeprom -R .fuse -R .lock -R .signature -O ihex TWI_D3.elf  "TWI_D3.hex"
	@echo 'Finished building: $@'
	@echo ' '

TWI_D3.eep: TWI_D3.elf
	@echo 'Create eeprom image (ihex format)'
	-avr-objcopy -j .eeprom --no-change-warnings --change-section-lma .eeprom=0 -O ihex TWI_D3.elf  "TWI_D3.eep"
	@echo 'Finished building: $@'
	@echo ' '

sizedummy: TWI_D3.elf
	@echo 'Invoking: Print Size'
	-avr-size --format=avr --mcu=atmega32 TWI_D3.elf
	@echo 'Finished building: $@'
	@echo ' '

# Other Targets
clean:
	-$(RM) $(FLASH_IMAGE)$(ELFS)$(OBJS)$(ASM_DEPS)$(EEPROM_IMAGE)$(S_DEPS)$(SIZEDUMMY)$(S_UPPER_DEPS)$(LSS)$(C_DEPS) TWI_D3.elf
	-@echo ' '

secondary-outputs: $(LSS) $(FLASH_IMAGE) $(EEPROM_IMAGE) $(SIZEDUMMY)

.PHONY: all clean dependents
.SECONDARY:

-include ../makefile.targets
