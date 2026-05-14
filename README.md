# Xenharmonic Microtonal Synth

A browser-based synthesizer for exploring microtonal and xenharmonic tuning systems, playable directly from your QWERTY keyboard. Built with the Web Audio API.

![Synth Screenshot](screenshot.png)

---

## Features

- **5 waveforms** — Sine, Square, Sawtooth, Triangle, and PWM (Pulse Width Modulation) with LFO
- **ADSR envelope** — Attack, Decay, Sustain, Release via rotary knobs
- **7 tuning systems** — from standard 12-TET to 53-TET and Just Intonation
- **Up to 12-voice polyphony**
- **Live oscilloscope display**
- **OP-1 inspired hardware aesthetic**

---

## Playing the Synth

Your QWERTY keyboard maps to 40 consecutive chromatic steps in the selected tuning, from lowest (bottom-left) to highest (top-right):

```
1  2  3  4  5  6  7  8  9  0   ← highest
Q  W  E  R  T  Y  U  I  O  P
A  S  D  F  G  H  J  K  L  ;
Z  X  C  V  B  N  M  ,  .  /   ← lowest
```

Use the **− / +** octave buttons to shift the entire keyboard up or down. Multiple keys can be held simultaneously for chords and polyphony.

---

## Tuning Systems

### What is a Tuning System?

Western music is built on **12-TET** — 12 equally spaced pitches per octave. But this is just one of countless ways to divide the octave. Other cultures and composers have explored tunings with more steps, pure mathematical ratios, or entirely different interval structures. This synth lets you play and compare seven of them.

Intervals are measured in **cents**: 1 octave = 1200 cents, 1 semitone in 12-TET = 100 cents.

---

### 12-TET — Standard Western
*12 equal divisions of the octave · Each step = 100 cents*

The tuning system underlying virtually all modern Western music — pianos, guitars, synthesizers. The octave is divided into 12 logarithmically equal semitones. While convenient for transposition and modulation, its intervals are all slightly "out of tune" compared to pure mathematical ratios. The perfect fifth is 2 cents flat (700 vs 702 cents), and the major third is 14 cents sharp (400 vs 386 cents).

**Best for:** standard Western harmony, pop, classical, jazz

---

### 19-TET
*19 equal divisions of the octave · Each step ≈ 63.2 cents*

19-TET is a meantone system with a noticeably smoother character than 12-TET. Its minor third (5 steps = 315.8 cents) nearly perfectly matches the pure 6:5 ratio (315.6 cents), and its major third (6 steps = 378.9 cents) is closer to pure than 12-TET's. A key feature: **sharps and flats are different pitches** — C# and D♭ are distinct notes, restoring the enharmonic distinctions that 12-TET collapses.

19-TET was advocated by Renaissance theorist Guillaume Costeley and twentieth-century composer Joseph Yasser. It has a characteristically "bluer" and more expressive melodic quality.

**Best for:** extended meantone harmony, blues-inflected melody, Renaissance-style counterpoint

---

### 24-TET — Quarter-Tone *(default)*
*24 equal divisions of the octave · Each step = 50 cents*

24-TET adds a **quarter-tone** between every semitone of the standard 12-TET scale. This is the most widely used microtonal system in practice, forming the basis of **Arabic maqam**, **Turkish makam**, and **Persian dastgah** music — traditions with centuries of repertoire built around quarter-tone inflections.

In the 20th century, Western composers including Charles Ives, Alois Hába, and Ivan Wyschnegradsky wrote quarter-tone music. The quarter-tone is notated with arrows (↑ = quarter-tone sharp).

**Common maqamat accessible in 24-TET:** Rast, Bayati, Hijaz, Saba, Nahawand, and many others.

**Best for:** Arabic, Turkish, and Persian music; experimental Western composition; expressive melodic inflection

---

### 31-TET
*31 equal divisions of the octave · Each step ≈ 38.7 cents*

31-TET is considered by many microtonalists to be the finest meantone system available. Its major third (10 steps = 387.1 cents) differs from the pure 5:4 ratio (386.3 cents) by less than 1 cent — essentially perfect to the ear. The minor third, perfect fourth, and perfect fifth are all excellent approximations of their just counterparts.

The Dutch physicist and composer **Adriaan Fokker** championed 31-TET in the 20th century and built 31-tone organs for it. It was also theorized by 16th-century composer Nicola Vicentino, who built a keyboard instrument called the *archicembalo* based on a 31-step division.

