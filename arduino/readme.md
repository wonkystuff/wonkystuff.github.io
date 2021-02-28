# Arduino Integration

If you would like to write your own code for the _**Core1**_ using the
Arduino programming environment (IDE), then you're going to need
to install some stuff.

This assumes that you're using **Arduino IDE version 1.6 or greater** -
if you're not then none of this will make sense and you should stop here
to preserve your sanity. We recommend using the latest version - our development
has been done using version 1.8.13;

## Installation

In order to integrate the _**Core1**_ hardware you'll need a URL to paste into
the preferences file. If you copy it now, then you can follow the instructions
after the link and paste it in.

The wonkystuff _Boards Manager JSON URL_ is:

```
  https://wonkystuff-uk.github.io/arduino/package_wonkystuffPlatform_index.json
```

Here are instructions on [how to add 3rd party hardware to the Arduino IDE](https://support.arduino.cc/hc/en-us/articles/360016466340-How-to-add-3rd-party-hardware-in-the-Arduino-IDE){:target="_blank" rel="noopener"}

Once you've added the URL to the preferences page, you'll need to install
the wonkystuff board package.

In the Arduino IDE, select `Tools` -> `Board <something>` -> `Boards Manager…`

At the top of that window, type _wonkystuff_ into the _filter_ text box. You should
now see **Wonkystuff Core1** - click on the text and then click the `install` button.

After a short-ish time, this should be done and the boards manager window can be closed.

Now in the Arduino IDE, select `Tools` -> `Board <something>` -> `wonkystuff boards` -> `Core1.D (audio bootloader)`

That's it. With a test sketch (empty, or blink for example), click upload and the
program should compile and then play the generated code through your computer
speakers.

## Programming the Core1 board

Programming the _Core1_ board is intended to be straightforward - lets see.

You will need:

* _Core1_ board (and battery pack);
* A computer with a headphone output;
* A 3.5mm jack-to-jack cable;

1. Connect the audio output of the computer to the audio input of the _Core1_
   using the 3.5mm jack-to-jack cable;
1. Switch on the Core1 (connect battery first of course);
1. Adjust the 4th control knob (marked IV) to around its middle position;
1. Press and hold the **RESET** button - the LED will light;
1. Hold the **RESET** button until the LED goes out. The _Core1_ is now listening
   out for a program to be downloaded to it.
1. Click on _Upload_ from the Arduino IDE. The code will compile and then will
   play the code into the _Core1_.
   - whilst the uploading is running, the LED should flash quickly until the
     upload is complete.

That's it! It may be that you need to play with the volume control on your
computer until the code is read - you might need to restart from stage 4
until you achieve success.

# Examples

Here we will add some examples as audio files which you can download and program
into your Core1.

## dr1a

This is the base software for the Core1 Rev.C, translated into audio format!

[Download Here](./dr1a.ino.wav)

# Version History

* **0.0.1** Initial version. `hex2wav.jar` has been compiled with a recent version of Java, so may not work on all platforms (`java.lang.UnsupportedClassVersionError`) - this will be addressed in the next version.
* **0.0.2** _BUGFIX_ `hex2wav.jar` has been recompiled to target JRE8.
* **0.0.3** _BUGFIX_ Upload works even if no programmer is selected.
* **0.0.4** Added a couple of simple examples to check functionality.
* **0.0.5** `Export Compiled Binary` now generates a `wav` file alongside the output hex.
* **0.0.6** Improved the `hex2wav` file so that when exporting a `wav` file it's not
  played. Also appear to have re-introduced the bug when no programmer is selected.
  Workaround is to set the programmer in the Tools menu.

Please raise any issues on the [issue tracker](https://github.com/wonkystuff-uk/wonkystuff-uk.github.io/issues)!

