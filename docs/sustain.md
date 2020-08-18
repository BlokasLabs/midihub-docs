# Sustain

![sustain](https://blokas.io/images/midihub/pipes/sustain.svg)

A modifier pipe that drops Note Off messages, if its sustain parameter is on. Produces all the necessary note off messages once it is switched off.
Chord mode can be used to automatically turn off previous notes once a new chord is being played.

| Parameter              | Description                                              |
| ---------------------- | -------------------------------------------------------- |
| Bypass                 | Whether processing is enabled.                           |
| Sustain On             | Whether sustain is on.                                   |
| Mode                   | **All**: Sustain all notes.<br/>**Chord**: Add sustained notes while at least one note is held down, once all keys are up and a new note is pressed, old notes will be turned off and newly pressed ones will be sustained. |

<span class="blokas-web-hide">

[List of Pipes](index.md#the-list-of-pipes)

</span>