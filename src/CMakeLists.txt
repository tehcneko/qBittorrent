if(TARGET ZLIB::ZLIBSTATIC AND NOT TARGET ZLIB::ZLIB)
    add_library(ZLIB::ZLIB INTERFACE IMPORTED GLOBAL)
    target_link_libraries(ZLIB::ZLIB INTERFACE ZLIB::ZLIBSTATIC)
endif()

include_directories(${CMAKE_CURRENT_SOURCE_DIR})

add_subdirectory(app)
add_subdirectory(base)

if (GUI)
    add_subdirectory(gui)
endif()

if (WEBUI)
    add_subdirectory(webui)
endif()
