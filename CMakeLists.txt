
cmake_minimum_required(VERSION 2.8)
project(synthi)

find_package(SDL)
find_package(SDL_image)
find_package(SDL_ttf)
find_package(SDL_mixer)
#find_package(Ruby)
find_package(ZLIB)
find_package(OpenGL)
find_package(PNG)
#FIND_PACKAGE(SWIG REQUIRED)

if ( NOT SDL_FOUND )
   message ( FATAL_ERROR "Make sure that SDL is installed" )
endif ( NOT SDL_FOUND )

link_libraries (
   ${SDL_LIBRARY}
   ${SDLIMAGE_LIBRARY}
   ${SDLMIXER_LIBRARY}
   ${SDLTTF_LIBRARY}
   SDLmain
   ${ZLIB_LIBRARY}
#   ${RUBY_LIBRARY}
   ${PNG_LIBRAY}
   ${OPENGL_gl_LIBRARY}
   ${OPENGL_glu_LIBRARY}
)
include_directories(${SDL_INCLUDE_DIR}
  ${CMAKE_CURRENT_SOURCE_DIR} 
  #  ${CMAKE_CURRENT_SOURCE_DIR}/lib
  #${CMAKE_CURRENT_SOURCE_DIR}/lib/gui
  #${CMAKE_CURRENT_SOURCE_DIR}/lib/sound
  #  #${CMAKE_CURRENT_SOURCE_DIR}/lib/3dengine
  #${CMAKE_CURRENT_SOURCE_DIR}/lib/game
  #${CMAKE_CURRENT_SOURCE_DIR}/lib/game/entities
  #${CMAKE_CURRENT_SOURCE_DIR}/lib/game/hljobs
  #${CMAKE_CURRENT_SOURCE_DIR}/lib/game/players
  #${CMAKE_CURRENT_SOURCE_DIR}/lib/game/formations
  #${CMAKE_CURRENT_SOURCE_DIR}/lib/game/path
  #${CMAKE_CURRENT_SOURCE_DIR}/lib/game/widgets
)


add_executable(synthi test.cc)

