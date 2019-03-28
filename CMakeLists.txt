cmake_minimum_required(VERSION 3.13)
project(BrickBraker)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_MODULE_PATH ${CMAKE_MODULE_PATH} "${BrickBraker_SOURCE_DIR}/cmake")

add_executable(BrickBraker src/main.cpp src/cppfiles/Ball.cpp src/header/Ball.h src/main.cpp src/cppfiles/GameManager.cpp src/header/GameManager.h src/cppfiles/Bricks.cpp src/header/Bricks.h src/header/Brick.h src/cppfiles/InputManager.cpp src/header/InputManager.h src/cppfiles/Paddle.cpp src/header/Paddle.h)

find_package(SDL2 REQUIRED)
find_package(SDL2_image REQUIRED)
find_package(SDL2_ttf REQUIRED)

include_directories(${SDL2_INCLUDE_DIR}
        ${SDL2_IMAGE_INCLUDE_DIR}
        ${SDL2_TTF_INCLUDE_DIR})

target_link_libraries(BrickBraker
            ${SDL2_LIBRARY}
            ${SDL2_IMAGE_LIBRARIES}
            ${SDL2_TTF_LIBRARIES}
        )