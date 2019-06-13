# CC Remap

A modifier pipe that remaps the CC id number from given input range to the desired output range.
Any CC messages that are outside of input range will get discarded. Using this pipe, you may remap MIDI CC ids.

The incoming MIDI CC messages with the CC id number outside of the Input range will get discarded.

| Parameter              | Description                        |
| ---------------------- | ---------------------------------- |
| Bypass                 | Whether processing is enabled.     |
| In Low                 | The lowest value of input range.   |
| In High                | The highest value of input range.  |
| Out Low                | The lowest value of output range.  |
| Out High               | The highest value of output range. |

[List of Pipes](index.md#the-list-of-pipes)
