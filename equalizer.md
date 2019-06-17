# Equalizer

![equalizer](https://blokas.io/images/midihub/pipes/equalizer.svg)

A modifier pipe that amplifies the Velocity parameter of MIDI Note On messages, based on the MIDI Note number and a 3 band Eq curve.

The low band is at C1 (note 24), the mid band is at C4 (note 60, Middle C), the high band is at C7 (note 96).

See the preview at the bottom of the the Properties panel to see how the curve looks like.

| Parameter              | Description                                              |
| ---------------------- | -------------------------------------------------------- |
| Bypass                 | Whether processing is enabled.                           |
| Low                    | The gain to apply to the incoming velocity at this band. |
| Medium                 | Same as above.                                           |
| High                   | Same as above.                                           |

[List of Pipes](index.md#the-list-of-pipes)
