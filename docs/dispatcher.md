# Dispatcher

![dispatcher](https://blokas.io/images/midihub/pipes/dispatcher.svg)

A modifier pipe that upon receiving a note message dispatches it to different channels, rotating and keeping track of empty slots.

This pipe should be combined with Virtual Pipes and Channel Remap to route the MIDI data to the necessary MIDI outputs.

| Parameter              | Description                    |
| ---------------------- | ------------------------------ |
| Bypass                 | Whether processing is enabled. |
| Use Ch 1               | Use MIDI Channel 1 for dispatching. |
| Use Ch 2               | Use MIDI Channel 2 for dispatching. |
| Use Ch 3               | Use MIDI Channel 3 for dispatching. |
| Use Ch 4               | Use MIDI Channel 4 for dispatching. |
| Use Ch 5               | Use MIDI Channel 5 for dispatching. |
| Use Ch 6               | Use MIDI Channel 6 for dispatching. |
| Use Ch 7               | Use MIDI Channel 7 for dispatching. |
| Use Ch 8               | Use MIDI Channel 8 for dispatching. |
| Use Ch 9               | Use MIDI Channel 9 for dispatching. |
| Use Ch 10              | Use MIDI Channel 10 for dispatching. |
| Use Ch 11              | Use MIDI Channel 11 for dispatching. |
| Use Ch 12              | Use MIDI Channel 12 for dispatching. |
| Use Ch 13              | Use MIDI Channel 13 for dispatching. |
| Use Ch 14              | Use MIDI Channel 14 for dispatching. |
| Use Ch 15              | Use MIDI Channel 15 for dispatching. |
| Use Ch 16              | Use MIDI Channel 16 for dispatching. |
| Algorithm              | The dispatching algorithm, see below table for descriptions. |
| Surplus Ch             | The MIDI Channel to use in case all the slots were used up by the other notes, or the chord is complete. |
| Chord Grace Period     | For Chord based algorithms - as the MIDI notes come in sequentially, this defines the duration since the last received notes to wait for the next note in the chord. If none is received after the Grace Period, the chord is considered complete, the additional notes will go to the Surplus channel. |

| Algorithm   | Description |
| ----------- | ----------- |
| Round Robin | The algorithm searches for the next free slot above the current channel, wrapping to the first one once at the end. |
| Random      | The algorithm picks a random free slot. |
| Ping Pong   | Similar to Round Robin, except instead of wrapping to the beginning, it starts searching for a free slot in the reverse direction. |
| Chord       | Similar to Round Robin, but resets the Channel counter to the lowest each time all notes are released. After Chord Grace Period passes since the last note, the remaining notes will act according to Surplus Ch parameter. |
| Chord Asc.  | Waits for Chord Grace Period for all of the chord notes, then plays the chord's notes sorted from lowest to highest dispatched into channels. |
| Chord Desc. | Similar to Chord Asc., except sorted from highest note to lowest. |

<span class="blokas-web-hide">

[List of Pipes](quick-links.md#the-list-of-pipes)

</span>