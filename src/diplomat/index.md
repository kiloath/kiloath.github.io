# diplomat
* <a href="https://github.com/rust-diplomat/diplomat" target="_blank">diplomat repo</a>
* CMakeLists.txt
  ```cmake
  cmake_minimum_required(VERSION 3.10)
  project(diplomat_example)

  include(ExternalProject)
  ExternalProject_Add(
      rust_code
      SOURCE_DIR ${CMAKE_SOURCE_DIR}/..
      CONFIGURE_COMMAND ""
      BUILD_COMMAND cargo build --release
      INSTALL_COMMAND ""
  )
  ```