CMAKE_MINIMUM_REQUIRED(VERSION 3.1)

SET(CMAKE_CXX_STANDARD 17)
SET(CMAKE_CXX_REQUIRED_STANDARD ON)
SET(CMAKE_DEBUG_POSTFIX "-d")

SET(PROJECT_NAME "battlemapper")
PROJECT(${PROJECT_NAME} LANGUAGES CXX)

SET(HEADERS AppEngine.hpp AppState.hpp Tilemap.hpp MapDesignerState.hpp Map.hpp)

SET(SOURCES AppEngine.cpp Tilemap.cpp MapDesignerState.cpp main.cpp)

ADD_EXECUTABLE(${PROJECT_NAME} ${HEADERS} ${SOURCES})

SET(SFUI_INCLUDE_DIR "../../SFUI/include")
SET(SFUI_LIB_DIR "../../SFUI/lib")
SET(SFML_INCLUDE_DIR "../../SFML/include")
SET(SFML_LIB_DIR "../../SFML/lib")

TARGET_INCLUDE_DIRECTORIES(${PROJECT_NAME} PUBLIC ${SFML_INCLUDE_DIR})
TARGET_LINK_LIBRARIES(${PROJECT_NAME} sfml-graphics sfml-audio sfml-window sfml-network sfml-system) # ${SFML_LIB_DIR})

TARGET_INCLUDE_DIRECTORIES(${PROJECT_NAME} PUBLIC ${SFUI_INCLUDE_DIR})
TARGET_LINK_LIBRARIES(${PROJECT_NAME} sfui) #${SFUI_LIB_DIR})

TARGET_LINK_LIBRARIES(${PROJECT_NAME} stdc++fs)
