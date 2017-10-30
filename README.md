# d8 compiler support for Xamarin.Android

Xamarin.Android as of b84de80 (which should be in d15-5) makes it possible
to alter Dex tool path and arguments enough to switch to new D8 dex compiler.

It is simply done by setting MSBuild properties: DxJarPath and DxExtraArguments
(the latter is new in d15-5, so it won't be usable in d15-4 or earlier).

There will be a NuGet package that you can just install and add to your
Android application project.

r8 sources can be found at https://r8.googlesource.com/r8

The LICENSE file is only for r8 itself. I don't believe the rest of this
project contains any creative source to make it copyrightable.

