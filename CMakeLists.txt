cmake_minimum_required(VERSION 2.8)

project( CPack_Example NONE )

install(FILES header.hpp DESTINATION . COMPONENT Headers )
install(FILES a_file.txt DESTINATION . COMPONENT Other )
install(FILES License.txt DESTINATION . )
install(FILES License.txt DESTINATION . COMPONENT Legal )
install(FILES License.txt DESTINATION . COMPONENT License )

set(CPACK_RESOURCE_FILE_LICENSE "${CMAKE_CURRENT_SOURCE_DIR}/License.txt")

set(CPACK_NSIS_MENU_LINKS "License.txt" "License")

set( CPACK_PROJECT_CONFIG_FILE "${CMAKE_CURRENT_SOURCE_DIR}/CMakeCPackOptions.cmake" )

include(CPack)

