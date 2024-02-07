# Rescale

![rescale](https://blokas.io/images/midihub/pipes/rescale.svg)

A modifier pipe that rescales the values of the MIDI messages it's set to work with.

First incoming values are clipped at the In range, then they get linearly rescaled to the Out range.

| Parameter              | Description                                              |
| ---------------------- | -------------------------------------------------------- |
| Bypass                 | Whether processing is enabled.                           |
| Kind                   | Selects the MIDI message kind to process.                |
| In Low                 | The lowest value of input range.   |
| In High                | The highest value of input range.  |
| Out Low                | The lowest value of output range.  |
| Out High               | The highest value of output range. |
| Any Id?                | Whether to work with all Ids of the set Kind.            |
| Id                     | If 'Any Id?' is deactivated, the Id of the Note / Control / Channel to work with. |

<span class="blokas-web-hide">

[List of Pipes](quick-links.md#the-list-of-pipes)

</span>