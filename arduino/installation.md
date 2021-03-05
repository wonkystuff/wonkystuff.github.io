# Installation

In order to integrate the _**Core1**_ hardware you'll need a URL to paste into
the preferences file. If you copy it now, then you can follow the instructions
after the link and paste it in.

The wonkystuff _Boards Manager JSON URL_ is:

```
  https://wonkystuff.github.io/arduino/package_wonkystuffPlatform_index.json
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
