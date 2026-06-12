# TLC5947 SplitLatch

TLC5947 SplitLatch is an unofficial fork of Adafruit_TLC5947. It keeps the
original `Adafruit_TLC5947` class and `write()` behavior for sketch
compatibility, and adds separate shift and latch operations for applications
that need to preload PWM frames before updating outputs.

This fork is not endorsed by Adafruit.

## Added API

- `writeWithoutLatch()` shifts PWM data to the connected TLC5947 drivers without
  updating the outputs.
- `latch()` updates the TLC5947 outputs from data that was already shifted.
- `write()` remains available and now calls `writeWithoutLatch()` followed by
  `latch()`.

## Installation

Until this fork is published through a package index, install it as a local
Arduino library from this repository.

Sketches should continue to include the original header name:

```cpp
#include <Adafruit_TLC5947.h>
```

## License

This project is licensed under the BSD-3-Clause license. See `license.txt`.

Original library:

Copyright (c) 2012, Adafruit Industries. Written by Limor Fried/Ladyada for
Adafruit Industries.

SplitLatch modifications:

Copyright (c) 2026, Patrick Scruggs.

## Upstream Attribution

The following upstream attribution text is preserved from Adafruit_TLC5947:

This is a library for our Adafruit 24-channel PWM/LED driver

Tested and works great with the Adafruit TLC5947

* http://www.adafruit.com/products/1429

These drivers uses SPI to communicate, 3 pins are required to interface: Data,
Clock and Latch. The boards are chainable

Adafruit invests time and resources providing this open source code, please
support Adafruit and open-source hardware by purchasing products from Adafruit!

Written by Limor Fried/Ladyada for Adafruit Industries.

BSD license, check license.txt for more information All text above must be
included in any redistribution
