---
title: "Rhythm-Based Target Shooter"
date: 2026-03-10T13:35:41+07:00
draft: false
description: "A rhythm game built in Unreal Engine where players shoot targets synchronized to MIDI music tracks, combining precision shooting with musical timing."
tags: ["Unreal Engine", "Game Development", "MIDI", "C++", "Blueprint"]
categories: ["Game Development"]
---

## Overview

A unique rhythm-based shooting game developed in Unreal Engine that challenges players to shoot targets in sync with music. The game reads MIDI files to generate gameplay patterns, creating a dynamic shooting experience where precision and rhythm awareness are equally important.

## Gameplay Concept

Players face a series of targets that appear and must be shot at specific moments dictated by the music's rhythm. The game parses MIDI files in real-time, converting musical notes into target spawn events, creating a seamless fusion of audio and gameplay mechanics.

### Core Features

- **MIDI-Driven Gameplay**: Dynamic target generation based on MIDI file parsing
- **Rhythm Synchronization**: Targets spawn and must be hit precisely on beat
- **Scoring System**: Combo multipliers and accuracy ratings based on timing precision
- **Multiple Difficulty Levels**: Adjustable note density and timing windows
- **Visual Feedback**: Real-time hit indicators and beat visualization
- **Audio Integration**: Synchronized sound effects and music playback

## Technical Implementation

### MIDI File Processing

Implemented a custom MIDI parser in Blueprint that reads standard MIDI files and extracts:

- Note timing and duration
- Velocity (intensity) values
- Tempo and time signature information

The parser converts MIDI events into gameplay events, allowing any MIDI file to be used as a level blueprint.

### Target Spawning System

Created a spawn manager that:

- Schedules target appearances based on MIDI note timing
- Adjusts spawn positions based on note pitch
- Applies different target types based on note velocity
- Maintains synchronization between audio and visual elements

### Shooting Mechanics

Developed precise hit detection with:

- Timing window evaluation (Perfect/Good/Miss)
- Audio-visual feedback system
- Combo tracking and score multiplier
- Accuracy statistics tracking

### Audio Synchronization

Ensured tight audio-visual sync through:

- High-precision timing system
- Latency compensation
- Audio buffer management
- Beat prediction algorithms

## Technical Challenges

### Audio Latency Management

Addressed input lag and audio buffer delays by implementing a predictive timing system that compensates for hardware latency, ensuring visual elements align with perceived audio.

### Performance

Optimized object pooling for target spawning to maintain consistent frame rates during high-density sections, crucial for rhythm-based gameplay where timing precision is critical and VR optimization is important.

### MIDI Format

Created a flexible parser supporting various MIDI file formats and edge cases like tempo changes and multiple simultaneous tracks using the existing plugins.

## Technologies Used

- **Engine**: Unreal Engine 5.7
- **Programming**: Blueprint for gameplay logic
- **Audio**: Unreal's audio engine with custom MIDI integration
- **File Parsing**: Custom C++ MIDI file parser
- **UI**: Unreal Motion Graphics (UMG)

## Development Insights

This project deepened my understanding of:

- Real-time audio synchronization in game engines using MIDI data and Niagara for visual effectss
- File format parsing and data structure design
- Performance optimization for rhythm-based games
- Event-driven architecture for gameplay systems
- Player feedback systems and game feel

## Future Enhancements

Potential improvements include:

- Multiplayer support with split-screen
- Visual effects system responsive to music intensity
- Leaderboard integration using Epic Online Services
- Support for different weapon skin to make play more personalized
- Dynamic difficulty adjustment based on player performance

## Conclusion

This game looks fun but i have meta quest 2 which is not developer friendly, like i have to use a lot of workarounds to get live link working, and the camera tracking is just a mess.
