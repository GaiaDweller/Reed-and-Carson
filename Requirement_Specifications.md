# Requirements Specification: A-Steriods

Game Name: A-Steriods
Team Members: Carson Kasper, Reed Stewart
Client: Arson Developoment
Date: November 14th 2024

## Game Overview

Brief Description: Space Shooter is a top-down arcade-style shooter where players pilot a spaceship, avoiding and destroying incoming asteroids while collecting power-ups.
Main Goal: The main objective is to survive as long as possible by shooting asteroids, collecting power-ups, and achieving a high score. Players lose when they run out of lives.

## Functional Requirements

### Core Features:
Players control the spaceship's position and orientation.
The game tracks and displays the player’s highest score.
Players can submit scores to a global leaderboard.
Power-ups provide temporary enhancements, such as spread shots, screen-clearing abilities, and increased fire rates.

### User Interactions:
PC Version: Movement via WASD; orientation determined by mouse position. Left mouse button fires.
Mobile Version: Movement controlled by a digital joystick; the ship orients towards the second finger on the screen and fires automatically when touched.

## Non-Functional Requirements

### Usability:
The game should have intuitive controls and a clear interface for power-up durations and scores.
Easy-to-understand mechanics, suitable for quick play sessions.

### Performance:
Consistent frame rate of at least 60 FPS.
Minimal load times (under 5 seconds).
Smooth performance with multiple objects and effects on screen.

### Cross-Platform Compatibility:
The game will support PC and mobile platforms with platform-specific control schemes.
It must run seamlessly on different devices and screen sizes.

## Design Requirements

### Graphics and Visuals:
Modern yet simple 2D graphics with smooth animations.
Asteroids and power-ups visually distinct, with clear indicators for effects and durations.

### Audio:
Background music that fits the space theme.
Sound effects for shooting, asteroid destruction, collecting power-ups, and losing lives.

## Data Requirements

### What Data Needs to be Saved or Tracked:
High scores and the player's current progress (e.g., lives remaining).
Global leaderboard data.

### How Will the Data be Stored:
High scores will be stored locally and synced to the leaderboard via a server.

## Collaboration with Client

### How Will You Gather Feedback from the Client in Each Sprint:
Regular playtesting sessions and surveys.
Direct meetings to gather input on mechanics and aesthetics.

### How Will You Ensure the Game is Developing According to the Client’s Needs:
Frequent progress demos at major milestones.
Iterative development with continuous feedback integration.



