# Channel Range Filter

![ch_r_filter](https://blokas.io/images/midihub/pipes/ch_r_filter.svg)

A modifier pipe that can discard or keep MIDI Channel events, like Note On, Note Off, CC, Program Change, and others in the desired ranges.

Both ends of the ranges are inclusive.

## Example Range

Filter out first 4 channels, channel 6 and the 8 last channels:

1-4, 6, 9-16

| Parameter              | Description                    |
| ---------------------- | ------------------------------ |
| Bypass                 | Whether processing is enabled. |
| Drop in range          | Whether to drop messages within any of the ranges. Disabling this would inverse the operation and make it keep messages within the ranges. |
| Ranges                 | A list of interval ranges and single values. See above for examples. |

[List of Pipes](index.md#the-list-of-pipes)
