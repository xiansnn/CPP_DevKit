#-------------------------------------------------------------------------------------
add_executable(serial_hello_world serial_hello_world.cpp )
# pico_set_program_name(serial_hello_world "cpp_dk")
# pico_set_program_version(serial_hello_world "0.1")
pico_enable_stdio_uart(serial_hello_world 1)
pico_enable_stdio_usb(serial_hello_world 0)

target_link_libraries(serial_hello_world
    pico_stdlib)

# Add the standard include files to the build
# target_include_directories(serial_hello_world 
#     PRIVATE
#     ${CMAKE_CURRENT_LIST_DIR}
# )
#-------------------------------------------------------------------------------------
add_executable(test_switch_button test_switch_button_irq.cpp)
pico_enable_stdio_uart(test_switch_button 1)
pico_enable_stdio_usb(test_switch_button 0)
# pico_set_program_name(test_switch_button "test_switch_button")
# pico_set_program_version(test_switch_button "0.1")
target_include_directories(test_switch_button 
    PRIVATE
    ${PROJECT_SOURCE_DIR}/include
    )
target_link_libraries(test_switch_button  
    pico_stdlib
    switch_button
    debug_probe
    )
# pico_add_extra_outputs(test_switch_button)
#-------------------------------------------------------------------------------------
add_executable(test_debug_probe test_debug_probe.cpp)
pico_enable_stdio_uart(test_debug_probe 1)
pico_enable_stdio_usb(test_debug_probe 0)
# pico_set_program_name(test_debug_probe "test_debug_probe")
# pico_set_program_version(test_debug_probe "0.1")
target_include_directories(test_debug_probe 
    PRIVATE 
    ${PROJECT_SOURCE_DIR}/include
    )
target_link_libraries(test_debug_probe
    pico_stdlib 
    debug_probe
    )
# pico_add_extra_outputs(test_debug_probe)

