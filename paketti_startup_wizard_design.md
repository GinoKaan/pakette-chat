# Paketti Startup Wizard Design

## The Problem
Users open Paketti and face:
- Overwhelming menu sprawl (Tools menu packed with options)
- Unclear device hierarchy (Paketti vs Paketti Gadgets)
- No clear entry points for common workflows

## The Solution: Workflow-First Wizard

### Initial Questions (First Launch):

**"What kind of music do you want to make today?"**

1. **MPC-Style Beat Making** (Your example)
   - "I want to play samples like an MPC and build beats"
   - Wizard would guide to: Paketti Drum Machine / Pattern Sampler
   - Setup: Sample slicing → Pad mapping → Pattern sequencing

2. **Bassline Sequencing**
   - "I want to create synth bass patterns quickly"
   - Wizard would guide to: Paketti Bassline / Arpeggiator tools
   - Setup: Sound selection → Pattern creation → Automation

3. **Melodic Pattern Work**
   - "I want to create melodic sequences and hooks"
   - Wizard would guide to: Paketti Pattern Sequencer
   - Setup: Scale selection → Melody generation → Variation

### Wizard Flow for MPC Workflow:

```
Step 1: Load Your Breakbeat
- [Browse] Select your sample file
- [Auto-slice] Detect transients and create slices
- [Manual adjust] Fine-tune slice points if needed

Step 2: Map to Controller
- [MIDI Learn] Tap your controller pads to assign slices
- [Pad layout] Choose 4x4, 8x8, or custom layout
- [Velocity sensitivity] Configure response curves

Step 3: Pattern Setup
- [Pattern length] Set bars and time signature
- [Quantization] Choose grid resolution
- [Play mode] Live recording vs step sequencing

Step 4: Additional Elements
- [Add drums] Load drum samples for layering
- [Add bass] Set up complementary bassline
- [Effects chain] Configure filters, delays, etc.
```

### Key Design Principles:

1. **Workflow-First, Not Tool-First**
   - Don't show "Paketti Bassline" - show "Create Bass Patterns"
   - Hide technical terms behind user goals

2. **Progressive Disclosure**
   - Only show relevant options for the chosen workflow
   - Advanced features remain hidden until needed

3. **Visual Mapping**
   - Show controller layouts matching user's hardware
   - Visual pattern grid that reflects the sequencing approach

4. **Quick Start Templates**
   - "Hip-Hop Beat" template with pre-configured patterns
   - "Techno Bass" template with common sound setups
   - "Ambient Pad" template with evolving textures

### Implementation Strategy:

- Detect first-time users and auto-launch wizard
- Store workflow preferences for future sessions
- Provide "Reset Wizard" option for experimentation
- Include video walkthroughs for each workflow

This approach would solve the overwhelming menu problem by starting with user intentions rather than technical tool names.
## Detailed Wizard Flow for MPC-Style Beat Making

### Step 1: Welcome and Workflow Selection

**Screen 1: Welcome to Paketti!**

*Message:* "Paketti is a powerful pattern-based tool for Renoise. Let's set it up for your workflow."

**Options:**
- [ ] MPC-Style Beat Making (play samples on pads and sequence patterns)
- [ ] Bassline Sequencing (create synth bass patterns)
- [ ] Melodic Pattern Work (create melodies and hooks)
- [ ] Experimental Sound Design (create evolving textures and effects)
- [ ] I'm not sure, show me examples

### Step 2: MPC Workflow - Sample Loading

**Screen 2: Load Your Breakbeat**

*Message:* "Let's load a breakbeat and slice it for your pads."

- [Browse] button to select a sample file
- After loading, show waveform with detected slices (transient detection)
- Slice adjustment tools: 
  - Threshold slider for sensitivity
  - Manual slice point adjustment (click on waveform to add/remove slices)
  - [Auto-slice] button to recalculate
- [Next] when satisfied

### Step 3: MPC Workflow - Pad Mapping

**Screen 3: Map Slices to Pads**

*Message:* "Now let's assign each slice to a pad on your controller."

- Visual representation of a 4x4 pad grid (or user-selectable layout)
- Each pad shows the slice name and waveform preview
- [MIDI Learn] button: when enabled, user hits a pad on their controller to assign the selected slice
- Alternatively, drag and drop slices to pads
- [Test] button: plays the slice when clicking on the pad in the grid
- [Next] when all slices are assigned

### Step 4: MPC Workflow - Pattern Setup

**Screen 4: Pattern Configuration**

*Message:* "Set up your pattern length and quantization."

- Pattern length: 1, 2, 4, 8 bars (with time signature 4/4, 3/4, etc.)
- Grid resolution: 1/4, 1/8, 1/16, 1/32 notes
- Play mode: 
  - [ ] Live recording (record your pad hits in real-time)
  - [ ] Step sequencing (input notes step by step)
- [Next]

### Step 5: MPC Workflow - Additional Elements

**Screen 5: Add More Elements**

*Message:* "Would you like to add more elements to your beat?"

- [ ] Add drum machine (load drum samples for kick, snare, etc.)
- [ ] Add bassline (set up a complementary bass instrument)
- [ ] Add melodic element (lead or pad)
- [ ] Add effects (filter, delay, reverb)

For each selected option, the wizard would guide through a simplified setup for that element.

### Step 6: MPC Workflow - Ready to Play

**Screen 6: You're All Set!**

*Message:* "Your MPC-style setup is ready. Here's how to use it:"

- Quick reference:
  - Press record and play your pads to record a pattern
  - Use the pattern editor to edit notes
  - Switch between patterns to build your song
- [Open tutorial video] link
- [Start using Paketti] button

## Conclusion

This wizard would eliminate the initial overwhelm by:
- Focusing on user goals, not tool names
- Guiding step-by-step through a specific workflow
- Hiding advanced options until the user is ready
- Providing immediate gratification by setting up a working environment quickly

By implementing such a wizard, Paketti would become much more accessible to new users while still retaining its power for advanced users.