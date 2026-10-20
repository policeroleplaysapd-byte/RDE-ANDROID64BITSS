cmake_minimum_required(VERSION 3.22.1)

project("rde_ai")

# Indicamos que vamos a compilar una biblioteca compartida (.so) llamada rde_ai a partir de main.cpp
add_library(
    rde_ai
    SHARED
    main.cpp
)

# Vinculamos la librería de logs de Android para poder depurar si es necesario
find_library(
    log-lib
    log
)

target_link_libraries(
    rde_ai
    ${log-lib}
)
