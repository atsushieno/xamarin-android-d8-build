# d8 or r8 compiler support for Xamarin.Android

Xamarin.Android as of b84de80 (which should be in d15-5) makes it possible
to alter Dex tool path and arguments enough to switch to new D8 dex compiler
in release mode, and e25f843 makes it possible to do it in debug mode.

It is simply done by setting MSBuild properties: DxJarPath and DxExtraArguments
(the latter is new in d15-5, so it won't be usable in d15-4 or earlier).

There is a NuGet package that you can just install and add to your
Android application project:
https://github.com/atsushieno/xamarin-android-d8-build

r8 sources can be found at https://r8.googlesource.com/r8

The LICENSE file is only for r8 itself. I don't believe the rest of this
project contains any creative source to make it copyrightable.

## r8 or d8?

Both of them are packaged in the NuGet package above, and it is just a
matter of which `DxJarPath` MSBuild property points to. But basically, r8
is a proguard replacement so it will run linking steps too.
Add `<DesugarWithR8>true</DesugarWithR8>` in your `.csproj` to use r8.


