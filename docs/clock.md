# Clock

![clock](https://blokas.io/images/midihub/pipes/clock_hybrid.svg)

A pipe that can be placed both as a Generator (leftmost) pipe or as a Modifier (inline) pipe.
It produces MIDI clock messages at the defined BPM value. Tap Tempo can be used to adjust the BPM in real time, or to count-in if the Clock was stopped.
When in Modifier position, incoming Start, Stop, Continue and Song Position Pointer messages can be used to adjust its sync.

| Parameter              | Description                    |
| ---------------------- | ------------------------------ |
| Bypass                 | Whether processing is enabled. |
| BPM                    | Beats per minute to generate.  |
| Started                | Whether the clock is started and generating output. |
| Start                  | Start the clock, also producing a MIDI Start message. |
| Continue               | Start the clock, also producing a MIDI Continue message. |
| Stop                   | Stop the clock, also producing a MIDI Stop message. |
| Measure Duration       | The duration of the measure in Beat units. (The upper part of Time Signature) Relevant for Tap Tempo. |
| Beat Duration          | The duration of a single beat, always a power of 2. (The lower part of Time Signature) Can be used for BPM multiplication purposes. |
| Tap Tempo              | Tap Tempo button - adjusts BPM according to rolling average of up to 32 taps. See Tap Tempo notes below. |
| Nudge Up               | Produces BPM rate 10% higher while held down. |
| Nudge Down             | Produces BPM rate 10% lower while held down. |

## Tap Tempo

While the Clock is stopped, Tap Tempo waits for Measure Duration amount of taps and automatically starts the Clock on the next beat.

If the Clock is running, Tap Tempo adjusts the BPM on the second tap, and keeps averaging the BPM for up to 32 taps.

After 3 seconds since the last tap, the previous taps are cleared.

## MIDI Mappings

Start, Continue, Stop and Tap Tempo buttons can be mapped to a CC or MIDI Note. In case of CC, only the value 127
triggers the control, while any Note On and Note Off velocities are sufficient to trigger the buttons.

Nudge Up and Nudge Down expect CC values above 63 to enable the Nudge, while any Note On and Note Off velocities enable and disable the Nudge.

<span class="blokas-web-hide">

[List of Pipes](quick-links.md#io-pipes)

</span>
