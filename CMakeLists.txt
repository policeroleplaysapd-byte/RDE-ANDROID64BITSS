cmake_minimum_required(VERSION 3.22.1)

project("rde_ai")

add_library(
    rde_ai
    SHARED
    main.cpp
)

# Forzamos a que el archivo generado se llame exactamente rde_ai.so (sin el prefijo "lib")
set_target_properties(rde_ai PROPERTIES PREFIX "")

find_library(
    log-lib
    log
)

target_link_libraries(
    rde_ai
    ${log-lib}
)
