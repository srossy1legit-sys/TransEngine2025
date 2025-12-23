# CMakeList.txt : CMake project for TransEngine, include source and define
# project specific logic here.
#
cmake_minimum_required (VERSION 3.8)

# Enable Hot Reload for MSVC compilers if supported.
if (POLICY CMP0141)
  cmake_policy(SET CMP0141 NEW)
  set(CMAKE_MSVC_DEBUG_INFORMATION_FORMAT "$<IF:$<AND:$<C_COMPILER_ID:MSVC>,$<CXX_COMPILER_ID:MSVC>>,$<$<CONFIG:Debug,RelWithDebInfo>:EditAndContinue>,$<$<CONFIG:Debug,RelWithDebInfo>:ProgramDatabase>>")
endif()

project ("TransEngine")

# Add source to this project's executable.
add_executable (TransEngine "TransEngine.cpp" "TransEngine.h"       "Binaries/ai_npc.h" "Binaries/player.h" "Binaries/ai_base.h"  "Consoles/Xbox/xbox.h" "Consoles/PS5/ps5.h" "Consoles/PS4/ps4.h" "Consoles/Nintendo Switch 2/nintendoswitch2.h" "Consoles/Nintendo Switch/nintendoswitch.h" "Consoles/Steam/steammachine.h" "Consoles/Steam/steamdeck.h" "Consoles/Steam/steamcontroller.h" "Physics/phys.h" "Core/ai_base.h")

if (CMAKE_VERSION VERSION_GREATER 3.12)
  set_property(TARGET TransEngine PROPERTY CXX_STANDARD 20)
endif()

# TODO: Add tests and install targets if needed.
