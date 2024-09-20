
idf_component_register(
  SRCS
    src/bsec2.cpp
    INCLUDE_DIRS
      src
      src/inc
    REQUIRES
      arduino
      Bosch-BME68x-Library
)

target_link_libraries(${COMPONENT_LIB}
  ${COMPONENT_DIR}/src/esp32/libalgobsec.a)

