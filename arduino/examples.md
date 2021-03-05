# Examples / tutorial

The arduino board-manager package comes with some example
sketches to show how to get started. With the Core1 board
selected, they should appear in the
`File`->`Examples`->`WonkystuffCore1` menu.

After going through these, it's now up to you! We'd
love to see what you come up with…

If things aren't clear, then please let us know either via email
or by raising a ticket on the
[issue tracker](https://github.com/wonkystuff/wonkystuff.github.io/issues)

## Blink

This is the simplest program that you can run on the Core1. All it
does is flash the LED every other second - there is no audio output.
It is very similar to the 'blink' program that you may have used
with an Arduino Uno or Nano, and it has the same structure:

- a `setup` function which tells the ATtiny that there will be
  output on the LED pin; and
- a `loop` function which is called repeatedly as long as power
  is available.

This program is handy also for testing that your environment is
set up correctly and you're able to reprogram the Core1.

Since we are only concerned with switching the LED on and off,
and are not too bothered about speed, we are using the standard
arduino `digitalWrite` functions. More about output later!

## Variable blink

This sketch extends the _Blink_ sketch, adding some control over
the *rate* that the LED flashes. Knob `II` on the Core1 is used to
change the amount of time that the LED is lit, whilst knob `III`
changes the amount of time that the LED is dark.

> Analogue controls can be read using the standard Arduino
> `analogRead` function, which reads the position (resistance) of
> the knob.

Controls are read within the `loop` function — for example:

`uint16_t del = analogRead(A1);`

Here the value of the knob is read into the 16-bit variable `del`.
The value is then used in the `delay` function to set the flash
rate. Note that the range of values that can be read is 0-1023,
and the delay function works in microseconds - so the range of
LED flashing will be from always-on when `del` is zero to just
over a second (1.023) when the knob is at its maximum.

## SimpleSquare

Now we've got an understanding of the basics of programming
the Core1, we can start to make some sounds! There are a few
extra steps to this because sound waves oscillate very quickly,
so the code to generate it *also* has to run quickly. Luckily
the ATTiny processor that the Core1 uses is plenty quick enough
to do this if we are careful about what we do and how we do it.

> Having said that, the ATTiny is only a small, 8-bit processor,
> we're not going to be doing anything complex like realistic
> reverb algorithms, or huge symphonic pad sounds - Sorry!

We'll do this by making use of some special software tools to
make this as simple as possible. The *big* change is the addition
of another function called `wsAudioLoop`, which you can think of
as a very fast version of the `loop` function described above.
This is set up to run 20000 times per second (i.e. the
_sampling rate_ is 20kHz). To work properly and predictably,
the `wsAudioLoop` function must finish within 50 microseconds
(µs) so that the processor has time to attend to the operations
in the `loop` function as well. Think of `wsAudioLoop` as
changing the position of the loudspeaker cone every time it
runs.

If you glance over the `SimpleSquare` sketch you'll see some
extra lines of code that we didn't need for the blinking LED
sketches above:

- `#include "wonkystuffCommon.h"` pulls in the
  extra functions that we'll need to build the program;
- `wsInit()` performs any setup that is required for the
  wonkystuff APIs, so we can use it for making noise;
- `wsInitAudioLoop(20000)` is used to specify how quickly
  `wsAudioLoop` is run. `20000` is the required sample rate
  specified in executions-per-second (Hz). The maximum
  sample rate is 65535 Hz.
- `wsPinSet` and `wsPinClear` functions are used to write
  'high' and 'low' to the outputs respectively. These are
  used instead of the arduino `digitalWrite` APIs because
  we're basically control freaks. Sorry 'bout that.

The code within `wsAudioLoop` continually increments a
variable `phase` which acts as a _phase accumulator_, the
amount that it is incremented by depends on the value of
the front panel control. `phase` runs from 0 to 65535, and
then starts again, like a ramp waveform. The code simply
looks at the value of the ramp, setting both outputs
'high' if the phase is larger than the midpoint, and
'low' otherwise (this gives us a square wave with equally-
sized high and low parts).

_A note about `wonkystuffCommon.h`_:
> `wonkystuffCommon.h` is intended to contain some useful
> definitions as well as APIs. For example we have defined
> some identifiers to make reading the analogue controls a
> bit more readable (use `wsKnob1` to `wsKnob4` instead of
> `A0` to `A3`). This API will get some proper documentation
> at some point!
