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
| Data Source 1          | The data source to use for the transformed event's first data byte. Applicable to Note On, Note Off, Control Change, Poly Aftertouch, Program Change and Channel Pressure messages. |
| Data Source 2          | The data source to use for the transformed event's second data byte. Applicable to Note On, Note Off, Control Change and Poly Aftertouch messages. |
| Argument 1             | The number to use, in case it's selected by Data Source parameter. |
| Argument 2             | The number to use, in case it's selected by Data Source parameter. |
| Prioritize Real-Time   | Whether the Real Time messages produced should be prioritized. If off, logical order of the messages is retained. |

<span class="blokas-web-hide">

[List of Pipes](index.md#the-list-of-pipes)

</span>