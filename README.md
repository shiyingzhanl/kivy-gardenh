# XCamera: Android-optimized camera widget

[![Build Status](https://travis-ci.com/kivy-garden/xcamera.svg?branch=develop)](https://travis-ci.com/kivy-garden/xcamera)
[![Coverage Status](https://coveralls.io/repos/github/kivy-garden/xcamera/badge.svg?branch=develop)](https://coveralls.io/github/kivy-garden/xcamera?branch=develop)
[![PyPI version](https://badge.fury.io/py/xcamera.svg)](https://badge.fury.io/py/xcamera)

XCamera is a widget which extends the standard Kivy Camera widget with more
functionality. In particular:

  1. it displays a "shoot button", which the user can press to take pictures

  2. on Android, it uses the native APIs to take high-quality pictures,
     including features such as auto-focus, high resolution, etc.

  3. it includes a method to force landscape mode. On Android, it is often
     desirable to switch to landscape mode when taking pictures: you can
     easily do it by calling `camera.force_landscape()`, and later
     `camera.resource_orientation()` to restore the orientation to whatever it
     was before.

Screenshot:

![screenshot](https://raw.githubusercontent.com/kivy-garden/xcamera/develop/screenshot.png?raw=True "Screenshot")

Notes:

  * On Android, the `resolution` property of the `XCamera` (and also of the
    plain `Camera`) widget controls the **preview size**: in other words, it
    only affects the quality of the preview, not the size of the pictures
    taken.

  * As it is now, the camera will shoot using the default setting for the
    picture size, which seems to be what the camera think it is "the best". In
    theory, we could add a method to retrieve the list of all possible picture
    sizes, and add a property to control it.  It would also be nice to add a
    new button to allow the user to manually select the preferred size.  Pull
    requests are welcome :)

## Install
```sh
pip install xcamera
```

## Demo
A full working demo is available in [src/kivy_garden/xcamera/main.py](https://github.com/kivy-garden/xcamera/blob/develop/src/main.py).
You can run it via:
```sh
make run
```

## Contribute
To play with the project, install system dependencies and Python requirements using the [Makefile](Makefile).
```sh
make
```
Then verify everything is OK by running tests.
```sh
make test
```
