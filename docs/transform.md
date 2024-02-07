# Transform

![transform](https://blokas.io/images/midihub/pipes/transform.svg)

A modifier pipe that transforms particular kind of MIDI messages into the desired kind of MIDI message.

It can convert between these message types:

| What / Into Values | | |
| ---- | ---- | ---- |
| Note On & Note Off (useful when remapping the note number) {colspan="3"}| | |
| Note On | Note Off | Reset |
| Control Change   | Program Change | Poly Aftertouch |
| Channel Pressure | Pitch Bend     | Start |
| Continue         | Stop           | Song Position Pointer |
| Song Select      | Tune Request   | Clock |
| Active Sense     |                |       |

| Parameter              | Description                                              |
| ---------------------- | -------------------------------------------------------- |
| Bypass                 | Whether processing is enabled.                           |
| Mode                   | The mode sets whether the transformed message should be inserted before the original event, after it, replace it, or whether the original event should simply be dropped (In this last mode, Transform acts as a specialized filter; transforming the incoming message to "nothing" as it were!). |
| What                   | Selects the MIDI message kind to convert.                |
| Into                   | Defines which message to transform it to.                |
| Set Channel to         | The selector of the value to use for the resulting message's Channel. See the below paragraph for extended description. |
| [Value for Byte 1]     | The name of this parameter depends on the Into parameter. It is the selector of the value to use for the MIDI message's first data byte. See the below paragraph for extended description. |
| [Value for Byte 2]     | Same as above. |
| Argument 1             | The value to use, in case it's selected by one of the above selector parameters. |
| Argument 2             | Same as above. |
| Channel Argument       | Similar to above, except limited to range 1-16. See the below paragraph for extended description. |
| Prioritize Real-Time   | Whether the Real Time messages produced should be prioritized. If off, logical order of the messages is retained. |
| Work with Channel      | Which channel to process (channel messages only).        |
| Work with Any Channel  | Whether to ignore the above parameter and process messages on any channel. |
| Work with [...] in Range Low | The lower data range bound of first data byte to trigger processing on. |
| Work with [...] in Range High | The higher data range bound of first data byte to trigger processing on. |
| Use [...]	Inside/Outside Range | Whether to trigger processing on data values inclusively within the range defined by above parameters, or exclusively outside the range. |
| Work with [...] in Range Low | Same as above, but for second data byte. |
| Work with [...] in Range High | Same as above, but for second data byte. |
| Use [...]	Inside/Outside Range | Same as above, but for second data byte. |

## Value Selectors and Arguments

When the Transform is being performed, there's up to 3 fields of the MIDI message to be set - the Channel, Data Byte 1 and Data Byte 2, depending on the desired MIDI message type set in the '**Into**' field. For maximum flexibility, there's a selector for each of these, with the following possible choices:

* **Arg1** - the value set in **Argument 1**. (Range: 0 - 127)
* **Arg2** - the value set in **Argument 2**. (Range: 0 - 127)
* **Ch. Arg** - the value set in **Channel Argument**. (Range: 1 - 16)
* **[Data Byte 1 (e.g. Note Number)]** - the 1st data value from the original message. The name is dynamic and depends on the **What** parameter. (Range: 0 - 127)
* **[Data Byte 2 (e.g. Note Velocity)]** - the 2nd data value from the original message. The name depends on the **What** parameter. (Range: 0 - 127)
* **Incoming Ch.** - the channel of the original message. (Range: 1 - 16)

When producing the new message, the Transform pipe picks the values for each necessary message's field according to the appropriate selector, scaling whenever the incoming and outgoing ranges differ:

As the range of channel numbers in MIDI is 1 - 16, but data values have a range of 0 - 127, it is necessary to rescale between the two ranges.

For example, if you transform a Note On into a CC and assign the CC's *value* to be set according to the Note On *Channel number* ('**Set Value to**' selector set to '**Incoming Ch.**'), then when incoming notes' channels equal 1, 2, 3, 15 and 16, you'll see the CC values 0, 8, 16, 112 and 120, respectively. When Transform is set up to do the opposite - use the incoming CC's Value byte for the Channel number selector, you will see the inverse - CC values 0, 8, 16, 112 and 120 would produce Channel numbers 1, 2, 3, 15 and 16, respectively.

<span class="blokas-web-hide">

[List of Pipes](quick-links.md#the-list-of-pipes)

</span>