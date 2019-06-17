# Chance

![chance](https://blokas.io/images/midihub/pipes/chance.svg)

A modifier pipe that randomly drops MIDI notes based on chance and timing.

There's Chance and Timed Chance parameters for defining the percentage chance of keeping the notes playing.
The dice for Timed Chance is rolled every Period of time. If it fails, all the notes will get dropped for the entire Period duration.
If it wins, then the Chance dice is rolled for every note or chord (as set by Granularity) to determine, whether the note(s) will play.

This allows to play or drop entire parts of bars, while still producing variation while notes are being played.
You can always set Chance or Timed Chance to 100% to cause the particular types of dice rolls to always win.

| Parameter              | Description                                                  |
| ---------------------- | ------------------------------------------------------------ |
| Bypass                 | Whether processing is enabled.                               |
| Granularity            | Whether to evaluate the chance per note or per chord.        |
| Chance                 | The chance to play the note or chord.                        |
| Timed Chance           | The chance to play for the period duration.                  |
| Period                 | The length of the timed period until rolling the dice again. |
| Sync                   | Whether the Period is synced to BPM or free running.         |
| Use Velocity           | Whether to use Velocity of the note instead of the Chance parameter. 127 velocity is 100%. |

[List of Pipes](index.md#the-list-of-pipes)
