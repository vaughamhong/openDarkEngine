include_directories ( 
    ${OGRE_INCLUDE_DIR} 
    ${OPDE_BINARY_DIR}
    ${OPDE_SOURCE_DIR}/src/base
    ${OPDE_SOURCE_DIR}/src/base/dyntype
    ${OPDE_SOURCE_DIR}/src/base/Dark
    ${OPDE_SOURCE_DIR}/src/scenemanager
    ${OPDE_SOURCE_DIR}/src/compat
    ${OPDE_SOURCE_DIR}/src/base/servicemanager
    ${OPDE_SOURCE_DIR}/src/base/console
    ${OPDE_SOURCE_DIR}/src/base/file
    ${OPDE_SOURCE_DIR}/src/base/logger
    ${OPDE_SOURCE_DIR}/src/services
    ${OPDE_SOURCE_DIR}/src/services/worldrep
    ${OPDE_SOURCE_DIR}/src/services/binary
    ${OPDE_SOURCE_DIR}/src/services/database
    ${OPDE_SOURCE_DIR}/src/services/link
    ${OPDE_SOURCE_DIR}/src/services/inherit
    ${OPDE_SOURCE_DIR}/src/services/property
)

link_directories ( 
    ${OGRE_LIB_DIR}
    ${OPDE_SOURCE_DIR}/src/base
    ${OPDE_SOURCE_DIR}/src/base/servicemanager
)

IF(STATIC_LIBS)
    add_library (OpdeGameService GameService.cpp GameService.h)

    SET_TARGET_PROPERTIES(OpdeGameService PROPERTIES
	COMPILE_DEFINITIONS "OPDELIB_DLL_TARGET"
    )
ENDIF(STATIC_LIBS)
