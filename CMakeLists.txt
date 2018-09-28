cmake_minimum_required(VERSION 2.6.0)

# pull in the pods macros. See cmake/pods.cmake for documentation
set(POD_NAME velodyne)
include(cmake/pods.cmake)

# automatically build LCM types.  This also defines a number of CMake
# variables, see cmake/lcmtypes.cmake for details
include(cmake/lcmtypes.cmake)
lcmtypes_build()

pods_install_pkg_config_file(lcmtypes_${POD_NAME}
    LIBS -l${LCMTYPES_LIBS}
    REQUIRES lcm
    VERSION 0.0.1)
