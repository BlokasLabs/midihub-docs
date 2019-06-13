# Harmonizer

A modifier pipe that upon receiving a note on message generates up to 8 additional harmonized notes according to the defined intervals.

Interval +0 (the incoming note) is always played.

If two or more intervals are of the same value, only one note of that interval gets produced.

| Parameter              | Description                    |
| ---------------------- | ------------------------------ |
| Bypass                 | Whether processing is enabled. |
| 1st interval           | Semitones offset to the base note. |
| 2nd interval           | Same as above. |
| 3rd interval           | Same as above. |
| 4th interval           | Same as above. |
| 5th interval           | Same as above. |
| 6th interval           | Same as above. |
| 7th interval           | Same as above. |
| 8th interval           | Same as above. |

[List of Pipes](index.md#the-list-of-pipes)
