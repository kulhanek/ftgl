# ==============================================================================
# FTGL CMake File
# ==============================================================================

SET(FTGL_LIB_SRC
        FTContour.cpp
        FTLayout/FTSimpleLayout.cpp
        FTLayout/FTLayout.cpp
        FTLayout/FTLayoutGlue.cpp
        FTLibrary.cpp
        FTGlyph/FTBufferGlyph.cpp
        FTGlyph/FTPolygonGlyph.cpp
        FTGlyph/FTGlyph.cpp
        FTGlyph/FTExtrudeGlyph.cpp
        FTGlyph/FTTextureGlyph.cpp
        FTGlyph/FTBitmapGlyph.cpp
        FTGlyph/FTGlyphGlue.cpp
        FTGlyph/FTPixmapGlyph.cpp
        FTGlyph/FTOutlineGlyph.cpp
        FTCharmap.cpp
        FTPoint.cpp
        FTSize.cpp
        FTGlyphContainer.cpp
        FTVectoriser.cpp
        FTFont/FTPixmapFont.cpp
        FTFont/FTFontGlue.cpp
        FTFont/FTBufferFont.cpp
        FTFont/FTTextureFont.cpp
        FTFont/FTBitmapFont.cpp
        FTFont/FTFont.cpp
        FTFont/FTOutlineFont.cpp
        FTFont/FTExtrudeFont.cpp
        FTFont/FTPolygonFont.cpp
        FTBuffer.cpp
        FTFace.cpp
        )

# create shared library --------------------------------------------------------

ADD_LIBRARY(ftgl_shared SHARED ${FTGL_LIB_SRC})

TARGET_LINK_LIBRARIES(ftgl_shared ${SYSTEM_LIBS})

SET_TARGET_PROPERTIES(ftgl_shared PROPERTIES
                        OUTPUT_NAME ${FTGL_LIB_NAME}
                        CLEAN_DIRECT_OUTPUT 1
                        VERSION ${FTGL_VERSION})
INSTALL(TARGETS
            ftgl_shared
        DESTINATION
            lib
        )

#-------------------------------------------------------------------------------
