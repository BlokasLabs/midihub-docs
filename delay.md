# Delay

![delay](https://blokas.io/images/midihub/pipes/delay.svg)

A modifier pipe that produces delayed notes based on what was played into it. It can be used as a looper
if the Feedback is at 100%, Infinite is enabled, and Delay Time is at some convenient value like 1 Bar.

Each pipe remembers up to 32 notes at a time, including the velocity and length of each note. Note slots are
reclaimed when notes fade out or has reached the repetitions target. If a new note is played while there's no
empty slots available, then the oldest slot will get reused.

All notes are turned off if Stop MIDI message is received, or if either Bypass or Sync parameters get changed.

Overdub may be disabled to allow playing on top of the loop, the notes within the loop will not interrupt the
held down notes.

**If Sync is on, MIDI Clock input must be provided to the pipe** for the delay effect to work.

| Parameter              | Description                        |
| ---------------------- | ---------------------------------- |
| Bypass                 | Whether processing is enabled.     |
| Delay Time             | The amount of time to delay incoming notes. It can be synced to the incoming tempo, or specified in milliseconds. |
| Note Length            | The note length to use for every note, if Fixed Length is enabled.  |
| Repetitions            | The number of times to repeat a note, can be overriden by Infinite parameter.  |
| Feedback               | The amount of feedback to apply to the velocity of delayed notes. |
| Dry/Wet                | The velocity ratio betwen the original note and the delayed notes:<ul><li>0% - full velocity of original note, 0 velocity of delayed notes,</li><li>50% - full velocity of both parts,</li><li>100% - 0 velocity of original notes, full velocity of delayed notes.</li></ul> |
| Infinite               | If on, the notes will be repeated infinite number of times, unless its velocity reaches 0 first. |
| Sync                   | Switch between synced and freerunning modes. |
| Fixed Length           | Whether to use variable lengths of notes as they were played, or the same fixed length for every note, as set by Note Length parameter. |
| Overdub                | If enabled, new notes will get recorded into the delay loop. |

[List of Pipes](index.md#the-list-of-pipes)
