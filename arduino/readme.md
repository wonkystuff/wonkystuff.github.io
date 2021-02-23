# Arduino Integration

This is the page containing information about the Arduino integration (board manager)
packages in order to program the _Core1_ board directly from the Arduino IDE.

## Pre-requisites

* **Arduino IDE version 1.6 or greater** - we recommend using the latest version - development has been done using version 1.8.13;
* **Java installed** (version tbc) - the audio-uploader is written in Java so this should be present.
  
## Installation

See [How to add boards in the board manager](https://support.arduino.cc/hc/en-us/articles/360016119519-How-to-add-boards-in-the-board-manager)

The wonkystuff _Boards Manager JSON file_ can be found here:

```
  https://wonkystuff-uk.github.io/arduino/package_wonkystuffPlatform_index.json
```

## Version History

* **0.0.1** Initial version. `hex2wav.jar` has been compiled with a recent version of Java, so may not work on all platforms (`java.lang.UnsupportedClassVersionError`) - this will be addressed in the next version.

Please raise any issues on the [issue tracker](https://github.com/wonkystuff-uk/wonkystuff-uk.github.io/issues)!
