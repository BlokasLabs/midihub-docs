# Sustain

![sustain](https://blokas.io/images/midihub/pipes/sustain.svg)

A modifier pipe that drops Note Off messages, according to its Mode and Pedal On parameters. Produces all the necessary note off messages once the Pedal is off.
Chord mode can be used to automatically turn off previous notes once a new chord is being played. Sostenuto holds only the notes that were playing at the time the Pedal was pushed, allowing the performer to play further notes as normal.

| Parameter              | Description                                              |
| ---------------------- | -------------------------------------------------------- |
| Bypass                 | Whether processing is enabled.                           |
| Pedal On               | Whether the pedal is currently  on. You should map this parameter. |
| Mode                   | **All**: Sustain all notes.<br/>**Chord**: Add sustained notes while at least one note is held down, once all keys are up and a new note is pressed, old notes will be turned off and newly pressed ones will be sustained.<br/>**Sostenuto**: The notes that were playing at the time the Pedal was pushed will be held, while new notes will play as normal. |

<span class="blokas-web-hide">

[List of Pipes](quick-links.md#io-pipes)

</span>