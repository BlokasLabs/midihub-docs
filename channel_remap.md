# Channel Remap

A modifier pipe that remaps the Channel number of MIDI messages that carry Channel information from given input range to the desired output range.
Any Channel messages that are outside of input range will get discarded. Using this pipe, you may route MIDI data based on the channel to other ports.

The incoming MIDI Channel messages with the channel number outside of the Input range will get discarded.

| Parameter              | Description                        |
| ---------------------- | ---------------------------------- |
| Bypass                 | Whether processing is enabled.     |
| In Low                 | The lowest value of input range.   |
| In High                | The highest value of input range.  |
| Out Low                | The lowest value of output range.  |
| Out High               | The highest value of output range. |


[List of Pipes](index.md#the-list-of-pipes)
