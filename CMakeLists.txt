# Specify the minimum version of CMake required to build this project.
cmake_minimum_required(VERSION 3.10)

# Define the project name and specify that it's a C++ project.
project(CPPRaytracer CXX)

# Set the C++ standard to C++17. This is a good modern standard with lots of
# useful features. The "REQUIRED" keyword ensures that the compiler supports it.
set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
set(CMAKE_CXX_EXTENSIONS OFF) # Disables compiler-specific extensions for better portability

# Add the executable target.
# The first argument is the name we want for our final program (e.g., "raytracer").
# The following arguments are the source files needed to build it.
# As you add more .cpp files, you will add them to this list.
add_executable(raytracer src/main.cpp)

# Optional: Add compiler warnings. This is a very good practice to catch
# potential errors early.
if(MSVC)
  # Warnings for Microsoft Visual C++ compiler
  add_compile_options(/W4 /WX)
else()
  # Warnings for GCC/Clang
  add_compile_options(-Wall -Wextra -Wpedantic -Werror)
endif()
