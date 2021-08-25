# MIDI Monitor

![MIDI Monitor](https://blokas.io/images/midihub/midihub-midi-monitor.png)

The MIDI Monitor shows the MIDI events that are being processed by the currently selected pipe in real time.
Filters for incoming and outgoing data can be set up to hide irrelevant events.
The events may be displayed in their raw hex form, or decoded into a readable form.

A BPM field in the monitor header provides the BPM estimate based on the timing of the recent Clock messages, even if they're filtered out from display.

If the monitor is scrolled to the very bottom, it will stay at bottom and follow the new events.

Each event consists of the following fields:

| Field     | Description                   |
| --------  | ----------------------------- |
| Timestamp | It is recorded when the event is being processed, based on the internal clock of Midihub, and is in millisecond accuracy. |
| Type      | They type of the event. It can be one of:<br/><br/>**Event**: A regular MIDI event.<br/>**Timed**: An output was generated based on time.<br/>**Mapping**: A mapped parameter change caused an event to be generated.<br/>**Param Chg**: The pipe parameter change caused an event to be generated.<br/>**Overflow**: If there's more events occurring than the monitor can read, an overflow is recorded, and some monitor data can get dropped. |
| Incoming  | The incoming event data. |
| Outgoing  | The outgoing processed data. If the field is empty, the event was discarded. There may be multiple events produced from a single incoming message, each event is display in its own row. |
