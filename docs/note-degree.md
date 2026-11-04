# Note to Degree / Degree to Note

![Note to Degree](https://blokas.io/images/midihub/pipes/note_to_degree.svg) ![Degree to Note](https://blokas.io/images/midihub/pipes/degree_to_note.svg)

These modifier pipes convert between MIDI notes and **scale degrees**: the positions of notes in a scale, shown as I, II, III and so on. In C major, C is I, D is II and E is III.

Use **Note to Degree** before other note-processing pipes to work in scale steps, then **Degree to Note** to turn the result back into playable notes. This lets you build chords that stay in scale or play the same pattern in a different scale.

## Working in Scale Steps

Between the two pipes, degrees are carried as ordinary MIDI note numbers, with each step representing the next degree. With a seven-note scale, seven steps make an octave. These intermediate note numbers are intended for further processing; place **Degree to Note** before the Output to hear the intended pitches.

### Example: Three-Note Chords

**Input -> Note to Degree -> Harmonizer -> Degree to Note -> Output**

Set both conversion pipes to **Base: C** and **Preset: Major**. In [Harmonizer](harmonizer.md), enable **Play Root Note?**, set **1st interval** to **+2** and **2nd interval** to **+4**, and leave the remaining intervals at **0**. Set **Inversion** to **0** and **Steps per Octave** to **7**.

Each key in the scale now produces a three-note chord: the played degree, its third and its fifth. C produces C-E-G, D produces D-F-A, and B produces B-D-F. The chords follow the scale, giving major, minor or diminished triads as needed. Notes outside the selected input scale are discarded when their mapping is **Off**.

Choose a different **Base** in Degree to Note to play these chords in another key, or a different **Preset** to change the output scale. Keep **Degree Count** the same in both conversion pipes, and match Harmonizer's **Steps per Octave** to it so chord inversions use the correct octave size.

### Other Pipes to Try Between the Converters

Between Note to Degree and Degree to Note, a change of **+1** to a note number moves up one scale degree. Controls labelled in semitones still change these intermediate note numbers, so their offsets act as scale steps here.

| Pipe | Ideas to try |
| ---- | ------------ |
| [Transpose](transpose.md) | Shift a melody up or down by scale degrees. **Semitones: +1** moves to the next degree; **+7** moves up an octave in a seven-note scale. |
| [Delay](delay.md) | Use **Pitch Shift** to make each delayed repeat climb or descend through the scale. Try **+1** for rising steps or **-2** for falling thirds. |
| [Harmonizer](harmonizer.md) | Build chords from degree offsets, as in the example above, and explore different inversions. |
| [Randomizer](randomizer.md) | Choose **Pitch (semitones)** for random movement by scale degrees, or **Pitch (octaves)** for random octave shifts. Use **Positive** and **Negative** to limit the movement. |
| [Arpeggiator](arpeggiator.md) | Turn held degrees into patterns and extend them with **Octave Range**. MIDI Clock must reach the pipe. |
| [Note Remap](note-remap.md) | Compress, expand or reverse a range of degrees to reshape a melody. Its range bounds refer to the intermediate note numbers, rather than the final pitches. |

For Harmonizer, Arpeggiator and Randomizer's **Pitch (octaves)** mode, set **Steps per Octave** to the converters' **Degree Count**: for example, **7** for major or minor, or **5** for a pentatonic scale. This sets the size of octave shifts; individual note offsets still count one degree at a time.

## Reverse

The **Reverse** button switches between Note to Degree and Degree to Note and builds the corresponding reverse map. For example, duplicate a Note to Degree pipe (Ctrl+Drag on Windows/Linux, Option+Drag on macOS) and click **Reverse** on the copy to create its matching Degree to Note pipe.

Changing **Type** alone switches direction without rebuilding the map. Use **Reverse**, or choose a Preset after changing Type, to set up the matching conversion.

## Parameters

| Parameter | Description |
| --------- | ----------- |
| Bypass | Whether processing is enabled. |
| Type | **Note to Degree** or **Degree to Note**. Changes how the mapping table is interpreted. Not MIDI-mappable. |
| Base | The base note of the scale. Use **C** when the player or original sequence uses a C-based scale, such as C major or C minor. In Degree to Note, this selects the base note of the output scale. |
| Degree Count | Number of degrees per octave, from **2 to 15**. Use 7 for a major or minor scale, or 5 for a pentatonic scale. Not MIDI-mappable. |
| Preset | Loads a built-in scale's mapping and Degree Count. Can be MIDI-mapped. |
| Note rows (Note to Degree) | Choose the degree assigned to each of the 12 notes, or **Off** to discard that note. |
| Degree rows I-XV (Degree to Note) | Choose the output note for each degree, or **Off** to discard it. The number of active rows follows Degree Count. |
| Natural 6th / Natural 7th | Available in **Degree to Note** with the **Minor** scale. Raise the sixth or seventh by one semitone. See below. |

## Minor Scale Options

**Natural 6th** and **Natural 7th** are available only with the **Minor** scale in the **Degree to Note** direction. They let you choose between the lowered and raised forms of those degrees while playing.

For example, use **Note to Degree: C Major** followed by **Degree to Note: C Minor**. You can play the C major keys and control which form of C minor comes out:

- **Both off:** natural minor, with Ab and Bb.
- **Natural 7th on:** harmonic minor, with Ab and B.
- **Both on:** ascending melodic minor, with A and B.

In traditional melodic minor, the sixth and seventh are raised when ascending and lowered when descending. Map these switches to buttons or pedals to choose the form that fits your melody. The pipe does not detect the melody's direction automatically; the choice stays with you. Harmonic minor uses the raised seventh in either direction.

<span class="blokas-web-hide">

[List of Pipes](quick-links.md#remap-pipes)

</span>
