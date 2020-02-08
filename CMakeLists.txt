#
# project: mtb_ui
#

if (NOT FIPS_IMPORT)
    cmake_minimum_required(VERSION 2.8)
    get_filename_component(FIPS_ROOT_DIR "../fips" ABSOLUTE)
    include("${FIPS_ROOT_DIR}/cmake/fips.cmake")
    fips_setup()
    fips_project(mtb_ui)
endif()

fips_project(mtb_ui)
fips_begin_lib(mtb_ui)
    fips_vs_warning_level(4)
    #fips_dir(src)
    #fips_files( ColorGradient.cpp Bezier.cpp
    #PieMenu.cpp  Plot.cpp ToggleButton.cpp ) #Sequentity.cpp
    fips_src(src)
    fips_dir(.)
    fips_dir(res)
    fipsutil_copy(fonts.yml)
    fips_include_directories(include)
    fips_deps(imgui)
fips_end_lib()
#target_include_directories(mtb_ui PUBLIC include)

if (NOT FIPS_IMPORT)
    fips_finish()
endif()

    

# cmake_minimum_required( VERSION 3.6 )
# set (CMAKE_CXX_STANDARD 14)
# set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -stdlib=libc++")

# project( helpers )

# set(ROOT ${CMAKE_CURRENT_SOURCE_DIR})

# set(CMAKE_INSTALL_PREFIX ${CMAKE_SOURCE_DIR})

# set(CMAKE_BUILD_TYPE Debug)

# add_library(mtb_ui STATIC
#   src/ColorGradient.cpp
#   src/Bezier.cpp
#   src/PieMenu.cpp
#   src/Sequentity.cpp
# )

# target_include_directories(mtb_ui PUBLIC ${CMAKE_CURRENT_SOURCE_DIR}/include)
# set_target_properties(mtb_ui PROPERTIES PREFIX "")

# target_link_libraries(mtb_ui PUBLIC imgui EnTT)

# install(TARGETS mtb_ui 
  # ARCHIVE DESTINATION static
# )

# install(DIRECTORY include/mtb_ui DESTINATION include)