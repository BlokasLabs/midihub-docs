# Midihub

## The Midihub Device

![midihub-side](https://blokas.io/images/midihub/midihub-side.jpg)

Midihub is the backbone of your MIDI hardware interconnectivity. It has MIDI DIN-5 input and output ports, 4 of each, as well as a USB port for power supply
and/or communicating with the PC and its software. All MIDI data flows through the customizable MIDI Processing Pipelines within the device with extremely low
latency and without involving any processing on the PC. It enables expanding the capabilities of your setup and makes interop between MIDI hardware easy.

## Input / Output

The Midihub has 4 MIDI input ports and 4 MIDI output ports and a single USB port which provides multiple virtual cables for the communication with the PC:
4 USB MIDI inputs and 4 USB MIDI outputs, as well as an internal USB serial port to be used for communicating with the editor only.
There's also Virtual Input and Output ports, 8 of each. They are used to forward the MIDI events to further Processing Pipelines. The different kinds of
ports are numbered using letters A, B, C, D, E, F, G and H. The USB MIDI ports will appear in your OS as regular MIDI devices. Their display names
are defined by the OS that is running on your PC.

See [The USB MIDI Port Mapping](the_usb_midi_port_mapping.md) for more details.

MIDI controllers with only USB output can't be connected directly to Midihub, however, they can still be used with Midihub if both are connected via a USB host such
as your PC or something like Raspberry Pi, the host then can forward the MIDI data coming from a USB controller to one (or more) Midihub's USB ports. The utilities
to achieve this vary with the OS, but to list a few, there's `aconnect` for Linux, 'Audio MIDI Setup' on Mac, 'MIDI-OX' on Windows, and most DAWs provide the functionality
to forward MIDI data between connected MIDI ports.

## The Memory

On power-up Midihub loads the MIDI Processing Pipelines that were stored in its Flash memory, preset 1. While editing the pipelines using the editor, changes
remain in volatile memory only, until the pipeline is 'Stored' in Flash memory of the device via the Toolbar or Device->Store submenu. It's also possible to
discard the current changes and restore the state by 'Loading' from Flash memory, via the Toolbar or Device->Load menu, making it easy to experiment with the
pipeline and go back to previous state.

Backups of all of the current Midihub state, including all of the presets, microtunings and settings, may be exported and imported via the 'Device -> Export
Everything' and 'Device -> Import Everything' menus while Midihub is connected to the editor.

## Technical Specification

| MIDI Paremeters | Value | Other Parameters | Value
|----|----|----|----|
| Input/Output Connectors | 8 x DIN-5 Female Sockets & USB-B Port | Enclosure | Powder-Coated 1mm Steel |
| MIDI Loopback Latency | Less than 1.5ms | Power | Bus-Powered - Computer or 5V USB Power Supply |
| Activity LEDs | 4 x MIDI Input, 4 x MIDI Output & 1 x USB/Status | Current Draw | 50mA @ 5.1VDC |
| Storage | 8 Presets | Dimensions | 75mm x 108mm x 36mm |
| Other Input | 1 x The Button | Weight | 285g |

## The Processing Pipelines

![editor-win](https://blokas.io/images/midihub/midihub-editor-win.png)

MIDI data flows through Midihub Processing Pipelines from left to right. All MIDI data enters the pipeline through the leftmost Input or Generator pipes, and exits
through the rightmost Output pipes. Processing the same MIDI event multiple times and in different ways is possible by making use of Virtual Input / Output ports.
The data sent to a Virtual Output port will appear again in the matching Virtual Input ports, enabling implementation of keyboard splits or automatically generating
chords. Pipes that modify or filter MIDI data can be placed in between the Input and Output ports. In case a pipe discards the MIDI data flowing through it, it won't
be forwarded to the pipe on the right, dropping the event.

Every pipe has a 'Bypass' parameter which, when enabled, bypasses the processing of the pipe, so it passes the incoming data to the right unmodified. If the leftmost
pipe is bypassed, the entire pipeline gets disabled.

Nearly all of the Pipe parameters can be MIDI mapped to external MIDI controllers. While Midihub is connected, the Map buttons next to the parameter value in the
Properties view are enabled. If one of them gets clicked on, unless the operation is interrupted, the very next CC message that gets sent to Midihub will get mapped
to the control. Don't forget to store the preset to memory after mapping changes are done.

## The Button

Clicking The Button on Midihub between 1-8 times allows switching between 1-8 presets.

The Button can be configured to do one of the following actions when held down for half a second (X indicates the channel number):

1. Send reset controller message to all 16 channels of selected ports (BXh 79h 00h).
2. Send system reset message to selected ports (FFh).
3. Send all notes off message to all 16 channels of selected ports (BXh 7Bh 00h).
4. Send custom data to selected ports (up to 32 bytes).

The settings are stored in non-volatile memory on closing the Settings dialog using the 'OK' button.

## The List of Pipes

| I/O Pipes | | |
|----|----|----|
| [MIDI Input](midi_input.md) | [MIDI Output](midi_output.md) | [USB Input](usb_input.md) |
| [USB Output](usb_output.md) | [Virtual Input](virtual_input.md) | [Virtual Output](virtual_output.md) |

| Gen. Pipes | | |
|----|----|----|
| [CC LFO](cc_lfo.md) | [Clock](clock.md) | |

| Filter Pipes | | |
|----|----|----|
| [Filter](filter.md) | [Channel Filter](filter_ch.md) | [Channel<br/>Range Filter](filter_range_ch.md)
| [Note Range Filter](filter_range_note.md) | [CC Range Filter](filter_range_cc.md) | |

| Remap Pipes | | |
|----|----|----|
| [Note Remap](note_remap.md) | [Channel Remap](channel_remap.md) | [CC Remap](cc_remap.md) |
| [Scale Remap](scale_remap.md) | [Micro Scale](micro_scale.md) |

| Modifier Pipes | | |
|----|----|----|
| [Note Length](note_length.md) | [Note Repeater](note_repeater.md) | [Arpeggiator](arpeggiator.md) |
| [Delay](delay.md) | [Transpose](transpose.md) | [Harmonizer](harmonizer.md) |
| [Dispatcher](dispatcher.md) | [Velocity Amp](velocity_amp.md) | [Equalizer](equalizer.md) |
| [Sustain](sustain.md) | [Limiter](limiter.md) | [Rescale](rescale.md) |
| [Transform](transform.md) | [Chance](chance.md) | [Randomizer](randomizer.md) |
| [Tempo Divider](tempo_divider.md) | [Sync Delay](sync_delay.md) | |
