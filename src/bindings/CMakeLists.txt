# Nothing interesting now. Will compile the python module after finished
#
# $Id$

INCLUDE( ${OPDE_SOURCE_DIR}/src/services/Services.cmake )
INCLUDE( ${OPDE_SOURCE_DIR}/src/base/Base.cmake )

include_directories(
    ${OGRE_INCLUDE_DIR}
    ${OIS_INCLUDE_DIR}
    ${OPDE_BINARY_DIR}
    ${OPDE_BASE_INCLUDES}
    ${OPDE_SERVICE_INCLUDES}
    ${PYTHON_INCLUDE_PATH}
)


add_library(OpdePythonBindings 
    bindings.cpp 
    bindings.h
    ServiceBinder.cpp
    ServiceBinder.h
    ConfigServiceBinder.cpp
    ConfigServiceBinder.h
    LinkServiceBinder.cpp
    LinkServiceBinder.h
    RelationBinder.cpp
    RelationBinder.h
    LinkQueryResultBinder.cpp
    LinkQueryResultBinder.h
    PropertyServiceBinder.cpp
    PropertyServiceBinder.h
    DTypeBinder.cpp
    DTypeBinder.h
)

target_link_libraries(OpdePythonBindings
    ${OGRE_LIBRARIES}
    ${OPDE_BASE_LIBRARIES}
    ${PYTHON_LIBRARIES}
    ${OPDE_SERVICE_LIBRARIES}
)