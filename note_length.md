# Note Length

![n_length](https://blokas.io/images/midihub/pipes/n_length.svg)

A modifier pipe that fixes the note lengths to the given length. If Trigger is set to Note Off, the note pattern gets inverted to produce notes where original notes were being turned off.

**If Sync is on, MIDI Clock input must be provided to the pipe** for the pipe to work.

| Parameter              | Description                        |
| ---------------------- | ---------------------------------- |
| Bypass                 | Whether processing is enabled.     |
| Length                 | The length to fix the notes to.    |
| Gate                   | The percentage amount to expand or shrink the note length parameter. <ul><li>0% - Shortest length,</li><li>100% - Unchanged length,</li><li>200% - Double length.</li></ul> |
| Trigger                | Whether to trigger the fixed length note on the Note On or Note Off event. |
| Sync                   | Whether to sync the length to the tempo. |
| Decay                  | In case Trigger is set to Note Off, this parameter affects the velocity of the Note On that will get produced when triggered by decaying the velocity of original Note On message. The time set by this parameter is the time it would take to decay the original Note On velocity to 0. |

<span class="blokas-web-hide">

[List of Pipes](index.md#the-list-of-pipes)

</span>