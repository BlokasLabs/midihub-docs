# Micro Scale

![mcr_scale](https://blokas.io/images/midihub/pipes/mcr_scale.svg)

A modifier pipe that adjusts MIDI note numbers and generates pitch bend messages according to a micro tuning defined in Scala language.

When retuning, the Micro Scale pipe may sometimes need to produce a different note along with a pitch bend to achieve the desired base note frequency. It uses the closest natural note to the desired frequency plus the necessary pitch bend amount to reach that frequency.

This pipe acts similar to the [Dispatcher](dispatcher.md) pipe, as it dispatches each note to a new channel,
since Pitch Bend messages apply for every note in the channel, to get correct polyphony, each note must go
to its own channel.

Midihub can hold up to 8 micro tunings at a time and they are shared between all the presets. Each micro tuning may consist of up to 127 tuning values.

Go to Device->Micro tunings... to manage the currently uploaded micro tunings.

Check out the [Scala website](http://www.huygens-fokker.org/scala/),
[Scala software](http://www.huygens-fokker.org/scala/downloads.html) and the
[Scala examples](http://www.huygens-fokker.org/scala/examples.html) section to get started with micro tunings!

::: tip
When using a sequencer to record and play back micro-tuned notes, it's crucial to ensure that the sequencer records the Pitch Bend messages sent by the Micro Scale pipe. If the sequencer only records the note data, the tuning will be incorrect on playback.

The recommended workflow is as follows:

1. Send the output of the Micro Scale pipe to your sequencer.
2. Record the performance in your sequencer.
3. Disable the Micro Scale pipe in Midihub.
4. Send the output of the sequencer directly to your synthesizer.

This ensures that the sequencer captures the complete, micro-tuned performance, including the necessary Pitch Bend data, and plays it back correctly.
:::

| Parameter              | Description                                |
| ---------------------- | ------------------------------------------ |
| Bypass                 | Whether processing is enabled.             |
| Scale                  | The micro scale to apply to the incoming notes. |
| Pitch Bend Depth       | The depth in semitones of the target synthesizer. This parameter should match what is specified in the manual or in the synthesizer configuration. |
| Base Note              | The base MIDI note used as a reference for the start of the scale. |
| Base Frequency         | The frequency of the base note. |
| Auto Frequency         | Initializes Base Frequency based on Base Note's frequency in 440Hz tuning standard. |
| Always Send Pitch Bend | Force sending Pitch Bend messages. Enable this parameter only if the receiving device is playing wrong notes. This disables data size optimization which relies on receiving device memorizing last Pitch Bend value on a channel. |
| Use Ch 1               | Use this channel for sending notes and pitch bends. |
| Use Ch 2               | Same as above.                             |
| Use Ch 3               | Same as above.                             |
| Use Ch 4               | Same as above.                             |
| Use Ch 5               | Same as above.                             |
| Use Ch 6               | Same as above.                             |
| Use Ch 7               | Same as above.                             |
| Use Ch 8               | Same as above.                             |
| Use Ch 9               | Same as above.                             |
| Use Ch 10              | Same as above.                             |
| Use Ch 11              | Same as above.                             |
| Use Ch 12              | Same as above.                             |
| Use Ch 13              | Same as above.                             |
| Use Ch 14              | Same as above.                             |
| Use Ch 15              | Same as above.                             |
| Use Ch 16              | Same as above.                             |

<span class="blokas-web-hide">

[List of Pipes](quick-links.md#io-pipes)

</span>