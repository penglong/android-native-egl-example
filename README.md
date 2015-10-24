Purpose
=======
- Use Android Studio to build Java with native C/C++ for OpenGL rendering
- Use Android Studio to debug/breakpoint both Java and native C/C++

This project is forked and based on tsaarni/android-native-egl-example,
which demonstrate how to combine Java with native C/C++ for OpenGL
rendering and is an interesting and useful use case.

New files such as build.gradle are added. The files structure is also
changed which is not necessary but makes things simpler.

It's tested with both Android Studio 1.4, and Android Studio 1.5 preview 2

* Refer to the link to understand Gradle’s new component model mechanism
http://tools.android.com/tech-docs/new-build-system/gradle-experimental

* To debug native code in Android Studio:
- Go to Run->Edit configurations.
- Click the + sign.
- Choose 'Android Native' as the configuration type.
- In the Module dropdown choose your app's module.
- Add breakpoints to your C/C++ code.
- Run->Debug...


Android Native EGL example
==========================

This project demonstrates how to combine Java application with native
C/C++ code for OpenGL rendering on Android 2.3 and newer.  It shows
how to do rendering without GLSurfaceView and GLSurfaceView.Renderer
Java classes.  The solution gives full control of the rendering for
the native code while still allowing the convenience of using Java for
calling Android APIs.

Java part of the sample application is responsible for the main UI and
application lifecycle.  It creates empty SurfaceView and passes that
to the native code.  Native code uses that for OpenGL rendering.  The
application is running standard Java activity and not the
NativeActivity.

Native code starts a new thread using pthreads API to execute
rendering code.  It uses EGL API to set up rendering context for the
thread.

![screenshot](http://i.imgur.com/qTfiE.png)

Requirements
------------

Android API level 9 and Android NDK r5 


Acknowledgments
---------------

The EGL setup code was adapted from Android NDK native-activity sample.

The OpenGL cube was adapted from Android SDK Graphics ApiDemos.

