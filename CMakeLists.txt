cmake_minimum_required(VERSION 3.10)

project(G_0_common VERSION 1.0 LANGUAGES C)

install(
  FILES
    include/-0_common.h
  DESTINATION
    include
)

install(
  FILES
    include/-0/common_export.h
    include/-0/common_macros.h
    include/-0/common_types.h
  DESTINATION
    include/-0
)
