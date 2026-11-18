# Note Repeater

![note_repeater](https://blokas.io/images/midihub/pipes/repeater.svg)

A modifier pipe that repeats every note held down at the given rate, using the velocity of the last note held down or aftertouch.
Swing and accent can be applied to the produced notes. The notes produced are quantized to the tempo, so **MIDI Clock messages must
reach this pipe** for it to be able to do its work. The notes are produced only on the quantization grid.

| Parameter              | Description                        |
| ---------------------- | ---------------------------------- |
| Bypass                 | Whether processing is enabled.     |
| Time Division          | The quantization time.             |
| Note Length            | The length of the notes, synced to grid or in milliseconds.  |
| Quantize Note Ends     | Whether to snap the note ends to beat grid |
| Swing                  | The amount of swing to apply to odd notes. |
| Accent                 | The amount to accent every 2nd note. |

<span class="blokas-web-hide">

[List of Pipes](quick-links.md#io-pipes)

</span>