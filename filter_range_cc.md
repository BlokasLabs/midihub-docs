# CC Range Filter

![cc_r_filter](https://blokas.io/images/midihub/pipes/cc_r_filter.svg)

A modifier pipe that can discard or keep MIDI CC events in the desired ranges.

Both ends of the ranges are inclusive.

A single pipe can store up to 9 argument values which are shared for the interval ranges, as well as
single values. In case of running out of space, a tooltip regarding it will get shown.
If you'd like to define more ranges, just put multiple Range Filter pipes in series.

## Example Range

Filter Mod Wheel MSB and LSB, and Channel Mode messages:

1, 33, 120-127

| Parameter              | Description                    |
| ---------------------- | ------------------------------ |
| Bypass                 | Whether processing is enabled. |
| Drop in range          | Whether to drop messages within any of the ranges. Disabling this would inverse the operation and make it keep messages within the ranges. |
| Ranges                 | A list of interval ranges and single values. See above for examples. |

<span class="blokas-web-hide">

[List of Pipes](index.md#the-list-of-pipes)

</span>