cmake_minimum_required(VERSION 3.16)
project(JuceHelloWorld)

set(CMAKE_CXX_STANDARD 14)

include_directories(JuceLibraryCode)
include_directories(Source)
include_directories(modules)
#-I/usr/include/freetype2 -I/usr/include/libpng16 -I/usr/include/x86_64-linux-gnu
include_directories(/usr/include/freetype2)
include_directories(/usr/include/libpng16)
include_directories(/usr/include/x86_64-linux-gnu)

add_executable(JuceHelloWorld
        JuceLibraryCode/include_juce_core.cpp
        JuceLibraryCode/include_juce_data_structures.cpp
        JuceLibraryCode/include_juce_events.cpp
        JuceLibraryCode/include_juce_graphics.cpp
        JuceLibraryCode/include_juce_gui_basics.cpp
        Source/Main.cpp
        Source/MainComponent.cpp
        )

target_link_libraries(JuceHelloWorld -ldl)
target_link_libraries(JuceHelloWorld -lpthread)
target_link_libraries(JuceHelloWorld -lrt)
target_link_libraries(JuceHelloWorld -lX11 -lXinerama -lXext -lfreetype -lcurl)
