add_library(rotary_encoder rotary_encoder.cpp)
target_include_directories(rotary_encoder 
    PUBLIC
    ${PROJECT_SOURCE_DIR}/include
    )
target_link_libraries(rotary_encoder 
    pico_stdlib 
    ui_core
    switch_button
    )