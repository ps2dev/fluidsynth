Xcode project file for building the static lib for iOS.

It uses SDL2 for audio output and was tested with the iOS port of Exult (http://exult.info).

But it doesn't build SDL2 on its own although it looks in ./../SDL/include for the SDL.h header file.

That's why there are two Xcode projects:

FluidSynth.xcodeproj: for when your app already uses and provides/builds SDL2.

FluidSynthSDL2dependency.xcodeproj: for when your app does *NOT* provide/build SDL2.
This also requires SDL sources to be in ./../SDL (make sure it'S the SDL2 branch if you use SDL's git)

These projects only support SF2 soundfonts. SF3 support would necessitate building libsndfile and its 
dependencies ogg/vorbis, opus and Flac. With a little work, this could be possible.
DLS support would require libinstpatch which is dependent on GLib/GObject which makes it not possible.

ToDo:
  - the header files fluidsynth.h and version.h are currently generated with hardcoded values
  - config.h is pre-generated in the project folder