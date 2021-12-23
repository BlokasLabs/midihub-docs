# CC LFO

![cc_lfo](https://blokas.io/images/midihub/pipes/cc_lfo_hybrid.svg)

A pipe that can be placed both as a Generator or as a Modifier.
It produces an LFO waveform, as defined by the many parameters,
on the selected CC value, Channel 1. Place a [Channel Remap](channel-remap.md) pipe to the
right of the LFO to change the channel.

If it is placed as a Modifier, it can be synchronized to the beat,
as well as it can apply modulation to previous CC LFO pipes in the pipeline,
and/or to the incoming CC value from the input.

See the preview at the bottom of the the Properties panel to visualize how the LFO waveform looks like.

| Parameter              | Description                    |
| ---------------------- | ------------------------------ |
| Bypass                 | Whether processing is enabled. |
| Started                | Whether the LFO clock is started. |
| CC                     | The CC value id to use. |
| Resolution             | The resolution to use. Use as low resolution as possible for your desired rate. |
| Rate                   | Rate of the LFO in Hz, or time units in case it is synced to the beat. |
| Phase                  | The phase offset of the LFO. |
| Depth                  | The depth of the LFO. Use 64 for full 0-127 range. |
| Waveform               | The waveform of the LFO. |
| Duty Cycle             | The duty cycle of the PWM wave. Not applicable to other waveforms. |
| Output Enabled         | Whether the output is actually enabled. Output may be disabled while keeping the LFO clock still ticking. |
| Mode                   | **Free running**: waveform is generated freely.<br/>**Active Mod.**: LFO is actively modulating (offsetting) the incoming CC value of the same id, generating new values even if incoming CC value is not changing.<br/>**Passive Mod.**: LFO is passively modulating (offseting) the incoming CC value of the same id, only on receiving the actual CC value. |
| Retrigger              | Controls retriggering behavior - LFO waveform can be retriggered on individual notes or on chords. |
| Sync to BPM            | (Only as Modifier) Whether to sync to the incoming BPM clock. |
| Retrigger on SysCommon | (Only as Modifier) Whether to retrigger on system common messages such as 'start', 'continue', 'song position pointer'. |
| Start on SysCommon     | (Only as Modifier) Whether to start ticking the LFO clock on system common messages such as 'start', 'continue', 'song position pointer'. |
| Manual Retrigger       | A button to manually retrigger the LFO. It can be mapped to a control which guarantees low latency to take effect as soon as the mapped control is moved. |
| One Shot               | Produce only one cycle of the wave. It has to be retriggered using Manual Retrigger parameter, or according to Retrigger mode parameter to produce another cycle of the wave. |

<span class="blokas-web-hide">

[List of Pipes](index.md#the-list-of-pipes)

</span>
