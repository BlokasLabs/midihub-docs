# CC / CC RPN / CC NRPN

![cc_rpn_nrpn](https://blokas.io/images/midihub/pipes/cc_rpn_nrpn_hybrid.svg)

Pipes that generate CC, RPN or NRPN messages through MIDI mappings or directly from the Editor.
They can be placed as a Generator (leftmost) or a Modifier (inline) pipe.

Use a Generator to control a device parameter from mapped knobs, buttons or the Editor.
Use a Modifier to also limit incoming values, or to convert ordinary CC input into RPN / NRPN updates.
Choose the controller or parameter number and Resolution from the receiving device's MIDI implementation chart, set the Channel, and place an Output pipe to the right.

| Pipe | Output |
| ---- | ------ |
| CC | Ordinary CC messages, using one controller number for 7-bit values or two for 14-bit values. |
| CC RPN | Registered Parameter Number messages. |
| CC NRPN | Non-Registered Parameter Number messages, usually for device-specific parameters. |

## Finding Parameter Numbers

Start with the receiving device's manual: look for its **MIDI implementation chart**, **CC list**, or **RPN / NRPN parameter table**. Some manufacturers provide these as a separate document on their support website. Check the parameter number, supported value range and resolution, and any MIDI settings needed to enable reception.

The Editor's CC / NRPN database is derived from [MIDI Guide](https://midi.guide/){target=_blank}, a community-maintained collection of device parameter definitions by Pencil Research and contributors. You can browse it by manufacturer and device to find CC and NRPN numbers and their value ranges. Refer to your device's manual for parameters that are missing, including supported RPNs.

### Contributing Missing Parameters

If a parameter or device is missing, visit the [MIDI Guide GitHub repository](https://github.com/pencilresearch/midi){target=_blank} and follow its [contribution instructions](https://github.com/pencilresearch/midi/blob/main/CONTRIBUTING.md){target=_blank}. You can report missing information in an issue, or update the device's CSV file using its manual and submit a pull request. The instructions also cover adding new devices and submitting changes by email.

## Choosing a Parameter in the Editor

The **Parameter** row shows the current parameter's name, or **Custom** if no CC / NRPN database entry matches. Click **Select...** to open the **Parameter Browser**. Search by parameter, manufacturer or device name, and use the **Device** filter to narrow the results. Choose **Registered Parameters (RPN)** in that filter to browse RPNs.

Selecting a parameter sets the pipe type, parameter numbers, resolution, value limits and message-sending options for you. Some entries also set a device-specific MIDI channel, so check **Channel** after choosing.

Some parameters are available as both **CC** and **CC NRPN**. **CC** is usually the preferred choice: it sends fewer MIDI messages, leaving more room for notes and other controls. Choose **CC NRPN** if it offers finer control that you need.

## Common Parameters

Edit or map **Selected Ch. n Value Coarse / Fine** to send values on the selected Channel.
Use **Ch. n Value** controls when individual mappings should always address a particular channel.

| Parameter | Description |
| --------- | ----------- |
| Bypass | Whether processing is enabled. |
| Parameter | Shows the selected parameter's name, or **Custom** if no CC / NRPN database entry matches. Click **Select...** to choose a parameter from the database. |
| Resolution | **7-bit MSB**: coarse value, 0-127.<br/>**7-bit LSB**: fine value, 0-127.<br/>**14-bit**: combined coarse and fine value, 0-16383. |
| Min / Max | Limits applied to the value. The range follows Resolution. |
| Use Incoming Ch. | (Only as Modifier) Process matching input on any channel and produce updates on that channel. When off, only the selected Channel is processed. |
| Channel | The output channel for Selected Ch. value controls. Also selects the input channel when Use Incoming Ch. is off. |
| Selected Ch. n Value Coarse / Fine | The current coarse or fine value on the selected Channel. Can be edited or MIDI-mapped. |
| Selected Ch. n Value 14bit | The combined 14-bit value on the selected Channel. Map its coarse and fine components separately. |
| Ch. n Value Coarse / Fine / 14bit | The corresponding value controls for each of the 16 MIDI channels, independent of Channel. |

In 14-bit mode, the combined value is **coarse x 128 + fine**.
Live values are not saved in the preset. MIDI mappings are saved.
Inactive parameters are hidden unless they have mappings; retained inactive mappings can be removed or reactivated by changing the configuration.

## CC

Use ordinary CC for parameters identified by a controller number. A 14-bit CC parameter uses a coarse/fine pair of controller numbers.

- **Volume:** select **7-bit MSB**, set **CC MSB** to **7**, and map **Selected Ch. n Value Coarse** to a knob.
- **14-bit control:** for a device using CC **1/33**, select **14-bit**, set **CC MSB** to **1** and **CC LSB** to **33**. Map the coarse and fine value controls separately, or edit the combined value in the Editor.

| Parameter | Description |
| --------- | ----------- |
| CC MSB | Controller number for the coarse value. Used in 7-bit MSB and 14-bit modes. |
| CC LSB | Controller number for the fine value. Used in 7-bit LSB and 14-bit modes. |

For standard 14-bit CC pairs, CC LSB is CC MSB + 32. Both numbers can be set independently to match the receiving device.

As a Modifier, the pipe limits matching incoming CC values to Min / Max. Other messages pass through unchanged.

## CC RPN / CC NRPN

Use RPN for registered parameters such as pitch bend sensitivity, and NRPN for device-specific parameters.
Enter the parameter number separately from the value: **Param MSB / LSB** select what to control; **Value Coarse / Fine** set its value.

- **RPN pitch bend range:** on a receiver supporting pitch bend sensitivity, set **Param MSB** and **Param LSB** to **0**, select **7-bit MSB**, and set **Selected Ch. n Value Coarse** to **2** for a +/- 2-semitone range.
- **NRPN from a knob:** if the device's chart specifies parameter **148** with values **0-127**, set **Param 14bit** to **148** (MSB **1**, LSB **20**), select **7-bit MSB**, and map **Selected Ch. n Value Coarse** to the knob.

As a Modifier, an alternative to MIDI mapping is to set **Value Coarse CC** to the knob's CC number, enable **Value Coarse CC Enabled**, and select MSB or either component in **Update On**. The original CC also passes through.

| Parameter | Description |
| --------- | ----------- |
| Param MSB / Param LSB | The two 7-bit parts of the target parameter number. |
| Param 14bit | Sets both parameter-number parts together: **MSB x 128 + LSB**. |
| Value Coarse CC Enabled | (Only as Modifier) Use incoming Value Coarse CC messages to update the stored coarse value. Does not disable triggering; see below. |
| Value Coarse CC | (Only as Modifier) Input controller number for coarse value updates and triggering. |
| Value Fine CC Enabled | (Only as Modifier) Use incoming Value Fine CC messages to update the stored fine value. Does not disable triggering; see below. |
| Value Fine CC | (Only as Modifier) Input controller number for fine value updates and triggering. |
| Update On | Trigger output on coarse (MSB), fine (LSB), or either component's input CC or mapped value changes. |
| Always Emit Param Select | Send both parameter-selection messages before every output update, even if the target is already selected. |
| Always Emit Both MSB and LSB | Send both value components on every output update, even if unchanged. |
| Always Emit End | Follow each output update with a null parameter selection: Param MSB = 127, Param LSB = 127. |

### Input and Triggering

As a Modifier, the pipe tracks incoming RPN or NRPN values for the matching protocol and parameter number, and limits their Data Entry values to Min / Max.

The additional Value Coarse CC and Value Fine CC inputs pass through unchanged.
Their **Enabled** switches control whether their values are used. These CC messages can still trigger output when disabled, using the stored value and following **Update On**.
Changing the stored component through a MIDI mapping also follows Update On.

Unchanged parameter-selection and value components may be omitted from generated output unless the corresponding Always Emit option is on.

RPN selects the parameter using CC 101/100; NRPN uses CC 99/98. Both use CC 6/38 for coarse/fine Data Entry.
These parameter-selection numbers are separate from the configurable Value Coarse CC / Value Fine CC input numbers.

<span class="blokas-web-hide">

[List of Pipes](quick-links.md#generator-pipes)

</span>
