# Arpeggiator

![arpeggiator](https://blokas.io/images/midihub/pipes/arp.svg)

A modifier pipe that produces arpeggios using the held down notes at the given rate, using the velocity of the last note held down or aftertouch.
Swing and accent can be applied to the produced notes. The notes produced are quantized to the tempo, so **MIDI Clock messages must
reach this pipe** for it to be able to do its work. The notes only get produced on quantization grid.

The arpeggio sequences will get repeated on the next octave, according to the Octave Range parameter.

Multiple variations of note sequences can be selected:

| Type                 | Description       |
| -------------------- | ----------------- |
|  Up                  | Go up.            |
|  Down                | Go down.          |
|  Up and Down         | Go up and down.   |
|  Down and Up         | Go down and up.   |
|  Up and Down Incl.   | Go up and down, repeating the high note once. |
|  Down and Up Incl.   | Go down and up, repeating the low note once. |
|  Low Up              | Repeat the low note every 2nd time while progressing up. |
|  Low Up and Down     | Repeat the low not every 2nd time while progressing up, then down. 4 or more notes needed. |
|  High Up             | Repeat the high note every 2nd time while progressing up. |
|  High Up And Down    | Repeat the high not every 2nd time while progressing up, then down. 4 or more notes needed. |
|  Chords              | Play all the notes at once, for use with Octave parameter. |
|  Random              | Play random notes based on the held down keys and octave range. |

| Parameter              | Description                        |
| ---------------------- | ---------------------------------- |
| Bypass                 | Whether processing is enabled.     |
| Time Division          | The quantization time.             |
| Note Length            | The length of the notes, synced to grid or in milliseconds.  |
| Quantize Note Ends     | Whether to snap the note ends to beat grid |
| Swing                  | The amount of swing to apply to odd notes. |
| Accent                 | The amount to accent every 2nd note. |
| Type                   | The sequence type. See above table. |
| Octave Range           | The range of octaves to go through. |
| Repetitions            | The amount of times to repeat the same step in the arpeggio sequence. |
| Retrigger Octave       | Whether to reset the current octave to 0 when all notes are off. |

<span class="blokas-web-hide">

[List of Pipes](index.md#the-list-of-pipes)

</span>