# The Midihub Device

![midihub-side](https://blokas.io/images/midihub/midihub-side.jpg)

Midihub is the backbone of your MIDI hardware interconnectivity. It has MIDI DIN-5 input and output ports, 4 of each, as well as a USB port for power supply
and/or communicating with the PC and its software. All MIDI data flows through the customizable MIDI Processing Pipelines within the device with extremely low
latency and without involving any processing on the PC. It enables expanding the capabilities of your setup and makes interop between MIDI hardware easy.

## Input / Output

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

## The Memory

On power-up Midihub loads the MIDI Processing Pipelines that were stored in its Flash memory, the last stored preset.
While editing the pipelines using the editor, changes remain in volatile memory only, until the pipeline is 'Stored' in Flash memory of the device
via the Toolbar or Device->Store submenu. It's also possible to discard the current changes and restore the state by 'Loading' from Flash memory,
via the Toolbar or Device->Load menu, making it easy to experiment with the pipeline and go back to previous state.

Backups of all of the current Midihub state, including all of the presets, microtunings and settings, may be exported and imported via the 'Device -> Export
Everything' and 'Device -> Import Everything' menus while Midihub is connected to the editor.

## Device Settings

Midihub's settings can be set via Device -> Settings menu. The settings are stored in non-volatile memory on closing the Settings dialog using the 'OK' button.

### The Button

Clicking The Button on Midihub between 1-8 times allows switching between 1-8 presets.

The Button can be configured to do one of the following actions when held down for half a second (X indicates the channel number):

1. Send reset controller message to all 16 channels of selected ports (BXh 79h 00h).
2. Send system reset message to selected ports (FFh).
3. Send all notes off message to all 16 channels of selected ports (BXh 7Bh 00h).
4. Send custom data to selected ports (up to 32 bytes).

### External Preset Change

You can configure a specific Midihub port to listen for Program Change messages on a particular channel, allowing you to switch between presets using an external device. When enabled, PC0–PC7 messages will switch to presets 1–8, respectively.

This setting can be configured in the **Device -> Settings** dialog. If you find that your presets are changing unexpectedly, it may be because your connected hardware is sending Program Change messages. You can disable this feature by setting the channel to 'OFF' in the settings.

### Initial Preset

Depending on the Initial Preset setting, upon powering on, Midihub either loads the very first preset, or the last preset that was saved to memory. This way, you may make Midihub by default load, say, Preset 7 upon powering on, if this was the last preset stored to memory before turning it off.

## Technical Specification

| MIDI Paremeters | Value | Other Parameters | Value
|----|----|----|----|
| Input/Output Connectors | 8 x DIN-5 Female Sockets & USB-B Port | Enclosure | Powder-Coated 1mm Steel |
| MIDI Loopback Latency | Less than 1.5ms | Power | Bus-Powered - Computer or 5V USB Power Supply |
| Activity LEDs | 4 x MIDI Input, 4 x MIDI Output & 1 x USB/Status | Current Draw | 50mA @ 5.1VDC |
| Storage | 8 Presets | Dimensions | 75mm x 108mm x 36mm |
| Other Input | 1 x The Button | Weight | 285g |
