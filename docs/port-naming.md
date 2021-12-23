# Port Naming

The names of all the ports can be changed in the Editor, via the Preset -> Edit Port Names menu, as well as Device -> Edit Default Port Names menu.
Each Midihub can have a set of device-default port names (only for non-virtual ports), which are shared for all presets that are stored in the device.
Each preset has another set of port names (virtual port names too). If the same port name is set in the Preset as in the default set, it will override
the device-default port name.

It's a good idea to rename the physical ports in the device defaults, and virtual ports in the preset memory, as that keeps presets easier to reuse, and
changing physical connections and their names easier across all presets in memory.

Here's a table showing what the resulting name of MIDI A input will be, depending on what name's are set in default and preset memories:

| Default Memory | Preset Memory | Resulting Name |
| -------------- | ------------- | -------------- |
| *&lt;unset&gt;*| *&lt;unset&gt;*| FROM A        |
| SYNTH          | *&lt;unset&gt;*| SYNTH         |
| *&lt;unset&gt;*| DRUM MACHINE  | DRUM MACHINE   |
| SYNTH          | DRUM MACHINE  | DRUM MACHINE   |

## Importing Names

The names can be imported through Preset -> Import Port Names... menu, Device -> Import Default Port Names... and through [Insert Preview](insert-preview.md) dialog's Merge Names button.

When importing/merging, a dialog will appear that allows for selecting which name to use for each port with different names (or entering a custom one).


## See Also

[USB MIDI Port Mapping](usb-midi-port-mapping.md)
