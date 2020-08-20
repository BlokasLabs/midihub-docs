# Micro Scale

![mcr_scale](https://blokas.io/images/midihub/pipes/mcr_scale.svg)

A modifier pipe that adjusts MIDI note numbers and generates pitch bend messages according to a micro tuning defined in Scala language.

This pipe acts similar to the [Dispatcher](dispatcher.md) pipe, as it dispatches each note to a new channel,
since Pitch Bend messages apply for every note in the channel, to get correct polyphony, each note must go
to its own channel.

Midihub can hold up to 8 micro tunings at a time and they are shared between all the presets. Each micro tuning may consist of up to 127 tuning values.

Go to Device->Micro tunings... to manage the currently uploaded micro tunings.

Check out the [Scala website](http://www.huygens-fokker.org/scala/),
[Scala software](http://www.huygens-fokker.org/scala/downloads.html) and the
[Scala examples](http://www.huygens-fokker.org/scala/examples.html) section to get started with micro tunings!

| Parameter              | Description                                |
| ---------------------- | ------------------------------------------ |
| Bypass                 | Whether processing is enabled.             |
| Scale                  | The micro scale to apply to the incoming notes. |
| Pitch Bend Depth       | The depth in semitones of the target synthesizer. This parameter should match what is specified in the manual or in the synthesizer configuration. |
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

[List of Pipes](index.md#the-list-of-pipes)

</span>