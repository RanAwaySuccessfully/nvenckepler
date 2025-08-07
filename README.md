# OBS - NVENC Kepler Plugin

## Introduction

This is pretty much a copy-paste of the existing [obs-nvenc plugin](https://github.com/obsproject/obs-studio/tree/master/plugins/obs-nvenc) on OBS Studio adapted to use the [plugin template](https://github.com/obsproject/obs-plugintemplate), with some features such as AV1 support and split encoding removed (due to the downgrade to using nv-codec-headers 11.1).

## Supported Platforms

| Platform  | Support   |
|-----------|--------|
| Windows   | yes |
| macOS     | i have no idea |
| Ubuntu 24.04 | absolutely |

## But why???

Honestly, because why not? Sure, eventually graphics cards get old enough, providing support for them starts to make less and less sense. But you have to admit, the idea of still making it work somehow even if unofficially is pretty cool right?

If Nouveau had video encoding support via VA-API I wouldn't even have bothered with this, but they only have decoding support, and only up until Kepler. This might increasingly become more problematic with the future discontinuation of Maxwell and Pascal graphics cards.