# Circle-of-Fifths

## Tool

---

### 1. Music Theory Overview
The Circle of Fifths organizes the 12 chromatic pitches in a sequence of perfect fifths to illustrate **diatonic relationships** (chords occurring naturally within a key).

*   **Outer Ring (Major Keys):** Clockwise movement progresses by perfect fifths (C → G → D); counter-clockwise movement progresses by perfect fourths (C → F → Bb).
*   **Inner Ring (Relative Minors):** Each major key is paired with its relative minor, sharing the same key signature (e.g., C Major and A Minor).
*   **Primary Chords:** When a key (Tonic, **I**) is selected, the tool highlights its immediate neighbors: the Subdominant (**IV**) and Dominant (**V**). Together with their relative minors (**ii, iii, vi**), these six chords form the harmonic foundation of most Western music.

### 2. Implementation: Completed JavaScript
The following logic completes the `updateDashboard` function, ensuring the UI reactively highlights the primary chords in the selected key.

```javascript
            // ... (previous logic)

            // UI Highlight Function
            const highlight = (id, className) => {
                const el = document.getElementById(id);
                if (el) {
                    el.classList.add(className);
                    el.style.opacity = "1";
                }
            };

            const majorPrefix = 'major-note-';
            const minorPrefix = 'minor-note-';

            // Highlight the six primary diatonic chords
            highlight(majorPrefix + i_idx, 'active-note');    // I (Tonic)
            highlight(majorPrefix + iv_idx, 'neighbor-note'); // IV (Subdominant)
            highlight(majorPrefix + v_idx, 'neighbor-note');  // V (Dominant)
            
            highlight(minorPrefix + vi_idx, 'neighbor-note'); // vi (Relative Minor)
            highlight(minorPrefix + ii_idx, 'neighbor-note'); // ii (Supertonic)
            highlight(minorPrefix + iii_idx, 'neighbor-note'); // iii (Mediant)
        }

        init();
```

### 3. Songwriting Applications

#### A. Common Chord Progressions
The Info Panel identifies the components for standard formulas:
*   **Pop Standard:** I – V – vi – IV (e.g., C – G – Am – F)
*   **Jazz Turnaround:** ii – V – I (e.g., Dm – G – C)
*   **Emotional/Ballad:** vi – IV – I – V (e.g., Am – F – C – G)

#### B. Rapid Transposition
To transpose a song, select a new key on the circle. The tool automatically updates the Roman Numeral associations, allowing for instant conversion of chord progressions between keys.

#### C. Key Signature Visualization
The clockwise progression correlates with the addition of sharps (#):
*   **C Major:** 0 sharps
*   **G Major:** 1 sharp (F#)
*   **D Major:** 2 sharps (F#, C#)

### 4. Technical Analysis

*   **Coordinate Mapping:** The UI uses polar-to-cartesian conversion to map the 1D note array to a 2D circular plane using `Math.cos` and `Math.sin`. An offset of `-Math.PI / 2` is applied to align "C" at the 12 o'clock position.
*   **Theming:** The implementation utilizes CSS variables (`:root`) for color states, enabling easy customization or "Dark Mode" integration.
*   **Contextual UI:** The `.wedge` element provides visual grouping, focusing the user's attention on the specific cluster of related chords within the current key.

### 5. Future Feature Roadmap
1.  **Web Audio API:** Integrate [Tone.js](https://tonejs.github.io/) to trigger chord playback on click.
2.  **Diminished Chord Integration:** Include the `vii°` chord for more advanced harmonic analysis.
3.  **Scale Visualization:** Display the specific notes of the selected scale (e.g., C-D-E-F-G-A-B).
4.  **Responsive Layout:** Implement media queries to transition from a side-by-side view to a vertical stack for mobile devices.
Processing...
Strategic Blueprint

Strategic Blueprint
UI/UX Enhancement & Widget Development

APPROVED
1. Executive Summary
2. Widget Enhancement
3. GUI Optimization
4. New Widgets
5. Roadmap
6. Conclusion & Approval
Data Analyst Supplement
Executive Summary
The Omni-Grid platform is entering a critical scaling phase. To maintain its competitive edge as a premier data-grid solution, we must transition from a "feature-complete" tool to a "performance-optimized" ecosystem.













