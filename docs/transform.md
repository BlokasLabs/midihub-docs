# Transform

![transform](https://blokas.io/images/midihub/pipes/transform.svg)

A modifier pipe that transforms particular kind of MIDI messages into the desired kind of MIDI message.

It can convert between these message types:

* Note On
* Note Off
* Control Change
* Program Change
* Poly Aftertouch
* Channel Pressure
* Start
* Continue
* Stop

| Parameter              | Description                                              |
| ---------------------- | -------------------------------------------------------- |
| Bypass                 | Whether processing is enabled.                           |
| Mode                   | The mode sets whether the transformed message should be inserted before the original event, after it or should it be completely replaced. |
| What                   | Selects the MIDI message kind to convert.                |
| Into                   | Defines which message to transform it to.                |
| [Value for Byte 1]     | The name of this parameter depends on the Into parameter. It may be set to use the values from Argument 1 or Argument 2 parameters, or to use a value from the message being transformed, depending on the What parameter. |
| [Value for Byte 2]     | Same as above |
| Argument 1             | The number to use, in case it's selected by [Value for Byte 1] parameter. |
| Argument 2             | The number to use, in case it's selected by [Value for Byte 2] parameter. |
| Prioritize Real-Time   | Whether the Real Time messages produced should be prioritized. If off, logical order of the messages is retained. |

<span class="blokas-web-hide">

[List of Pipes](index.md#the-list-of-pipes)

</span>