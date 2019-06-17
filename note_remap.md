# Note Remap

![note_remap](https://blokas.io/images/midihub/pipes/note_remap.svg)

A modifier pipe that remaps Note On and Note Off note values from given input range to the desired output range.
Any Note On and Note Off events that are outside of input range will get discarded. Using this pipe together with
virtual inputs / outputs you can split your keyboard to control multiple devices. Or you can transpose and scale or
flip the range if you feel like experimenting.

The allowed value inputs are:

* 0 .. 127 - the MIDI note number. Note 60 is usually Middle C.
* C-1 .. G9 - alphabetic notation and octave number. C-1 is Note 0, C#-1 is Note 1, C4 is Note 60 (Middle C), G9 is 127.

The incoming MIDI Notes with the note number outside of the Input range will get discarded.

| Parameter              | Description                        |
| ---------------------- | ---------------------------------- |
| Bypass                 | Whether processing is enabled.     |
| In Low                 | The lowest value of input range.   |
| In High                | The highest value of input range.  |
| Out Low                | The lowest value of output range.  |
| Out High               | The highest value of output range. |

[List of Pipes](index.md#the-list-of-pipes)
