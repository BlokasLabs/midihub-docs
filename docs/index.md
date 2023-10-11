# Midihub

## The Midihub Device

![midihub-side](https://blokas.io/images/midihub/midihub-side.jpg)

Midihub is the backbone of your MIDI hardware interconnectivity. It has MIDI DIN-5 input and output ports, 4 of each, as well as a USB port for power supply
and/or communicating with the PC and its software. All MIDI data flows through the customizable MIDI Processing Pipelines within the device with extremely low
latency and without involving any processing on the PC. It enables expanding the capabilities of your setup and makes interop between MIDI hardware easy.

### Input / Output

The Midihub has 4 MIDI input ports and 4 MIDI output ports and a single USB port which provides multiple virtual cables for the communication with the PC:
4 USB MIDI inputs and 4 USB MIDI outputs, as well as an internal USB serial port to be used for communicating with the editor only.
There's also Virtual Input and Output ports, 8 of each. They are used to forward the MIDI events to further Processing Pipelines. The different kinds of
ports are numbered using letters A, B, C, D, E, F, G and H. The ports can be [renamed](port-naming.md) in the Editor. The USB MIDI ports will appear in your OS as regular MIDI devices. Their display names
are defined by the OS that is running on your PC.

See [The USB MIDI Port Mapping](usb-midi-port-mapping.md) for more details.

MIDI controllers with only USB output can't be connected directly to Midihub, however, they can still be used with Midihub if both are connected via a USB host such
as your PC or something like Raspberry Pi, the host then can forward the MIDI data coming from a USB controller to one (or more) Midihub's USB ports. The utilities
to achieve this vary with the OS, but to list a few, there's 'aconnect' for Linux, 'MIDI Patchbay' on Mac, 'MIDI-OX' on Windows, and most DAWs provide the functionality
to forward MIDI data between connected MIDI ports.

### The Memory

On power-up Midihub loads the MIDI Processing Pipelines that were stored in its Flash memory, the last stored preset.
While editing the pipelines using the editor, changes remain in volatile memory only, until the pipeline is 'Stored' in Flash memory of the device
via the Toolbar or Device->Store submenu. It's also possible to discard the current changes and restore the state by 'Loading' from Flash memory,
via the Toolbar or Device->Load menu, making it easy to experiment with the pipeline and go back to previous state.

Backups of all of the current Midihub state, including all of the presets, microtunings and settings, may be exported and imported via the 'Device -> Export
Everything' and 'Device -> Import Everything' menus while Midihub is connected to the editor.

### Device Settings

Midihub's settings can be set via Device -> Settings menu. The settings are stored in non-volatile memory on closing the Settings dialog using the 'OK' button.

#### The Button

Clicking The Button on Midihub between 1-8 times allows switching between 1-8 presets.

The Button can be configured to do one of the following actions when held down for half a second (X indicates the channel number):

1. Send reset controller message to all 16 channels of selected ports (BXh 79h 00h).
2. Send system reset message to selected ports (FFh).
3. Send all notes off message to all 16 channels of selected ports (BXh 7Bh 00h).
4. Send custom data to selected ports (up to 32 bytes).

#### External Preset Change

You may make a particular Midihub's port to listen for Program Change messages on a particular channel. PC0 - PC7 messages switch between presets 1 - 8.

#### Initial Preset

Depending on the Initial Preset setting, upon powering on, Midihub either loads the very first preset, or the last preset that was saved to memory. This way, you may make Midihub by default load, say, Preset 7 upon powering on, if this was the last preset stored to memory before turning it off.

### Technical Specification

| MIDI Paremeters | Value | Other Parameters | Value
|----|----|----|----|
| Input/Output Connectors | 8 x DIN-5 Female Sockets & USB-B Port | Enclosure | Powder-Coated 1mm Steel |
| MIDI Loopback Latency | Less than 1.5ms | Power | Bus-Powered - Computer or 5V USB Power Supply |
| Activity LEDs | 4 x MIDI Input, 4 x MIDI Output & 1 x USB/Status | Current Draw | 50mA @ 5.1VDC |
| Storage | 8 Presets | Dimensions | 75mm x 108mm x 36mm |
| Other Input | 1 x The Button | Weight | 285g |

## The Midihub Editor

The Midihub Editor lets you customize Midihub's processing logic by laying down the processing pipelines using different Pipes, sort of MIDI effects.
The interface is based on intuitive Drag & Drop model. Every pipeline starts from an Input or Generator pipe, from which MIDI data flows to the right, until it ends up in an Output pipe. You can play around with the Editor even without the device connected. Midihub Editor works on all major platforms - Windows, macOS and Linux!

<span class="blokas-editor-hide">

### Downloads

Download the latest version of the Editor for your platform:

- [Editor for Windows](https://blokas.io/midihub/downloads/latest/windows/)
- [Editor for macOS](https://blokas.io/midihub/downloads/latest/mac/)
- [Editor for Linux](https://blokas.io/midihub/downloads/latest/linux/)
- [Editor for Raspberry Pi](https://blokas.io/midihub/downloads/latest/linux_arm/)

</span>

### The Processing Pipelines

![editor-win](https://blokas.io/images/midihub/midihub-editor-win.png)

MIDI data flows through Midihub Processing Pipelines from left to right. All MIDI data enters the pipeline through the leftmost Input or Generator pipes, and exits
through the rightmost Output pipes. [MIDI Monitor](midi-monitor.md) pane can be used to see the data flow in real time. Processing the same MIDI event multiple times and in different ways is possible by making use of Virtual Input / Output ports.
The data sent to a Virtual Output port will appear again in the matching Virtual Input ports, enabling implementation of keyboard splits or automatically generating
chords. Pipes that modify or filter MIDI data can be placed in between the Input and Output ports. In case a pipe discards the MIDI data flowing through it, it won't
be forwarded to the pipe on the right, dropping the event.

Pipelines from a file may be [imported](inserting-pipelines-from-file.md) into the current Preset. They may also be imported directly from [Patchstorage](inserting-from-patchstorage.md).

The Pipelines are built by dragging in Pipe icons from Pipes pane into the main canvas. To customize functionality of each pipe, the parameters of the currently selected pipe can be changed in the Properties pane. To make copies of a Pipe, you may start dragging one in the main canvas with the mouse while keeping Alt or Ctrl keys held down. If Shift is held as well the mappings get copied too. Entire pipeline can be duplicated via the mouse right click menu.

### Pipe Parameters

Every pipe has a 'Bypass' parameter which, when enabled, bypasses the processing of the pipe, so it passes the incoming data to the right unmodified. If the leftmost
pipe is bypassed, the entire pipeline gets disabled.

Nearly all of the Pipe parameters can be MIDI mapped to MIDI controllers. While Midihub is connected, the Map buttons next to the parameter values in the
Properties view are enabled. If one of them gets clicked on, unless the operation is interrupted, the very next CC or Note message that gets sent to Midihub will get mapped
to the parameter. Don't forget to store the preset to memory after mapping changes are done.

In addition to that, there's also an Add button that can be used to add a parameter mapping to a particular MIDI CC or Note message. Afterwards, the mappings can be edited using the Edit button.

Events that are mapped to physical DIN-5 or USB ports take effect as soon as they are received by Midihub. Preprocessing the events that are mapped to parameters can be done by manually creating mappings to Virtual Output ports. This way Midihub's Pipes can be used to preprocess the message before it is used to change a mapped parameter. The virtual mappings affect the mapped parameters as soon as a mapped MIDI event reaches the appropriate Virtual Output Pipe.

### The List of Pipes

| I/O Pipes | | |
|----|----|----|
| [MIDI Input](midi-input.md) | [MIDI Output](midi-output.md) | [USB Input](usb-input.md) |
| [USB Output](usb-output.md) | [Virtual Input](virtual-input.md) | [Virtual Output](virtual-output.md) |

| Generator Pipes | | |
|----|----|----|
| [CC LFO](cc-lfo.md) | [Clock](clock.md) | |

| Filter Pipes | | |
|----|----|----|
| [Filter](filter.md) | [Channel Filter](channel-filter.md) | [Channel<br/>Range Filter](channel-range-filter.md)
| [Note Range Filter](note-range-filter.md) | [CC Range Filter](cc-range-filter.md) | |

| Remap Pipes | | |
|----|----|----|
| [Note Remap](note-remap.md) | [Channel Remap](channel-remap.md) | [CC Remap](cc-remap.md) |
| [Scale Remap](scale-remap.md) | [Micro Scale](micro-scale.md) |

| Modifier Pipes | | |
|----|----|----|
| [Note Length](note-length.md) | [Note Repeater](note-repeater.md) | [Arpeggiator](arpeggiator.md) |
| [Delay](delay.md) | [Transpose](transpose.md) | [Harmonizer](harmonizer.md) |
| [Dispatcher](dispatcher.md) | [Velocity Amp](velocity-amp.md) | [Equalizer](equalizer.md) |
| [Sustain](sustain.md) | [Limiter](limiter.md) | [Rescale](rescale.md) |
| [Transform](transform.md) | [Chance](chance.md) | [Randomizer](randomizer.md) |
| [Tempo Divider](tempo-divider.md) | [Sync Delay](sync-delay.md) | |
