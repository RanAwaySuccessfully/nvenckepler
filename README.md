# NVENC Kepler Plugin

## Introduction

This is pretty much a copy-paste of the existing [obs-nvenc plugin](https://github.com/obsproject/obs-studio/tree/master/plugins/obs-nvenc) that comes bundled with OBS Studio adapted to still be compatible with Kepler cards. This required a downgrade to remove features introduced after NVIDIA Video Codec SDK v11.1 such as AV1 support and split encoding removed (although they have been removed quite hastily and as such, some non-functional leftovers may still be found here and there).

If you want to use NVENC on OBS Studio 31 and above on an older Nvidia graphics card, this plugin is for you.

This plugin has been adapted to use the [official plugin template](https://github.com/obsproject/obs-plugintemplate), but it is very much a non-official plugin.

**NOTE:** Currently, NVENC detection is non-functional, so the option to select NVENC as an encoder will always show up regardless of proper hardware support. This should be fixed in a future release.

## How to install

Grab the most recent release from the Releases section and download the one appropriate for your platform.

### How to build manually

Make sure you have an appropriate version of `obs-studio` and `libobs` installed.

Run the following commands. Change `ubuntu-x86_64` to `windows-x64` if making a windows build.

```
cmake --preset ubuntu-x86_64
cmake --build --preset ubuntu-x86_64
```

Once the commands finish, open the `build_x86_64` folder to see nvenckepler.so or nvenckepler.dll there.

If using a non-Ubuntu based Linux, you can try the same preset as Ubuntu and see if it works. If it doesn't, you'll likely have to tinker around with the CMake settings until it works.

## Why

Mostly because I had a spare Kepler card I kept as a secondary/tertiary graphics card and while using it is more of a novelty than anything else, I still want NVENC to be available with it in the future. Providing support for these cards is unlikely to get any easier with time, and I don't plan on doing anything other than the extreme basics with this plugin (pull requests are more than welcome though).

Do note that using this plugin is only a solution if you are OK and able to keep an older NVIDIA driver installed, which may become more difficult with newer operating system updates and releases.

If Nouveau had video encoding support via VA-API I wouldn't even have bothered with this plugin, but they only have decoding support, and only up until Kepler. NVENC is listed on a TODO list with a "Hard" difficulty attached to it, so I imagine this is not going to be ready anytime soon.