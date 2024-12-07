#[[-----------------------------------
Component name
-------------------------------------]]

set(component_name f7_disco_bsp_component)
set(component_src f7_disco_bsp_source)

message("Compiling ${component_name}, bsp_directory: ${bsp_directory}")

#[[-----------------------------------
Build setup
-------------------------------------]]

#[[-----------------------------------
Components
-------------------------------------]]
set(${component_src}                   
    Components/exc7200/exc7200.c
    Components/ft5336/ft5336.c
    Components/mfxstm32l152/mfxstm32l152.c
    Components/ov9655/ov9655.c
    Components/s5k5cag/s5k5cag.c
    Components/st7735/st7735.c
    Components/stmpe811/stmpe811.c
    Components/ts3510/ts3510.c
    Components/wm8994/wm8994.c
    #Fonts/font8.c
    #Fonts/font12.c
    #Fonts/font16.c
    #Fonts/font20.c
    #Fonts/font24.c
    Log/lcd_log.c
    STM32746G-Discovery/stm32746g_discovery_ts.c
    STM32746G-Discovery/stm32746g_discovery_sdram.c
    STM32746G-Discovery/stm32746g_discovery_sd.c
    STM32746G-Discovery/stm32746g_discovery_qspi.c
    STM32746G-Discovery/stm32746g_discovery_lcd.c
    STM32746G-Discovery/stm32746g_discovery_eeprom.c
    STM32746G-Discovery/stm32746g_discovery_camera.c
    STM32746G-Discovery/stm32746g_discovery_audio.c
    STM32746G-Discovery/stm32746g_discovery.c
)

#[[-----------------------------------
Compiler flag
-------------------------------------]]

set_source_files_properties( ${${component_src}}
    COMPILE_FLAGS "${SYSTEM_COMPILE_OPTIONS}")

#[[-----------------------------------
Add library
-------------------------------------]]

add_library(${component_name} OBJECT ${${component_src}})

target_compile_definitions(${component_name} PRIVATE 
	${TARGET_COMPILE_DEFS}
)

target_include_directories(${component_name} PRIVATE
    ${bsp_directory}/cmsis/arm/Core/Include
    ${bsp_directory}/cmsis/arm/DSP/Include
    ${bsp_directory}/cmsis/cmsis-device-f7-master/Include
    ${bsp_directory}/hal/stm32f7xx-hal-driver-legacy/Inc
    ${bsp_directory}/hal/stm32f7xx-hal-driver-master/Inc/Config
    ${bsp_directory}/hal/stm32f7xx-hal-driver-master/Inc
    STM32746G-Discovery
    Log
    Fonts
    Components/wm8994
    Components/ts3510
    Components/stmpe811
    Components/st7735
    Components/s5k5cag
    Components/rk043fn48h
    Components/ov9655
    Components/n25q512a
    Components/n25q128a
    Components/mfxstm32l152
    Components/ft5336
    Components/exc7200
    Components/ampire640480
    Components/ampire480272
    Components/Common
)

#[[-----------------------------------
END
-------------------------------------]]

