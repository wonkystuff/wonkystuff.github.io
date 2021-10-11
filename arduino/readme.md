# Arduino Integration

If you would like to write your own code for the _**Core1**_ using the
Arduino programming environment (IDE), then you're going to need
to install some stuff.

This assumes that you're using **Arduino IDE version 1.6 or greater** -
if you're not then none of this will make sense and you should stop here
to preserve your sanity. We recommend using the latest version - our development
has been done using version 1.8.13.

We have split this page into sections to make it a bit more digestible, feel
free to skip the parts you already know!

- **[Installation](./installation.md)** describes how to install the Core1
  board manager package into your Arduino IDE;
- **[Programming the Core1 board](./programming.md)** describes the procedure
  for reprogramming the Core1 via the _audio input_;
- **[Tutorial/examples](./examples.md)** a tour of the examples which are
  included with the Core1 board manager package.

## Version History
* **0.1.5** Fixed misunderstanding about `delay()` and permanently disabled `millis()` _(11/10/2021)_
* **0.1.4** Fixed Karplus-Strong example _(10/10/2021)_
* **0.1.3** Added support for the _AE Modular_ version of the Core1. Added version
  of the `dr1a` code as another example as well as a simple sine-wavetable version
  of the _polyramp_ example.  _(10/10/2021)_
* **0.1.2** Split library sources into individual files; added more examples (ramp and poly);
  added first attempt at the octave-lookup calculation; Fixed typo in `#include` of `Arduino.h`;
  API changed for `wsInitAudio`; Tools menu changed to add Sample Rate selection.
* **0.1.1** Corrected _Variable Blink_ example (rolleyes). _(05/03/2021)_
* **0.1.0** Added some more examples to hopefully introduce some concepts. _(05/03/2021)_
* **0.0.6** Improved the `hex2wav` file so that when exporting a `wav` file it's not
  played. Also appear to have re-introduced the bug when no programmer is selected.
  Workaround is to set the programmer in the Tools menu.
* **0.0.5** `Export Compiled Binary` now generates a `wav` file alongside the output hex.
* **0.0.4** Added a couple of simple examples to check functionality.

* **0.0.3** _BUGFIX_ Upload works even if no programmer is selected.
* **0.0.2** _BUGFIX_ `hex2wav.jar` has been recompiled to target JRE8.
* **0.0.1** Initial version. `hex2wav.jar` has been compiled with a
  recent version of Java, so may not work on all platforms
  (`java.lang.UnsupportedClassVersionError`) - this will be addressed in the next version.

Please raise any issues on the [issue tracker](https://github.com/wonkystuff/wonkystuff.github.io/issues)!

