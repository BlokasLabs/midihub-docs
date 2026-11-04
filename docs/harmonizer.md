# Harmonizer

![harmon](https://blokas.io/images/midihub/pipes/harmon.svg)

A modifier pipe that upon receiving a note on message generates up to 8 additional harmonized notes according to the defined intervals.

Interval +0 (the incoming note) is played if "Play Root Note?" is enabled.

If two or more intervals are of the same value, only one note of that interval gets produced.

The produced chords can be inverted up or down by adjusting the Inversion parameter.
Adjusting the Inversion parameter beyond the number of notes harmonized creates octaves of inversions.

| Parameter              | Description                    |
| ---------------------- | ------------------------------ |
| Bypass                 | Whether processing is enabled. |
| 1st interval           | Semitones offset to the root note. |
| 2nd interval           | Same as above. |
| 3rd interval           | Same as above. |
| 4th interval           | Same as above. |
| 5th interval           | Same as above. |
| 6th interval           | Same as above. |
| 7th interval           | Same as above. |
| 8th interval           | Same as above. |
| Play Root Note?        | Whether to play the +0 root note. |
| Inversion              | The chord inversion number. |
| Steps per Octave | Number of note-number steps used for octave shifts in chord inversions, from **1 to 16**; default **12**. Between [Note to Degree and Degree to Note](note-degree.md), match their **Degree Count** (for example, **7** for major or minor). This does not rescale the interval settings. |

<span class="blokas-web-hide">

[List of Pipes](quick-links.md#io-pipes)

</span>
