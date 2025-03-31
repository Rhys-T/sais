cmake_minimum_required(VERSION 3.6)

project(MY_APP)

find_library(SDL2 SDL2)
find_library(SDL2MIXER SDL2_mixer)

include_directories(${CMAKE_SOURCE_DIR}/SDL_mixer/include)
include_directories(${CMAKE_SOURCE_DIR}/physfs/src)

add_library(main SHARED)

set(SAIS_ROOT_DIR ${CMAKE_SOURCE_DIR}/../../..)

# target_sources(main PRIVATE YourSourceHere.c)
target_sources(main PRIVATE
	${SAIS_ROOT_DIR}/src/cards.cpp
	${SAIS_ROOT_DIR}/src/combat.cpp
	${SAIS_ROOT_DIR}/src/combat_display.cpp
	${SAIS_ROOT_DIR}/src/combat_init.cpp
	${SAIS_ROOT_DIR}/src/combat_sim.cpp
	${SAIS_ROOT_DIR}/src/combat_weapons.cpp
	${SAIS_ROOT_DIR}/src/endgame.cpp
	${SAIS_ROOT_DIR}/src/font.cpp
	${SAIS_ROOT_DIR}/src/gfx.cpp
	${SAIS_ROOT_DIR}/src/interface.cpp
	${SAIS_ROOT_DIR}/src/is_fileio.cpp
	${SAIS_ROOT_DIR}/src/main.cpp
	${SAIS_ROOT_DIR}/src/modconfig.cpp
	${SAIS_ROOT_DIR}/src/physfsrwops.c
	${SAIS_ROOT_DIR}/src/sdl_iface.cpp
	${SAIS_ROOT_DIR}/src/sdl_main.cpp
	${SAIS_ROOT_DIR}/src/sound.cpp
	${SAIS_ROOT_DIR}/src/sprites.cpp
	${SAIS_ROOT_DIR}/src/starmap.cpp
	${SAIS_ROOT_DIR}/src/starmap_encounters.cpp
	${SAIS_ROOT_DIR}/src/starmap_init.cpp
	${SAIS_ROOT_DIR}/src/starmap_inventory.cpp
	${SAIS_ROOT_DIR}/src/startgame.cpp
	${SAIS_ROOT_DIR}/src/textstr.cpp
	${SAIS_ROOT_DIR}/src/w32_gfx.cpp
	${SAIS_ROOT_DIR}/src/w32_sound.cpp
	${SAIS_ROOT_DIR}/src/safe_cstr.h
	${SAIS_ROOT_DIR}/src/port.h
	${SAIS_ROOT_DIR}/src/portable/safe_cstr.cpp
	${SAIS_ROOT_DIR}/src/portable/abort.cpp
)

target_link_libraries(main SDL2)
target_link_libraries(main SDL2_mixer)
target_link_libraries(main physfs)


