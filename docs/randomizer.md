# Randomizer

![random](https://blokas.io/images/midihub/pipes/random.svg)

A modifier pipe that randomly modulates the selected parameter of incoming MIDI notes or CC values.

| Parameter              | Description                                                  |
| ---------------------- | ------------------------------------------------------------ |
| Bypass                 | Whether processing is enabled.                               |
| Parameter              | The parameter to randomize.                                  |
| Positive               | The max depth to offset the value in the positive direction. |
| Negative               | The max depth to offset the value in the negative direction. |
| CC                     | The CC id to work with, if CC Value parameter is selected.   |
| Steps per Octave | Number of note-number steps in each random octave shift, from **1 to 16**; default **12**. Applies only when **Parameter** is **Pitch (octaves)**. Between [Note to Degree and Degree to Note](note-degree.md), match their **Degree Count** (for example, **7** for major or minor). |

<span class="blokas-web-hide">

[List of Pipes](quick-links.md#io-pipes)

</span>