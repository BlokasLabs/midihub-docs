# Midihub

## The Midihub Device

![midihub-side](https://blokas.io/images/midihub/midihub-side.jpg)

Midihub is the backbone of your MIDI hardware interconnectivity. It has MIDI DIN-5 input and output ports, 4 of each, as well as a USB port for power supply and/or communicating with the PC and its software. All MIDI data flows through the customizable MIDI Processing Pipelines within the device with extremely low latency and without involving any processing on the PC. It enables expanding the capabilities of your setup and makes interop between MIDI hardware easy.

## Input / Output

The Midihub has 4 MIDI input ports and 4 MIDI output ports and a single USB port which provides multiple virtual cables for the communication with the PC: 5 USB MIDI inputs and 5 USB MIDI outputs. The 5th pair is dedicated to be used for communicating with the editor only, don't use it in other software in order for the editor to be able to recognize the connected device. There's also Virtual Input and Output ports, 8 of each. They are used to forward the MIDI events to further Processing Pipelines. The different kinds of ports are numbered using letters A, B, C, D, E, F, G and H. The USB MIDI ports will appear in your OS as regular MIDI devices. However, their display names are defined by the OS that is running on your PC.

See [The USB MIDI Port Mapping](the_usb_midi_port_mapping) for more details.

## The Memory

On power-up Midihub loads the MIDI Processing Pipelines that were stored in its Flash memory, preset 1. While editing the pipelines using the editor, changes remain in volatile memory only, until the pipeline is 'Stored' in Flash memory of the device via the Toolbar or Device->Store submenu. It's also possible to discard the current changes and restore the state by 'Loading' from Flash memory, via the Toolbar or Device->Load menu, making it easy to experiment with the pipeline and go back to previous state.

## Technical Specification

| MIDI Paremeters | Value | Other Parameters | Value
|----|----|----|----|
| Input/Output Connectors | 8 x DIN-5 Female Sockets & USB-B Port | Enclosure | Powder-Coated 1mm Steel |
| MIDI Loopback Latency | Less than 1.5ms | Power | Bus-Powered - Computer or 5V USB Power Supply |
| Activity LEDs | 4 x MIDI Input, 4 x MIDI Output & 1 x Status | Current Draw | 50mA @ 5.1VDC |
| Other Input | 1 x The Button | Dimensions | 75mm x 108mm x 36mm |
| | | Weight | 285g |

## The Processing Pipelines

![editor-win](https://blokas.io/images/midihub/midihub-editor-win.png)

MIDI data flows through Midihub Processing Pipelines from left to right. All MIDI data enters the pipeline through the leftmost Input or Generator pipes, and exits through the rightmost Output pipes. Processing the same MIDI event multiple times and in different ways is possible by making use of Virtual Input / Output ports. The data sent to a Virtual Output port will appear again in the matching Virtual Input ports, enabling implementation of keyboard splits or automatically generating chords. Pipes that modify or filter MIDI data can be placed in between the Input and Output ports. In case a pipe discards the MIDI data flowing through it, it won't be forwarded to the pipe on the right, dropping the event.

Every pipe has a 'Bypass' parameter which, when enabled, bypasses the processing of the pipe, so it passes the incoming data to the right unmodified. If the leftmost pipe is bypassed, the entire pipeline gets disabled.

## The Button

Clicking The Button on Midihub between 1-8 times allows switching between 1-8 presets.

The Button can be configured to do one of the following actions when held down for half a second (X indicates the channel number):

1. Send reset controller message to all 16 channels of selected ports (BXh 79h 00h).
2. Send system reset message to selected ports (FFh).
3. Send all notes off message to all 16 channels of selected ports (BXh 7Bh 00h).
4. Send custom data to selected ports (up to 32 bytes).

'Store' must be done after changing the device's settings in order to make Midihub memorize it for the next time it is powered on.

## The List of Pipes

* [MIDI Input](midi_input)
* [MIDI Output](midi_output)
* [USB Input](usb_input)
* [USB Output](usb_output)
* [Virtual Input](virtual_input)
* [Virtual Output](virtual_output)
* [CC LFO](cc_lfo)
* [Clock](clock)
* [Note Length](note_length)
* [Note Repeater](note_repeater)
* [Arpeggiator](arpeggiator)
* [Delay](delay)
* [Transpose](transpose)
* [Harmonizer](harmonizer)
* [Dispatcher](dispatcher)
* [Filter](filter)
* [Channel Filter](filter_ch)
* [Channel Range Filter](filter_range_ch)
* [Note Range Filter](filter_range_note)
* [CC Range Filter](filter_range_cc)
* [Note Remap](note_remap)
* [Channel Remap](channel_remap)
* [CC Remap](cc_remap)
* [Scale Remap](scale_remap)
* [Micro Scale](micro_scale)
* [Velocity Amp](velocity_amp)
* [Equalizer](equalizer)
* [Sustain](sustain)
* [Limiter](limiter)
* [Rescale](rescale)
* [Transform](transform)
* [Chance](chance)
* [Randomizer](randomizer)
* [Tempo Divider](tempo_divider)
* [Sync Delay](sync_delay)
