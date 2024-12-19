add_library(hw_i2c hw_i2c.cpp)
target_include_directories(hw_i2c 
    PUBLIC
    ${PROJECT_SOURCE_DIR}/include
    )
target_link_libraries(hw_i2c 
    pico_stdlib 
    hardware_i2c 
    pico_i2c_slave 
    )

