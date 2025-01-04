# Game-in-assembler

## Overview
This project is a sprite-based game implemented in assembly language. The game utilizes a simple graphical environment to display and interact with objects on the screen. The user can choose flower colors, move a sprite, and interact with displayed flowers through key presses or by hovering over them.

---

## Features

1. **Interrupt-Driven Design**
   - Handles vertical synchronization (VSync) and keyboard interrupts using an interrupt service routine (ISR).
   - Supports smooth rendering and responsive input handling.

2. **Graphics Rendering**
   - Displays text and objects on the screen using VRAM manipulation.
   - Offers a multi-screen interface with different content displayed sequentially.

3. **User Interaction**
   - Allows movement of a sprite using keyboard keys (W, A, S, D).
   - Changes the sprite color when hovering over specific objects or pressing designated keys.

4. **Gameplay Elements**
   - Users can "choose" a flower color by pressing keys (`Y`, `G`, `L`, `P`) or by hovering the sprite over flowers on the screen.
   - Displays dynamic feedback to the user.

---

## Requirements

- A system capable of running the assembly program with a compatible emulator or hardware setup.
- Graphics card capable of text and basic graphical modes.
- Keyboard for user input.

---

## Program Flow

### Initialization
1. Set up the stack pointer.
2. Configure the graphics card for text mode and enable interrupts.

### Screen Flow
1. **Title Screen**:
   - Displays introductory text with instructions.
   - Waits for 3 seconds before clearing the screen.

2. **Gameplay Instructions**:
   - Displays additional instructions for controlling the sprite.
   - Waits for another 3 seconds before clearing the screen.

3. **Main Game**:
   - Displays flowers and initializes the user-controlled sprite.
   - Allows user interaction with flowers through movement and key presses.

### Interrupt Handling
- **VSync Interrupt**:
  - Ensures smooth frame rendering.
- **Keyboard Interrupt**:
  - Captures key presses to trigger corresponding actions.

### Game Loop
1. Read the sprite's current position.
2. Check for user input to move the sprite or change its color.
3. Detect when the sprite hovers over a flower and change its color.
4. Wait for a few frames to control the speed of movement.
5. Repeat the loop until the program halts.

---

## Controls

- **Movement**:
  - `W`: Move up
  - `A`: Move left
  - `S`: Move down
  - `D`: Move right

- **Color Selection**:
  - `Y`: Yellow
  - `G`: Green
  - `L`: Lila
  - `P`: Pink

---

## Functions and Code Structure

### Main Functions

- **ISR (Interrupt Service Routine)**:
  - Handles VSync and keyboard interrupts.

- **wait_frames**:
  - Delays the execution by a specified number of frames.

- **front_page / dfront_page**:
  - Displays or deletes strings on the screen.

- **color**:
  - Changes the sprite's color based on user input.

- **hover**:
  - Detects when the sprite hovers over a flower and changes its color.

- **movement**:
  - Handles sprite movement based on key presses.

- **flowers**:
  - Displays flowers on the screen with distinct colors.

- **display_objects**:
  - Initializes and displays the user-controlled sprite.

---

## How to Run
1. Assemble the code using an appropriate assembler (e.g., `NASM`).
2. Load the assembled binary onto a compatible emulator or hardware.
3. Run the program and follow the on-screen instructions.

---

## Future Improvements
- Add scoring or objectives to enhance gameplay.
- Implement more complex sprite animations.
- Include sound effects for interactions.

---

## Troubleshooting
- **No Display**:
  - Ensure the graphics card is configured properly.
  - Verify the hardware or emulator supports the specified I/O operations.

- **No Response to Key Presses**:
  - Check keyboard interrupt handling.
  - Verify that the ISR is correctly configured.

---

## Acknowledgments
This program is a demonstration of assembly-level programming for interactive graphics and user input handling.
