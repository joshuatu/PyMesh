# Include headers
INCLUDE_DIRECTORIES(${PROJECT_SOURCE_DIR}/src)
INCLUDE_DIRECTORIES(${PROJECT_SOURCE_DIR}/tools)

SET(TARGET_MODULE_TESTS "")

IF (TARGET MeshUtils)
    ADD_SUBDIRECTORY(MeshUtils)
    LIST(APPEND TARGET_MODULE_TESTS MeshUtils_tests)
ENDIF (TARGET MeshUtils)

IF (TARGET assembler)
    ADD_SUBDIRECTORY(Assembler)
    LIST(APPEND TARGET_MODULE_TESTS assembler_tests)
ENDIF (TARGET assembler)

IF (TARGET tetgen)
    ADD_SUBDIRECTORY(tetgen)
    LIST(APPEND TARGET_MODULE_TESTS tetgen_tests)
ENDIF (TARGET tetgen)

IF (TARGET cgal)
    ADD_SUBDIRECTORY(CGAL)
    LIST(APPEND TARGET_MODULE_TESTS cgal_tests)
ENDIF (TARGET cgal)

IF (TARGET triangle)
    ADD_SUBDIRECTORY(triangle)
    LIST(APPEND TARGET_MODULE_TESTS triangle_tests)
ENDIF (TARGET triangle)

IF (TARGET convex_hull)
    ADD_SUBDIRECTORY(ConvexHull)
    LIST(APPEND TARGET_MODULE_TESTS convex_hull_tests)
ENDIF (TARGET convex_hull)

IF (TARGET boolean)
    ADD_SUBDIRECTORY(Boolean)
    LIST(APPEND TARGET_MODULE_TESTS boolean_tests)
ENDIF (TARGET boolean)

#IF (TARGET EigenUtils)
#    ADD_SUBDIRECTORY(EigenUtils)
#    LIST(APPEND TARGET_MODULE_TESTS EigenUtils_tests)
#ENDIF (TARGET EigenUtils)

IF (TARGET SparseSolver)
    ADD_SUBDIRECTORY(SparseSolver)
    LIST(APPEND TARGET_MODULE_TESTS SparseSolver_tests)
ENDIF (TARGET SparseSolver)

IF (TARGET envelope)
    ADD_SUBDIRECTORY(Envelope)
    LIST(APPEND TARGET_MODULE_TESTS envelope_tests)
ENDIF (TARGET envelope)

IF (TARGET wires)
    ADD_SUBDIRECTORY(Wires)
    LIST(APPEND TARGET_MODULE_TESTS wires_tests)
ENDIF (TARGET wires)

IF (TARGET lib_igl)
    ADD_SUBDIRECTORY(IGL)
    LIST(APPEND TARGET_MODULE_TESTS igl_tests)
ENDIF (TARGET lib_igl)

IF (TARGET lib_triangulation)
    ADD_SUBDIRECTORY(Triangulation)
    LIST(APPEND TARGET_MODULE_TESTS triangulation_tests)
ENDIF (TARGET lib_triangulation)

ADD_CUSTOM_TARGET(tools_tests DEPENDS ${TARGET_MODULE_TESTS})
