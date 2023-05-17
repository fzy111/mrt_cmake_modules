cmake_minimum_required(VERSION 3.0.2)
project(mrt_cmake_modules)

cmake_policy(SET CMP0057 NEW)

# Update the installation paths
set(CATKIN_PACKAGE_SHARE_DESTINATION share/${PROJECT_NAME})
set(CATKIN_PACKAGE_BIN_DESTINATION bin)

# Install all cmake files
install(DIRECTORY cmake DESTINATION ${CATKIN_PACKAGE_SHARE_DESTINATION})
install(PROGRAMS scripts/generate_cmake_dependency_file.py scripts/init_coverage.py scripts/eval_coverage.py
                 scripts/run_test.py DESTINATION ${CATKIN_PACKAGE_SHARE_DESTINATION}/scripts)
install(PROGRAMS scripts/generate_cmakelists.py DESTINATION ${CATKIN_PACKAGE_BIN_DESTINATION})
install(FILES yaml/cmake.yaml DESTINATION ${CATKIN_PACKAGE_SHARE_DESTINATION}/yaml)
install(FILES ci_templates/CMakeLists.txt DESTINATION ${CATKIN_PACKAGE_SHARE_DESTINATION})
