# Limiter

A modifier pipe that limits the values of the MIDI messages it's set to work with.

The incoming values are clipped to fit in range [Minimum;Maximum].

| Parameter              | Description                                              |
| ---------------------- | -------------------------------------------------------- |
| Bypass                 | Whether processing is enabled.                           |
| Kind                   | Selects the MIDI message kind to process.                |
| Minimum                | The lowest value.                                        |
| Maximum                | The highest value.                                       |

[List of Pipes](index.md#the-list-of-pipes)
