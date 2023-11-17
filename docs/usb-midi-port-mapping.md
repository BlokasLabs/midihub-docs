# The USB MIDI Port Mapping

The following table contains the Midihub USB Input / Output letter mapping to the device name used by OS.

Renaming of the USB ports in the Editor unfortunately does not rename ports as seen by the OS,
as the drivers for all major OSes ignore USB port name information as provided by the device.

Renaming of Midihub via Device -> Settings... menu should allow overriding the name of all
4 input and 4 output USB ports as shown by the OS. For changes to take place you have to reconnect
the device. On macOS, you may have to additionally remove the Midihub device from MIDI Setup
while it is disconnected. This can cause other macOS software (like MIDI Patchbay) configurations
to get confused, so make sure to back them up before doing this.

For future proofing, Midihub does provide the Default Port Names set for each USB port
via USB string descriptors, at some point hopefully USB MIDI drivers will take that into account.

## Windows

| USB Port | Input Port Name           | Output Port Name          |
| -------- | ------------------------- | ------------------------- |
| USB A    | Midihub MH-...            | Midihub MH-...            |
| USB B    | MIDIIN2 (Midihub MH-...)  | MIDIOUT2 (Midihub MH-...) |
| USB C    | MIDIIN3 (Midihub MH-...)  | MIDIOUT3 (Midihub MH-...) |
| USB D    | MIDIIN4 (Midihub MH-...)  | MIDIOUT4 (Midihub MH-...) |

## Mac

| USB Port | Input Port Name        | Output Port Name       |
| -------- | ---------------------- | ---------------------- |
| USB A    | Midihub MH-... (Port1) | Midihub MH-... (Port1) |
| USB B    | Midihub MH-... (Port2) | Midihub MH-... (Port2) |
| USB C    | Midihub MH-... (Port3) | Midihub MH-... (Port3) |
| USB D    | Midihub MH-... (Port4) | Midihub MH-... (Port4) |

## Linux

| USB Port | Input Port Name | Output Port Name |
| -------- | --------------- | ---------------- |
| USB A    | hw:n,0,0        | hw:n,0,0         |
| USB B    | hw:n,0,1        | hw:n,0,1         |
| USB C    | hw:n,0,2        | hw:n,0,2         |
| USB D    | hw:n,0,3        | hw:n,0,3         |

## See Also

[Port Naming](port-naming.md)
