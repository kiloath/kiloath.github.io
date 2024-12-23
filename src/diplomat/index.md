# diplomat
* <a href="https://github.com/rust-diplomat/diplomat" target="_blank">diplomat repo</a>
* CMakeLists.txt
  ```cmake
  cmake_minimum_required(VERSION 3.10)
  project(diplomat_example)
  
  file(GLOB ALL_HEADERS "*.h")
  
  include(ExternalProject)
  ExternalProject_Add(
      rust_code
      SOURCE_DIR ${CMAKE_CURRENT_SOURCE_DIR}/..
      CONFIGURE_COMMAND ""
      BUILD_COMMAND cargo build --release
      INSTALL_COMMAND ""
  )
  
  set(RUST_LIB_PATH "${CMAKE_CURRENT_SOURCE_DIR}/../../target/release/diplomat_example.dll.lib")
  
  add_executable(${PROJECT_NAME} main.c)
  target_link_libraries(${PROJECT_NAME} ${RUST_LIB_PATH})
  ```
* <a href="https://tweedegolf.nl/en/blog/131/mix-in-rust-delegating-ffi-definitions-to-diplomat">build.rs</a>