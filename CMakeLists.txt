cmake_minimum_required(VERSION 2.8)

project( CPack_Example NONE )

install(FILES header.hpp DESTINATION . COMPONENT Headers )
install(FILES a_file.txt DESTINATION . COMPONENT Other )
install(FILES License.txt DESTINATION . )
install(FILES License.txt DESTINATION . COMPONENT Legal )
install(FILES License.txt DESTINATION . COMPONENT License )

#set(CPACK_PACKAGE_NAME "Iosif_CPack_Example") #should you wish to override the above project setting
set(CPACK_PACKAGE_VENDOR "Iosif") 
set(CPACK_PACKAGE_DESCRIPTION_SUMMARY "Not a very good description") # Not used by NSIS?
set(CPACK_PACKAGE_VERSION "6.6.6") # major.minor.path
set(CPACK_RESOURCE_FILE_LICENSE "${CMAKE_CURRENT_SOURCE_DIR}/License.txt")

set(CPACK_NSIS_MENU_LINKS "License.txt" "License")

set(CPACK_COMPONENTS_GROUPING "IGNORE")

include(CPack)

