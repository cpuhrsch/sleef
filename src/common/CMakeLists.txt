# Compiler properties

set(COMMON_TARGET_PROPERTIES 
  POSITION_INDEPENDENT_CODE ON   # -fPIC
  C_STANDARD 99                  # -std=gnu99
  )

# This is a workaround of appveyor bug
string(CONCAT CMAKE_C_FLAGS ${SLEEF_C_FLAGS})

# Target TARGET_LIBCOMMON_OBJ

add_library(${TARGET_LIBCOMMON_OBJ} OBJECT common.c)
set_target_properties(${TARGET_LIBCOMMON_OBJ} PROPERTIES ${COMMON_TARGET_PROPERTIES})

# Target TARGET_LIBARRAYMAP_OBJ

add_library(${TARGET_LIBARRAYMAP_OBJ} OBJECT arraymap.c)
set_target_properties(${TARGET_LIBARRAYMAP_OBJ} PROPERTIES ${COMMON_TARGET_PROPERTIES})
