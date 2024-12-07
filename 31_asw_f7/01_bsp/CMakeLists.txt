
#[[-----------------------------------
Set Project Directories
-------------------------------------]]
set(bsp_directory_f7xx   ${CMAKE_CURRENT_SOURCE_DIR}/hal)
set(cmsis_directory_f7xx ${CMAKE_CURRENT_SOURCE_DIR}/cmsis)
#[[-----------------------------------
Board Specific Drivers 
-------------------------------------]]
set(board_support_dir   ${CMAKE_CURRENT_SOURCE_DIR}/f7-disco-bsp)


#[[-----------------------------------
Global Include Directories
-------------------------------------]]
include_directories(
    ${cmsis_directory_f7xx}/arm/Core/Include
    ${cmsis_directory_f7xx}/cmsis-device-f7-master/Include
    ${bsp_directory_f7xx}/Inc/Config
    ${bsp_directory_f7xx}/Inc
    # ${bsp_directory_f7xx}/Inc/Legacy
)

#[[-----------------------------------
Include CMakeFiles from various modules
-------------------------------------]]
add_subdirectory(${cmsis_directory_f7xx})
add_subdirectory(${bsp_directory_f7xx})
add_subdirectory(${board_support_dir})