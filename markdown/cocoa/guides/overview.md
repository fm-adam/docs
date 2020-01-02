# iOS
## Starting a Cocoa Project

If you are starting an iOS project, create a new XCode project. Add the LiveSwitch libraries to your project in Xcode - they are the files under iOS/Libraries. You should include, at minimum, the following:

-   libFMLiveSwitch.a
-   libFMLiveSwitchOpus.a
-   libFMLiveSwitchVpx.a
-   libFMLiveSwitchYuv.a

As with other project types, you will also need some way to capture audio and video data. LiveSwitch provides a module to handle this. Include:

-   libFMLiveSwitchCocoa.a

Your project also needs some Apple framework dependencies. Include the following frameworks:

-   libz.dylib
-   AudioToolbox.framework
-   AVFoundation.framework
-   CoreAudio.framework
-   CoreGraphics.framework
-   CoreMedia.framework
-   CoreVideo.framework
-   CFNetwork.framework
-   GLKit.framework
-   OpenGLES.framework
-   Security.framework
-   VideoToolbox.framework

After you have added these dependencies, the last thing to do is to add `-ObjC` linker flag. If you do not do this, you will get load errors at run time. You can add this under the "Other Linker Flags" section under the build settings for your current build target.

Note that we _previously_ recommended that you also add the `-all_load` linker flag. This is _no longer_ the case. **Do not** add the `-all_load` flag, as it can result in duplicate symbol definitions.
