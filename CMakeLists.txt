cmake_minimum_required (VERSION 3.0)

project(ziplib)

add_library(${PROJECT_NAME} STATIC
	Source/ZipLib/ZipArchive.cpp
	Source/ZipLib/ZipArchiveEntry.cpp
	Source/ZipLib/ZipFile.cpp
	Source/ZipLib/detail/EndOfCentralDirectoryBlock.cpp
	Source/ZipLib/detail/ZipCentralDirectoryFileHeader.cpp
	Source/ZipLib/detail/ZipGenericExtraField.cpp
	Source/ZipLib/detail/ZipLocalFileHeader.cpp)

if(ZLIB_USE_STATIC_LIBS)
	target_link_libraries(${PROJECT_NAME} zlibstatic)
else()
	target_link_libraries(${PROJECT_NAME} zlib)
endif()

target_include_directories(${PROJECT_NAME} PUBLIC ${PROJECT_SOURCE_DIR}/Source)
