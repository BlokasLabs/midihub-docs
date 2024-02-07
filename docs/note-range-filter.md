# Note Range Filter

![note_r_filter](https://blokas.io/images/midihub/pipes/note_r_filter.svg)

A modifier pipe that can discard or keep MIDI Note On and Note Off events in the desired ranges.

Both ends of the ranges are inclusive.

A single pipe can store up to 9 argument values which are shared for the interval ranges, as well as
single values. In case of running out of space, a tooltip regarding it will get shown.
If you'd like to define more ranges, just put multiple Range Filter pipes in series.

## Example Ranges

Filter out first 3 octaves, the 5th and 6th octaves, and C# in the 8th octave, using MIDI Note Numbers:

0-47, 60-83, 97

The same can be written using note letters and octave number, where C4 is Note 60 (Middle C):

C-1-B2, C4-B5, C#7

| Parameter              | Description                    |
| ---------------------- | ------------------------------ |
| Bypass                 | Whether processing is enabled. |
| Drop in range          | Whether to drop messages within any of the ranges. Disabling this would inverse the operation and make it keep messages within the ranges. |
| Ranges                 | A list of interval ranges and single values. See above for examples. |

<span class="blokas-web-hide">

[List of Pipes](quick-links.md#io-pipes)

</span>