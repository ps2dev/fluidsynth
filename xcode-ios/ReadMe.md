Xcode project file for building the static lib for iOS.

It uses SDL2 for audio output and was tested with the iOS port of Exult (http://exult.info).

But it doesn't build SDL2 on its own although it looks in ./../SDL/include for the SDL.h header file.

ToDo:
  - the header files fluidsynth.h and version.h are currently generated with hardcoded values
  - config.h is pre-generated in the project folder