# The Midihub Editor

![editor-win](https://blokas.io/images/midihub/midihub-editor-win.png)

The Midihub Editor lets you customize Midihub's processing logic by laying down the processing pipelines using different Pipes, sort of MIDI effects.
The interface is based on intuitive Drag & Drop model. Every pipeline starts from an Input or Generator pipe, from which MIDI data flows to the right, until it ends up in an Output pipe. You can play around with the Editor even without the device connected. Midihub Editor works on all major platforms - Windows, macOS and Linux!

<span class="blokas-editor-hide">

## Downloads

Download the latest version of the Editor for your platform:

- [Editor for Windows](https://blokas.io/midihub/downloads/latest/windows/)
- [Editor for macOS](https://blokas.io/midihub/downloads/latest/mac/)
- [Editor for Linux](https://blokas.io/midihub/downloads/latest/linux/)
- [Editor for Raspberry Pi](https://blokas.io/midihub/downloads/latest/linux_arm/)

</span>

## The Processing Pipelines

MIDI data flows through Midihub Processing Pipelines from left to right. All MIDI data enters the pipeline through the leftmost Input or Generator pipes, and exits
through the rightmost Output pipes. [MIDI Monitor](midi-monitor.md) pane can be used to see the data flow in real time. Processing the same MIDI event multiple times and in different ways is possible by making use of Virtual Input / Output ports.
The data sent to a Virtual Output port will appear again in the matching Virtual Input ports, enabling implementation of keyboard splits or automatically generating
chords. Pipes that modify or filter MIDI data can be placed in between the Input and Output ports. In case a pipe discards the MIDI data flowing through it, it won't
be forwarded to the pipe on the right, dropping the event.

Pipelines from a file may be [imported](inserting-pipelines-from-file.md) into the current Preset. They may also be imported directly from [Patchstorage](inserting-from-patchstorage.md).

The Pipelines are built by dragging in Pipe icons from Pipes pane into the main canvas. To customize functionality of each pipe, the parameters of the currently selected pipe can be changed in the Properties pane. Holding down Alt or Ctrl keys while dragging a Pipe will create a copy in a new location. Holding down Shift as well copies the mappings along with the Pipe. The mouse right-click menu shows options for duplicating the entire pipeline.

If you are running two instances of Midihub Editor, Alt/Ctrl-drag may be used to copy a pipe from one canvas to the other.

## Pipe Parameters

Every pipe has a 'Bypass' parameter which, when enabled, bypasses the processing of the pipe, so it passes the incoming data to the right unmodified. If the leftmost
pipe is bypassed, the entire pipeline gets disabled.

Almost every Pipe parameter can be MIDI mapped to MIDI controllers. While Midihub is connected, the Map buttons next to the parameter values in the Properties view are enabled.
When a Map button is clicked, a dialog appears: "Mapping... Send a Note or CC message to any of Midihub's input ports:"
Unless interrupted, Midihub will map the next external CC or Note message to the parameter. Don't forget to store the preset to memory after mapping changes are done.

Alongside each Map button, there is an Add button. This button allows manual setting of parameter mappings for both physical inputs and virtual outputs.
Afterwards, the mappings can be edited using the Edit button. The Add button can also be used when Midihub is disconnected.
Settings within the Add/Edit dialog are maintained, allowing the same settings to be used for multiple successive parameters.

Events that are mapped to physical DIN-5 or USB ports take effect as soon as they are received by Midihub. Preprocessing the events that are mapped to parameters can be done by manually creating mappings to Virtual Output ports. This way Midihub's Pipes can be used to preprocess the message before it is used to change a mapped parameter. The virtual mappings affect the mapped parameters as soon as a mapped MIDI event reaches the appropriate Virtual Output Pipe.

## I/O Pipes
- [MIDI Input](midi-input.md)
- [MIDI Output](midi-output.md)
- [USB Input](usb-input.md)
- [USB Output](usb-output.md)
- [Virtual Input](virtual-input.md)
- [Virtual Output](virtual-output.md)

## Generator Pipes
- [CC LFO](cc-lfo.md)
- [Clock](clock.md)

## Filter Pipes
- [CC Range Filter](cc-range-filter.md)
- [Channel Filter](channel-filter.md)
- [Channel Range Filter](channel-range-filter.md)
- [Filter](filter.md)
- [Note Range Filter](note-range-filter.md)

## Remap Pipes
- [CC Remap](cc-remap.md)
- [Channel Remap](channel-remap.md)
- [Micro Scale](micro-scale.md)
- [Note Remap](note-remap.md)
- [Scale Remap](scale-remap.md)

## Modifier Pipes
- [Arpeggiator](arpeggiator.md)
- [Chance](chance.md)
- [Delay](delay.md)
- [Dispatcher](dispatcher.md)
- [Equalizer](equalizer.md)
- [Harmonizer](harmonizer.md)
- [Limiter](limiter.md)
- [Note Length](note-length.md)
- [Note Repeater](note-repeater.md)
- [Randomizer](randomizer.md)
- [Rescale](rescale.md)
- [Sustain](sustain.md)
- [Sync Delay](sync-delay.md)
- [Tempo Divider](tempo-divider.md)
- [Transform](transform.md)
- [Transpose](transpose.md)
- [Velocity Amp](velocity-amp.md)
