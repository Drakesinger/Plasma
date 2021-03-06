include_directories("../../CoreLib")
include_directories("../../NucleusLib")

set(pnUtils_HEADERS
    Pch.h
    pnUtils.h
    pnUtCoreLib.h
    pnUtAllIncludes.h
    pnUtArray.h
    pnUtCmd.h
    pnUtCrypt.h
    pnUtHash.h
    pnUtList.h
    pnUtMisc.h
    pnUtPragma.h
    pnUtPriQ.h
    pnUtSort.h
    pnUtStr.h
    pnUtTime.h
)

set(pnUtils_SOURCES
    pnUtArray.cpp
    pnUtCmd.cpp
    pnUtCrypt.cpp
    pnUtHash.cpp
    pnUtList.cpp
    pnUtMisc.cpp
    pnUtStr.cpp
    pnUtTime.cpp
)

if(WIN32)
    set(pnUtils_WIN32
        Win32/pnUtW32Misc.cpp
    )
endif(WIN32)

add_library(pnUtils STATIC ${pnUtils_HEADERS} ${pnUtils_SOURCES} ${pnUtils_WIN32})

source_group("Header Files" FILES ${pnUtils_HEADERS})
source_group("Source Files" FILES ${pnUtils_SOURCES})
if(WIN32)
    source_group("Win32" FILES ${pnUtils_WIN32})
endif(WIN32)
