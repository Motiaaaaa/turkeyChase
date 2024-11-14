# Requirements Specification: turkeyChase

## Game Name: turkeyChase
**Team Members**: Kim Foreman, Motiaa Radwan  
**Client**: Pallas Kennedy  
**Date**: November 14, 2024

---

## Game Overview

**Description**:  
*turkeyChase* is a Thanksgiving-themed game where the player controls a turkey that eats Thanksgiving food in a box-shaped room. The size of the room can be selected. As the turkey eats more food, it gets faster. The goal is to eat as much food as possible to reach a higher score. 

**Main Goal**:  
Keep eating food to increase your score and always try to achieve a new high score.

---

## Functional Requirements

### Core Features:
- **Turkey Movement**: The turkey is always in motion and starts in the middle of the room.
- **Speed Increase**: For each piece of food the turkey eats, it gets faster by 1 frame.
- **Room Size**: Choose between three room sizes: small, medium, and large.
- **Score Tracking**: Current score and high score are displayed.
- **No Login**: No login or user authentication required.

### User Interactions:
- **Controls**:  
  - **PC**: Keyboard (arrow keys or WASD).
  - **Mobile/Tablet**: Swipe controls (up, down, left, right).

---

## Non-Functional Requirements

### Usability:
- Easy to understand with intuitive controls.
- Clear layout that shows the current score, high score, and allows for easy navigation of the game.

### Performance:
- **Frame Rate**: Consistent frame rate, with 1 frame added per food eaten.
- **Load Time**: Minimal load time (approximately 3 seconds).
- **Stability**: Game should run smoothly without crashes.

### Cross-Platform Compatibility:
- Accessible on mobile, PC, and tablet devices.
- Layout and controls should adapt to different screen sizes.

---

## Design Requirements

### Graphics and Visuals:
- **Art Style**: Cartoonish and colorful with a Thanksgiving theme.
- **Animations**: Smooth animations when the turkey eats food, with clear visual feedback.
- **Food Items**: Different Thanksgiving foods (pumpkin pie, turkey legs, mashed potatoes, etc.).
- **Speed Effects**: Clear visual effects to indicate when the turkey speeds up (motion blur or speed lines).
- **Background**: The game takes place on a Thanksgiving dinner table with seasonal decorations like autumn leaves and pumpkins.

### Audio:
- **Sound Effects**: Munching noise when the turkey eats food, background music with a festive, Thanksgiving vibe.

---

## Data Requirements

### What Data Needs to Be Saved/Tracked:
- High score.
- Current score.
- On mobile, progress should be saved to ensure continuity.

### How Will Data Be Stored:
- **PC**: Game data will be saved locally for a single session.
- **Mobile**: Game data will be saved on the device to persist progress.

---

## Collaboration with Client

### How Will You Gather Feedback from the Client in Each Sprint:
- After 50 food items are eaten, an optional survey will be provided to gather feedback on gameplay.

### How Will You Ensure the Game is Developing According to the Client’s Needs:
- The development team will conduct regular check-ins to ensure that client expectations are being met.
- Demos will be provided after each sprint, and any required changes will be made based on client feedback.

---

