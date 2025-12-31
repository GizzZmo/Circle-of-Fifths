# Circle of Fifths Tool

A music theory tool for understanding and visualizing the relationships between musical keys.

## Table of Contents

- [About](#about)
- [What is the Circle of Fifths?](#what-is-the-circle-of-fifths)
- [Features](#features)
- [Installation](#installation)
- [Usage](#usage)
- [Music Theory Background](#music-theory-background)
- [Contributing](#contributing)
- [License](#license)

## About

The Circle of Fifths Tool is designed to help musicians, composers, and music students understand the relationships between different musical keys. This tool provides an interactive and visual way to explore key signatures, chord progressions, and harmonic relationships.

## What is the Circle of Fifths?

The Circle of Fifths is a fundamental concept in music theory that illustrates the relationships among the 12 tones of the chromatic scale, their corresponding key signatures, and the associated major and minor keys. Moving clockwise around the circle, each key is a perfect fifth higher than the previous one. Moving counterclockwise, each key is a perfect fifth lower (or a perfect fourth higher).

### Key Benefits:

- **Understand Key Signatures**: Quickly determine how many sharps or flats are in any key
- **Find Relative Keys**: Easily identify major and minor keys that share the same key signature
- **Compose Chord Progressions**: Discover harmonically related chords for smooth transitions
- **Transpose Music**: Navigate between keys efficiently
- **Learn Music Theory**: Visual representation makes complex relationships intuitive

## Features

- **Interactive Visualization**: Explore the circle of fifths in an intuitive interface
- **Key Signature Reference**: View sharps and flats for all major and minor keys
- **Chord Relationships**: Understand which chords work well together
- **Educational Tool**: Perfect for music students and teachers
- **Quick Reference**: Fast lookup for composers and arrangers

## Installation

### Prerequisites

(To be added based on implementation)

### Setup

```bash
# Clone the repository
git clone https://github.com/GizzZmo/Circle-of-Fifths-.git

# Navigate to the project directory
cd Circle-of-Fifths-

# Additional setup steps will be added as the project develops
```

## Usage

(Usage instructions will be added as features are implemented)

### Basic Example

The Circle of Fifths tool helps you:

1. **Find Key Signatures**: Select a key to see its sharps or flats
2. **Navigate Keys**: Move clockwise (+5th) or counterclockwise (-5th) between keys
3. **Discover Relationships**: See which keys are closely related for modulation

### Common Use Cases

- **Songwriting**: Find keys that work well together for key changes
- **Practice**: Plan your practice routine by working through the circle
- **Analysis**: Analyze harmonic progressions in existing music
- **Ear Training**: Develop your ability to recognize key relationships by ear

## Music Theory Background

### The Structure

The Circle of Fifths organizes all 12 chromatic pitches in a circle, where:

- **Clockwise movement**: Each step moves up by a perfect fifth (7 semitones)
- **Counterclockwise movement**: Each step moves down by a perfect fifth (up by a perfect fourth)

### Key Signatures

- **Sharp Keys** (Clockwise from C): G, D, A, E, B, F♯, C♯
  - Each key adds one sharp in the order: F♯, C♯, G♯, D♯, A♯, E♯, B♯
  
- **Flat Keys** (Counterclockwise from C): F, B♭, E♭, A♭, D♭, G♭, C♭
  - Each key adds one flat in the order: B♭, E♭, A♭, D♭, G♭, C♭, F♭

### Relative Major and Minor

Every major key has a relative minor key that shares the same key signature:
- The relative minor is located 3 semitones (a minor third) below its relative major
- Example: C major and A minor both have no sharps or flats

### Closely Related Keys

Keys adjacent to each other on the circle (one step away) share all but one note and are considered closely related:
- They differ by only one sharp or flat
- Modulations between these keys sound smooth and natural
- Example: C major (no sharps/flats) is closely related to G major (1 sharp) and F major (1 flat)

## Contributing

Contributions are welcome! If you'd like to contribute to this project:

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add some amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

Please ensure your contributions:
- Follow the existing code style
- Include appropriate documentation
- Add tests if applicable
- Maintain music theory accuracy

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Resources

### Learn More About Music Theory

- [Music Theory Basics](https://www.musictheory.net/)
- [Circle of Fifths Explained](https://www.musictheory.net/lessons/24)
- [Understanding Key Signatures](https://www.musictheory.net/lessons/23)

### Contact

For questions, suggestions, or feedback, please open an issue on GitHub.

---

**Note**: This tool is under active development. Features and documentation will be expanded as the project evolves.

# Circle-=======of-Fifths

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














