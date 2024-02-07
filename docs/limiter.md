# Limiter

![limiter](https://blokas.io/images/midihub/pipes/limiter.svg)

A modifier pipe that limits the values of the MIDI messages it's set to work with.

The incoming values are clipped to fit in range [Minimum;Maximum].

| Parameter              | Description                                              |
| ---------------------- | -------------------------------------------------------- |
| Bypass                 | Whether processing is enabled.                           |
| Kind                   | Selects the MIDI message kind to process.                |
| Minimum                | The lowest value.                                        |
| Maximum                | The highest value.                                       |
| Any Id?                | Whether to work with all Ids of the set Kind.            |
| Id                     | If 'Any Id?' is deactivated, the Id of the Note / Control / Channel to work with. |

<span class="blokas-web-hide">

[List of Pipes](quick-links.md#the-list-of-pipes)

</span>