# Clock

![clock](https://blokas.io/images/midihub/pipes/clock.svg)

Generator pipe that produces MIDI clock at the defined BPM value.
Start, Stop, Continue and Song Position Pointer messages can be used to adjust its sync.
[Transform](transform.md) pipe can be used to convert other messages like Note On to Start,
Stop and Continue as needed and be sent to a Virtual Output to control the Clock pipe.

| Parameter              | Description                    |
| ---------------------- | ------------------------------ |
| Bypass                 | Whether processing is enabled. |
| BPM                    | Beats per minute to generate.  |
| Started                | Whether the clock is started and generating output. |
| Use MIDI DIN A         | Listen to start, stop, continue, song position pointer messages on MIDI DIN A input. |
| Use MIDI DIN B         | Same for MIDI DIN B input.     |
| Use MIDI DIN C         | Same for MIDI DIN c input.     |
| Use MIDI DIN D         | Same for MIDI DIN D input.     |
| Use MIDI USB A         | Same for MIDI USB A input.     |
| Use MIDI USB B         | Same for MIDI USB B input.     |
| Use MIDI USB C         | Same for MIDI USB C input.     |
| Use MIDI USB D         | Same for MIDI USB D input.     |
| Use Virtual A          | Same for Virtual A input.      |
| Use Virtual B          | Same for Virtual B input.      |
| Use Virtual C          | Same for Virtual C input.      |
| Use Virtual D          | Same for Virtual D input.      |
| Use Virtual E          | Same for Virtual E input.      |
| Use Virtual F          | Same for Virtual F input.      |
| Use Virtual G          | Same for Virtual G input.      |
| Use Virtual H          | Same for Virtual H input.      |

<span class="blokas-web-hide">

[List of Pipes](index.md#the-list-of-pipes)

</span>