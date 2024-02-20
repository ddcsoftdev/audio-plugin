cmake_minimum_required(VERSION 3.15)

project(MyJuceProject VERSION 0.0.1)

# Add the JUCE submodule
add_subdirectory(JUCE)

# Define your application target
juce_add_gui_app(MyApp
        PRODUCT_NAME "My JUCE Application")

# Specify the sources and headers of your app
target_sources(MyApp
        PRIVATE
        Main.cpp
        MainComponent.h
        MainComponent.cpp)

# Link against the JUCE modules you use
target_link_libraries(MyApp
        PRIVATE
        juce::juce_gui_extra)

# Set C++ standard and other compile options as needed
target_compile_features(MyApp PRIVATE cxx_std_17)
