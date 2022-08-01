cmake_minimum_required(VERSION 3.0)

project(ITKVNL VERSION 1.0.0)

set(ITKVNL_THIRD_PARTY 1)
  # ITKv5 no longer supports legacy method signatures for VNL
  set(VNL_CONFIG_LEGACY_METHODS     OFF CACHE BOOL "Whether backward-compatibility methods are provided by vnl." FORCE )
  set(VXL_BUILD_CORE_NUMERICS       ON  CACHE BOOL "VXL configuration for ITK" FORCE )
  set(VXL_BUILD_CORE_NUMERICS_ONLY  ON  CACHE BOOL "VXL configuration for ITK" FORCE ) #This hides other VXL core options from CMake
  set(VXL_NO_EXPORT                 FALSE  CACHE BOOL "VXL configuration for ITK" FORCE )
  set(VXL_BUILD_CORE_GEOMETRY       OFF CACHE BOOL "VXL configuration for ITK" FORCE )
  set(VXL_BUILD_CORE_IMAGING        OFF CACHE BOOL "VXL configuration for ITK" FORCE )
  set(VXL_BUILD_CORE_IMAGING        OFF CACHE BOOL "VXL configuration for ITK" FORCE )
  set(VXL_BUILD_CORE_SERIALISATION  OFF CACHE BOOL "VXL configuration for ITK" FORCE )
  set(VXL_BUILD_CORE_UTILITIES      OFF CACHE BOOL "VXL configuration for ITK" FORCE )
  set(VXL_BUILD_CORE_VIDEO          OFF CACHE BOOL "VXL configuration for ITK" FORCE )
  set(VXL_BUILD_CONTRIB             OFF CACHE BOOL "VXL configuration for ITK" FORCE )
  set(VXL_BUILD_EXAMPLES            OFF CACHE BOOL "VXL configuration for ITK" FORCE )
#
  set(VXL_FORCE_V3P_CLIPPER     OFF CACHE BOOL "VXL configuration for ITK" FORCE )
  set(VXL_FORCE_V3P_ZLIB        OFF CACHE BOOL "VXL configuration for ITK" FORCE )
  set(VXL_FORCE_B3P_EXPAT       OFF CACHE BOOL "VXL configuration for ITK" FORCE)
  set(VXL_FORCE_B3P_SHAPELIB    OFF CACHE BOOL "VXL configuration for ITK" FORCE)
  set(VXL_FORCE_V3P_BZLIB2      OFF CACHE BOOL "VXL configuration for ITK" FORCE)
  set(VXL_FORCE_V3P_CLIPPER     OFF CACHE BOOL "VXL configuration for ITK" FORCE)
  set(VXL_FORCE_V3P_DCMTK       OFF CACHE BOOL "VXL configuration for ITK" FORCE)
  set(VXL_FORCE_V3P_GEOTIFF     OFF CACHE BOOL "VXL configuration for ITK" FORCE)
  set(VXL_FORCE_V3P_J2K         OFF CACHE BOOL "VXL configuration for ITK" FORCE)
  set(VXL_FORCE_V3P_JPEG        OFF CACHE BOOL "VXL configuration for ITK" FORCE)
  set(VXL_FORCE_V3P_OPENJPEG2   OFF CACHE BOOL "VXL configuration for ITK" FORCE)
  set(VXL_FORCE_V3P_PNG         OFF CACHE BOOL "VXL configuration for ITK" FORCE)
  set(VXL_FORCE_V3P_TIFF        OFF CACHE BOOL "VXL configuration for ITK" FORCE)
  set(VXL_FORCE_V3P_ZLIB        OFF CACHE BOOL "VXL configuration for ITK" FORCE)

  set(VXL_LIB_PREFIX            "itk")
  set(VXL_LIBRARY_PROPERTIES ${ITK_LIBRARY_PROPERTIES})

  set(ITKVNL_INCLUDE_DIRS
    ${ITKVNL_SOURCE_DIR}/src/v3p/netlib
    ${ITKVNL_SOURCE_DIR}/src/vcl
    ${ITKVNL_SOURCE_DIR}/src/core
    ${ITKVNL_BINARY_DIR}/src/v3p/netlib
    ${ITKVNL_BINARY_DIR}/src/vcl
    ${ITKVNL_BINARY_DIR}/src/core
    )
  set(ITKVNL_LIBRARIES itkvnl_algo itkvnl itkv3p_netlib itkvcl)

add_subdirectory(src)
