# CC Table

![cc_table](https://blokas.io/images/midihub/pipes/cc_table.png)

A pipe that can be placed both as a Generator (leftmost) pipe or as a Modifier (inline) pipe.
It can inject CC events into the pipeline through **MIDI mappings** or directly from the Editor.
Contrary to most of other Midihub's pipes, this pipe does not modify events passing through it.

It features a Takeover mode for the case where the same CC Value parameter is mapped to multiple knobs,
the last value from last used knob must be passed by the other mapped knob, in order take over the control.
This avoids sudden jumps when using multiple knobs.

It is recommended to map the CC n Value parameters to external controllers.

| Parameter              | Description                    |
| ---------------------- | ------------------------------ |
| Bypass                 | Whether processing is enabled. |
| Channel                | The MIDI channel of the produced events. |
| Mode                   | The control Mode, see below table.  |
| 1st CC Id              | The CC Id number of the first table slot. |
| 2nd CC Id              | ... |
| 3rd CC Id              | ... |
| 4th CC Id              | ... |
| 5th CC Id              | ... |
| 6th CC Id              | ... |
| 7th CC Id              | The CC Id number of the last table slot. |
| CC 0 Value             | The CC Value to produce using the 1st CC Id. |
| CC 1 Value             | ... |
| CC 2 Value             | ... |
| CC 3 Value             | ... |
| CC 4 Value             | ... |
| CC 5 Value             | ... |
| CC 6 Value             | ... |
| CC 7 Value             | The CC Value to produce using the last CC Id. |

| Mode        | Description |
| ----------- | ----------- |
| Immediate   | The CC event is produced immediately whenever a mapped control is moved. |
| Takeover    | If using multiple mapped controls to modify the same CC Value, the value of the control must first overpass the level set by the last control used. |

<span class="blokas-web-hide">

[List of Pipes](quick-links.md#io-pipes)

</span>
