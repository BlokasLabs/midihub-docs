# Sync Delay

![sync_delay](https://blokas.io/images/midihub/pipes/sync_delay.svg)

A modifier pipe that drops a given number of Real-Time Clock MIDI messages or produces up to one quarter note worth of Clock messages in an instant to shift forward.
The shift happens every time MIDI Start message is processed.

Using this pipe some tricky MIDI hardware sync incompatibility issues can be resolved.

| Parameter              | Description                                                  |
| ---------------------- | ------------------------------------------------------------ |
| Bypass                 | Whether processing is enabled.                               |
| Delay by               | The amount of clocks to delay by, or shift forward if the value is negative. |

See also: [Sync Delay Ms](sync-delay-ms.md)

<span class="blokas-web-hide">

[List of Pipes](quick-links.md#io-pipes)

</span>