# Transform

A modifier pipe that transforms particular kind of MIDI messages into the desired kind of MIDI message.

The possible transformations:

| What                 | Into              |
| -------------------- | ----------------- |
| Note Value           | Control Change    |
| Note Velocity        | Program Change    |
| Control Change       | Channel Pressure  |
| Program Change       | Start             |
| Channel Pressure     | Continue          |
| Start                | Stop              |
| Continue             |                   |
| Stop                 |                   |

| Parameter              | Description                                              |
| ---------------------- | -------------------------------------------------------- |
| Bypass                 | Whether processing is enabled.                           |
| What                   | Selects the MIDI message kind to convert.                |
| Into                   | Defines which message to transform it to.                |
| Argument               | (Conversion to CC only) The CC id to use.                |
| Pass-Through           | Whether to send the untransformed message through.       |

[List of Pipes](index.md#the-list-of-pipes)
