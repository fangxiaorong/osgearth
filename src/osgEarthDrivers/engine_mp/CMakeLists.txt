
SET(TARGET_COMMON_LIBRARIES ${TARGET_COMMON_LIBRARIES} osgEarthSymbology)

set(TARGET_GLSL
    MPEngine.vert.glsl
    MPEngine.frag.glsl)

set(SHADERS_CPP "${CMAKE_CURRENT_BINARY_DIR}/AutoGenShaders.cpp")

configure_shaders(
    MPShaders.cpp.in
    ${SHADERS_CPP}
    ${TARGET_GLSL} )

SET(TARGET_SRC
    HeightFieldCache.cpp
    KeyNodeFactory.cpp
    MPGeometry.cpp
    MPTerrainEngineNode.cpp
    MPTerrainEngineDriver.cpp
    SingleKeyNodeFactory.cpp
    TerrainNode.cpp
    TileGroup.cpp
    TileModel.cpp
    TileModelCompiler.cpp
    TileNode.cpp
    TileNodeRegistry.cpp
    TileModelFactory.cpp
    TilePagedLOD.cpp
    ${SHADERS_CPP}
)

SET(TARGET_H
    Common
    DynamicLODScaleCallback
    HeightFieldCache
    FileLocationCallback
    KeyNodeFactory
    MPGeometry
    MPTerrainEngineNode
    MPTerrainEngineOptions
    QuickReleaseGLObjects
    SingleKeyNodeFactory
    TerrainNode
    TileGroup
    TileModel
    TileModelCompiler
    TileNode
    TileNodeRegistry
    TileModelFactory
    TilePagedLOD
)

setup_plugin(osgearth_engine_mp)

# to install public driver includes:
SET(LIB_NAME engine_mp)
SET(LIB_PUBLIC_HEADERS ${TARGET_H})
INCLUDE(ModuleInstallOsgEarthDriverIncludes OPTIONAL)

