cmake_minimum_required (VERSION 3.0)

project(ziplib)

add_library(${PROJECT_NAME} STATIC
	ZipArchive.cpp
	ZipArchiveEntry.cpp
	ZipFile.cpp
	detail/EndOfCentralDirectoryBlock.cpp
	detail/ZipCentralDirectoryFileHeader.cpp
	detail/ZipGenericExtraField.cpp
	detail/ZipLocalFileHeader.cpp)

target_link_libraries(${PROJECT_NAME} zlibstatic)

target_include_directories(${PROJECT_NAME} PUBLIC ${PROJECT_SOURCE_DIR})
