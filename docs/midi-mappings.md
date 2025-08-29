# MIDI Mappings

Almost every Pipe parameter can be MIDI mapped to MIDI controllers. While Midihub is connected, the Map buttons next to the parameter values in the Properties view are enabled.
When a Map button is clicked, a dialog appears: "Mapping... Send a Note or CC message to any of Midihub's input ports:"
Unless interrupted, Midihub will map the next external CC or Note message to the parameter. Don't forget to store the preset to memory after mapping changes are done.

Alongside each Map button, there is an Add button. This button allows manual setting of parameter mappings for both physical inputs and virtual outputs.
Afterwards, the mappings can be edited using the Edit button. The Add button can also be used when Midihub is disconnected.
Settings within the Add/Edit dialog are maintained, allowing the same settings to be used for multiple successive parameters.

Events that are mapped to physical DIN-5 or USB ports take effect as soon as they are received by Midihub.
The events can be preprocessed in the Mapping Options dialog. The following options may be set:

| Parameter              | Description                                                  |
| ---------------------- | ------------------------------------------------------------ |
| Port                   | The port for the mapping. You may select a Virtual port for internal mappings. |
| Type                   | **CC**: Controller events.<br/>**Note On**: Note events with value range 1-127. Triggers on key down, but not release.<br/>**Note On & Off**: Triggers on both Note On (1 - 127) & Note Off events (0). |
| Channel                | The Channel to listen to. |
| Id                     | The Id of the CC or Note to look out for. |
| Mode                   | **Scale**: Linearly rescale incoming 0 - 127 value to [Low;High].<br/>**Toggle**: Toggles between Low and High values every time the mapped CC goes above 63 or a mapped Note On is received.<br/>**Clip**: The value is clipped and limited at [Low;High] range.<br/>**Slice**: The value is used for parameter updates only if it falls inside [Low;High] range. Can be useful to edit different parameters at different value ranges. |
| Low                    | The Low value of the range. If Low is greater than High, the control is inverted. |
| High                   | The High value of the range. If High is lower than Low, the control is inverted. |
| Drop                   | Whether to drop the mapped parameter from processing by the pipes. If enabled, the mapping event won't appear at any of the matching Input pipes. |

More flexibe preprocessing can be achieved by sending the events through a series of MIDI pipes into a Virtual Output.
Then you should create parameter mappings for the matching Virtual bus. The virtual mappings affect the mapped parameters
as soon as a mapped MIDI event reaches the appropriate Virtual Output Pipe.
