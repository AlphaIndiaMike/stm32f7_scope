#[[-----------------------------------
Component name
-------------------------------------]]

set(component_name main_component)
set(component_src main_component_source)

message("Compiling ${component_name}, bsp_directory: ${bsp_directory}")

#[[-----------------------------------
Build setup
-------------------------------------]]

set(${component_src}                      
    Src/GUIConf.c
    Src/LCDConf.c
    Src/main.c
    Src/mtouch.c
    Src/stm32f7xx_it.c
    # Src/syscalls.c
    Src/system_stm32f7xx.c
) 

set_source_files_properties( ${${component_src}}
    COMPILE_FLAGS "${SYSTEM_COMPILE_OPTIONS}")

add_library(${component_name} OBJECT ${${component_src}})

target_compile_definitions(${component_name} PRIVATE 
	${TARGET_COMPILE_DEFS}
)

target_include_directories( ${component_name} PRIVATE
    ${bsp_directory}/cmsis/arm/Core/Include
    ${bsp_directory}/cmsis/arm/DSP/Include
    ${bsp_directory}/cmsis/cmsis-device-f7-master/Include
    ${bsp_directory}/hal/stm32f7xx-hal-driver-master/Inc/Config
    ${bsp_directory}/hal/stm32f7xx-hal-driver-master/Inc
    ${bsp_directory}/f7-disco-bsp
    ${bsp_directory}/f7-disco-bsp/STM32746G-Discovery
    ${bsp_directory}/f7-disco-bsp/Log
    ${bsp_directory}/f7-disco-bsp/Fonts
    ${bsp_directory}/f7-disco-bsp/Components/wm8994
    ${bsp_directory}/f7-disco-bsp/Components/ts3510
    ${bsp_directory}/f7-disco-bsp/Components/stmpe811
    ${bsp_directory}/f7-disco-bsp/Components/st7735
    ${bsp_directory}/f7-disco-bsp/Components/s5k5cag
    ${bsp_directory}/f7-disco-bsp/Components/rk043fn48h
    ${bsp_directory}/f7-disco-bsp/Components/ov9655
    ${bsp_directory}/f7-disco-bsp/Components/n25q512a
    ${bsp_directory}/f7-disco-bsp/Components/n25q128a
    ${bsp_directory}/f7-disco-bsp/Components/mfxstm32l152
    ${bsp_directory}/f7-disco-bsp/Components/ft5336
    ${bsp_directory}/f7-disco-bsp/Components/exc7200
    ${bsp_directory}/f7-disco-bsp/Components/ampire640480
    ${bsp_directory}/f7-disco-bsp/Components/ampire480272
    ${bsp_directory}/f7-disco-bsp/Components/Common
    ${lib_directory}/STemWin/inc
    ${lib_directory}/STemWin/Config
    ${os_directory}/FreeRTOS/Source/include
    ${os_directory}/FreeRTOS/Source/portable/GCC/ARM_CM7
    ${os_directory}/FreeRTOS/Config
    ${os_directory}/CMSIS_RTOS
    Inc
)

#[[-----------------------------------
END
-------------------------------------]]

