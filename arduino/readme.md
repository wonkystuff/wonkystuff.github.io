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

Now in the Arduino IDE, select `Tools` -> `Board <something>` -> `wonkystuff boards`

That's it. With a test sketch (empty, or blink for example), click upload and the
program should compile and then play the generated code through your computer
speakers.

## Programming the Core1 board

`<TODO>`

# Version History

* **0.0.1** Initial version. `hex2wav.jar` has been compiled with a recent version of Java, so may not work on all platforms (`java.lang.UnsupportedClassVersionError`) - this will be addressed in the next version.
* **0.0.2** _BUGFIX_ `hex2wav.jar` has been recompiled to target JRE8.
* **0.0.3** _BUGFIX_ Upload works even if no programmer is selected.

Please raise any issues on the [issue tracker](https://github.com/wonkystuff-uk/wonkystuff-uk.github.io/issues)!
