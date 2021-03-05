# Programming the Core1 board

Programming the _Core1_ board is intended to be straightforward - lets see.

You will need:

- _Core1_ board (and battery pack);
- A computer with a headphone output;
- A 3.5mm jack-to-jack cable;

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

## Examples

Here we will add some examples as audio files which you can download and program
into your Core1.

### dr1a

This is the base software for the Core1 Rev.C, translated into audio format!

[Download Here](./dr1a.ino.wav)
