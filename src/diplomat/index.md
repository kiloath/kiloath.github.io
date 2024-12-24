# diplomat
* <a href="https://github.com/rust-diplomat/diplomat" target="_blank">diplomat repo</a>
* example/c/CMakeLists.txt
  ```
  cmake_minimum_required(VERSION 3.10)
  project(diplomat_example)
  
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
  
  add_custom_command(
      TARGET ${PROJECT_NAME} POST_BUILD
      COMMAND ${CMAKE_COMMAND} -E copy_if_different
      "${CMAKE_CURRENT_SOURCE_DIR}/../../target/release/diplomat_example.dll"
      "${CMAKE_BINARY_DIR}"
  )
  ```
* example/c/Cargo.toml
  ```toml
  [build-dependencies]
  diplomat-tool.workspace = true
  ```
* example/c/build.rs
  ```rust
  fn main() {
      diplomat_tool::gen(
          std::path::Path::new("src/lib.rs"),
          "c",
          std::path::Path::new("c/include/"),
          &Default::default(),
          None,
          false,
      )
      .unwrap();
  }
  ```
* <a href="https://tweedegolf.nl/en/blog/131/mix-in-rust-delegating-ffi-definitions-to-diplomat">build.rs</a>