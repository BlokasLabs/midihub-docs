# Equalizer

![equalizer](https://blokas.io/images/midihub/pipes/equalizer.svg)

A modifier pipe that applies a 3 band Eq curve on message values indicated by the Kind parameter.

The 3 bands are located at these positions:

| Band           | Low | Medium | High |
| -------------- | --- | ------ | ---- |
| Number         | 24  | 60     | 96   |
| Middle C3 std. | C0  | C3     | C6   |
| Middle C4 std. | C1  | C4     | C7   |
| Middle C5 std. | C2  | C5     | C8   |

See the preview at the bottom of the the Properties panel to see how the curve looks like.

| Parameter              | Description                                              |
| ---------------------- | -------------------------------------------------------- |
| Bypass                 | Whether processing is enabled.                           |
| Low                    | The gain to apply to the incoming velocity at this band. |
| Medium                 | Same as above.                                           |
| High                   | Same as above.                                           |
| Kind                   | Selects the MIDI message kind to process. **Velocity (Note #)** modifies the velocity of the notes based on the note number. The other kinds apply the curve on the value based on itself. |
| Any Id / Channel ?     | Depending on the Kind parameter, whether to affect MIDI messages with any Id (for messages that have a Note or CC number) or Channel (Pitch Bend and Channel Pressure). |
| Id / Channel           | The particular Id or Channel to affect, if **Any Id / Channel** parameter is off. This allows chaining multiple Equalizer pipes in a single pipeline as well as intermixing with other pipes. |

<span class="blokas-web-hide">

[List of Pipes](index.md#the-list-of-pipes)

</span>