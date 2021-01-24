cmake_minimum_required(VERSION 3.12)

include(pico_sdk_import.cmake)

project(weatherstation)

pico_sdk_init()

add_executable(weatherstation
        weatherstation.c
        )
        
pico_enable_stdio_usb(weatherstation 1)
pico_enable_stdio_uart(weatherstation 0)

target_link_libraries(weatherstation pico_stdlib hardware_i2c)

pico_add_extra_outputs(weatherstation)