**Best for:** Renaissance and Baroque harmony with superior consonance, extended chromaticism, microtonal jazz

---

### 53-TET
*53 equal divisions of the octave · Each step ≈ 22.6 cents*

53-TET is extraordinary for its near-perfect approximations of just intonation. Its perfect fifth (31 steps = 701.9 cents) differs from the pure 3:2 ratio (702.0 cents) by just 0.07 cents — essentially imperceptible. Its major third (17 steps = 384.9 cents) is within 1.4 cents of pure.

This system was known independently across cultures. The Chinese music theorist **Jing Fang** described it in 45 BCE. Helmholtz noted it in *On the Sensations of Tone* (1863). It provides an extremely fine-grained palette — 53 distinct pitches per octave — making it capable of representing almost any just interval with high accuracy.

**Best for:** near-just intonation, intricate harmonic structures, academic and experimental use

---

### Pythagorean Tuning
*12 pitches per octave derived from stacked pure fifths · Pure 3:2 ratios*

All pitches are generated by stacking **pure perfect fifths** (ratio 3:2 = 702 cents), then collapsing them into a single octave. The result is that every fifth in the system is perfectly pure, but the major third is wide and harsh — 81:64 = 407.8 cents, versus the pure 5:4 = 386.3 cents.

This was the dominant tuning of **medieval European music**, where composers wrote in styles that privileged the fifth and fourth over the third. In that context, the wide thirds are not a flaw — they create a characteristic brightness and tension that suits modal counterpoint.

**Best for:** medieval and early Renaissance polyphony, drone-based music, understanding historical tuning practice

---

### Just Intonation (5-limit)
*12 pitches per octave using pure integer ratios of 2, 3, and 5*

Just intonation uses simple integer frequency ratios to produce **acoustically pure intervals**. In 5-limit just intonation, all ratios involve only the prime factors 2, 3, and 5:

| Interval | Ratio | Cents |
|---|---|---|
| Unison | 1:1 | 0 |
| Minor second | 16:15 | 111.7 |
| Major second | 9:8 | 203.9 |
| Minor third | 6:5 | 315.6 |
| Major third | 5:4 | 386.3 |
| Perfect fourth | 4:3 | 498.0 |
| Tritone | 45:32 | 590.2 |
| Perfect fifth | 3:2 | 702.0 |
| Minor sixth | 8:5 | 813.7 |
| Major sixth | 5:3 | 884.4 |
| Minor seventh | 9:5 | 1017.6 |
| Major seventh | 15:8 | 1088.3 |

The result is supremely consonant chords in the home key. The tradeoff: unlike equal temperament, just intonation is not octave-equivalent across transposition — moving to a different key introduces mistuned "wolf" intervals. It is best suited to music that stays within a limited harmonic area.

**Best for:** sustained chords, drone music, acoustic demonstration, understanding harmonic physics

---

## Controls

| Control | Function |
|---|---|
| **Waveform buttons** | Select oscillator shape |
| **A knob** | Attack — time to reach full volume |
| **D knob** | Decay — time to fall to sustain level |
| **S knob** | Sustain — volume while key is held |
| **R knob** | Release — time to fade after key release |
| **VOL knob** | Master output volume |
| **Tuning dropdown** | Select tuning system |
| **− / +** | Shift base octave down or up |
| **PANIC** | Immediately silence all voices |

Knobs can be adjusted by **clicking and dragging up/down**, or using the **scroll wheel**.

### PWM Controls

When PWM waveform is selected, three additional controls appear:

| Control | Function |
|---|---|
| **Width** | Pulse duty cycle (5%–95%). 50% = square wave |
| **LFO Rate** | Speed of automatic width modulation (0.05–20 Hz) |
| **LFO Depth** | How much the LFO sweeps the pulse width |

---

## Further Reading

- [Xenharmonic Wiki](https://en.xen.wiki) — comprehensive resource on microtonal music and tuning theory
- [The Xenharmonic Alliance](https://www.facebook.com/groups/xenharmonic2/) — active community of microtonal composers
- *On the Sensations of Tone* — Hermann von Helmholtz (1863)
- *Genesis of a Music* — Harry Partch (1949) — foundational text on just intonation and instrument building

---

## Tech Stack

- Vanilla HTML / CSS / JavaScript
- [Web Audio API](https://developer.mozilla.org/en-US/docs/Web/API/Web_Audio_API)
- No dependencies, no build step — open `index.html` in any modern browser
