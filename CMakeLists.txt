if(CONFIG_USE_SENSOR_BME680)
  set(BSEC2_SRCS src/bsec2.cpp)
endif()

idf_component_register(
  SRCS
    ${BSEC2_SRCS}
  INCLUDE_DIRS
    src
    src/inc
  REQUIRES
    arduino
    Bosch-BME68x-Library
)

if(CONFIG_USE_SENSOR_BME680)
  target_link_libraries(${COMPONENT_LIB}
    ${COMPONENT_DIR}/src/esp32/libalgobsec.a)
endif()
