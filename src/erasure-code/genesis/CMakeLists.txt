# genesis plugin

set(genesis_srcs
  ErasureCodePluginGenesis.cpp
  ErasureCodeGenesis.cpp
  genesis_init.cpp
  $<TARGET_OBJECTS:erasure_code_objs>
  $<TARGET_OBJECTS:crush_objs>
  ${CMAKE_SOURCE_DIR}/src/common/str_map.cc
)

add_library(ec_genesis SHARED ${genesis_srcs})
set_target_properties(ec_genesis PROPERTIES
  INSTALL_RPATH "")
install(TARGETS ec_genesis DESTINATION ${erasure_plugin_dir})
