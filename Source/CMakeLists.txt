cmake_minimum_required (VERSION 3.0)

project(ziplib)

add_library(${PROJECT_NAME} STATIC
	ZipLib/ZipArchive.cpp
	ZipLib/ZipArchiveEntry.cpp
	ZipLib/ZipFile.cpp
	ZipLib/detail/EndOfCentralDirectoryBlock.cpp
	ZipLib/detail/ZipCentralDirectoryFileHeader.cpp
	ZipLib/detail/ZipGenericExtraField.cpp
	ZipLib/detail/ZipLocalFileHeader.cpp)

target_link_libraries(${PROJECT_NAME} zlibstatic)

target_include_directories(${PROJECT_NAME} PUBLIC ${PROJECT_SOURCE_DIR})
