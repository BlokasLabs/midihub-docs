# Transform

![transform](https://blokas.io/images/midihub/pipes/transform.svg)

A modifier pipe that transforms particular kind of MIDI messages into the desired kind of MIDI message.

It can convert between these message types:

* Note On
* Note Off
* Note On & Note Off (useful when remapping the note number)
* Control Change
* Program Change
* Poly Aftertouch
* Channel Pressure
* Pitch Bend
* Start
* Continue
* Stop
* Song Position Pointer
* Song Select
* Tune Request
* Clock
* Active Sense
* Reset

| Parameter              | Description                                              |
| ---------------------- | -------------------------------------------------------- |
| Bypass                 | Whether processing is enabled.                           |
| Mode                   | The mode sets whether the transformed message should be inserted before the original event, after it, replace it, or drop the event. |
| What                   | Selects the MIDI message kind to convert.                |
| Into                   | Defines which message to transform it to.                |
| [Value for Byte 1]     | The name of this parameter depends on the Into parameter. It may be set to use the values from Argument 1 or Argument 2 parameters, or to use a value from the message being transformed, depending on the What parameter. |
| [Value for Byte 2]     | Same as above. |
| Argument 1             | The number to use, in case it's selected by [Value for Byte 1] parameter. |
| Argument 2             | The number to use, in case it's selected by [Value for Byte 2] parameter. |
| Prioritize Real-Time   | Whether the Real Time messages produced should be prioritized. If off, logical order of the messages is retained. |
| Work with Channel      | Which channel to process (channel messages only).        |
| Work with Any Channel  | Whether to ignore the above parameter and process all messages. |
| Set Channel To         | What channel to set (channel messages only).             |
| Keep Channel           | Whether to ignore the above parameter and keep original channel. |
| Work with [...] in Range Low | The lower data range bound of first data byte to trigger processing on. |
| Work with [...] in Range High | The higher data range bound of first data byte to trigger processing on. |
| Use [...]	Inside/Outside Range | Whether to trigger processing on data values inclusively within the range defined by above parameters, or exclusively outside the range. |
| Work with [...] in Range Low | Same as above, but for second data byte. |
| Work with [...] in Range High | Same as above, but for second data byte. |
| Use [...]	Inside/Outside Range | Same as above, but for second data byte. |


<span class="blokas-web-hide">

[List of Pipes](index.md#the-list-of-pipes)

</span>