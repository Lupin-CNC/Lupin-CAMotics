set(headers
    CompositeSurface.h
    ContourGenerator.h
    CorrectedMC33.h
    CorrectedMC33Cube.h
    CorrectedMC33LUTs.h
    CubeSlice.h
    CubicalMarchingSquares.h
    Edge.h
    FieldFunction.h
    GridTree.h
    GridTreeBase.h
    GridTreeLeaf.h
    GridTreeNode.h
    GridTreeRef.h
    MarchingCubes.h
    QEF.h
    SliceContourGenerator.h
    Surface.h
    Triangle.h
    TriangleMesh.h
    TriangleSurface.h
    VertexSlice.h)

set(sources
    CompositeSurface.cpp
    CorrectedMC33.cpp
    CorrectedMC33Cube.cpp
    CubeSlice.cpp
    CubicalMarchingSquares.cpp
    FieldFunction.cpp
    GridTree.cpp
    GridTreeLeaf.cpp
    GridTreeNode.cpp
    GridTreeRef.cpp
    MarchingCubes.cpp
    QEF.cpp
    SliceContourGenerator.cpp
    Surface.cpp
    Triangle.cpp
    TriangleMesh.cpp
    TriangleSurface.cpp
    VertexSlice.cpp)

add_library(camotics-contour OBJECT "${headers}" "${sources}")
target_compile_definitions(camotics-contour PRIVATE USING_CBANG)

if("${CMAKE_PROJECT_NAME}" STREQUAL "${PROJECT_NAME}")
  install(FILES ${headers} DESTINATION ${CMAKE_INSTALL_INCLUDEDIR}/camotics/contour)
  install(TARGETS camotics-contour EXPORT CamoticsCore-targets)
endif()
