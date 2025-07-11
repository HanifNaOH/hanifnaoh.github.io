---
title: "Rusty and the Reborn of Widget"
date: 2025-07-10
draft: false
tags: ["Game Review", "Idle Game", "Farming Simulator"]
description: "Decomposing Rusty’s Retirement: An Idle Farming Simulator"
---

## Rusty and the Reborn of Widget

![Rusty Retirement](https://shared.akamai.steamstatic.com/store_item_assets/steam/apps/2666510/extras/close-up.gif?t=1743519099)

## Introduction

Rusty’s Retirement is an idle farming simulator developed and published by Mister Morris Games. It was released on April 26, 2024 for PC (Windows and Mac). Uniquely, the game is designed to run as a small window at the bottom (or side) of your screen, allowing you to play it while engaging in other activities on your computer.

## Core Gameplay Mechanics and Systems

### Game Systems

{{< mermaid >}}
classDiagram
    direction TD

    %% Player progression & economy
    class PlayerProgression {
      +int spare_parts
      +int bio_fuel
      +add_spare_parts(int)
      +consume_bio_fuel(int)
    }

    %% World grid
    class TileMap {
      +Tile[][] tiles
      +get_tile(x:int, y:int) Tile
      +set_tile(x:int, y:int, tile:Tile)
    }

    class Tile {
      +Plant? plant
      +bool is_watered
      +harvest():Resource[]
      +water():void
      +plant_seed(seed:Seed):void
    }

    %% Farming
    class Plant {
      +string type
      +int growth_timer
      +grow(delta:float):void
      +is_mature():bool
    }

    class Seed {
      +string type
      +int germ_time
    }

    %% Automated helpers
    class AutomationBot {
      +string bot_type
      +int level
      +perform_task(tile:Tile):void
      +upgrade():void
    }

    %% Main characters (Rusty + helpers)
    class NPC {
      +string name
      +NPC_State state
      +move_to(tile:Tile):void
      +perform_action(tile:Tile):void
    }

    class NPC_State {
      <<enumeration>>
      IDLE
      MOVING
      WATERING
      PLANTING
      HARVESTING
    }

    %% UI & control
    class GameManager {
      +PlayerProgression PlayerProgression
      +TileMap GameMap
      +Inventory PlayerInventory
      +start():void
      +update(delta:float):void
      +save():void
      +load():void
    }

    class Inventory {
      +int Money
      +Resource[] resources
      +add_resource(Resource):void
    }

    %% Relationships
    GameManager --> PlayerProgression
    GameManager --> TileMap
    GameManager --> Inventory
    GameManager --> AutomationBot
    GameManager --> NPC

    TileMap --> Tile
    Tile --> Plant
    Tile --> Seed

    PlayerProgression "1" --> "*" Resource

    NPC_State <|-- NPC
    NPC --> TileMap
    AutomationBot --> Tile

{{< /mermaid >}}
This may be overwhelming at frist but for programmers, this is the complexity of the game systems that make it so engaging. The game is built around a series of interconnected systems that allow players to manage resources, automate tasks, and progress through a farming simulation. (Quality of life not included in this breakdown lol)

### Game Core Loop

{{< mermaid >}}
flowchart LR
    A[Growing Crop] --> B[Progression]
    B[Progression] --> C[Idle Waiting]
    C[Idle Waiting] --> A[Growing Crop]
{{< /mermaid >}}
For non-programmers, the core loop of the game can be summarized as follows:

1. Start the game and let crops grow idly.
2. Check if any crops are mature for harvesting.
3. If yes, harvest the crops and collect resources.
4. Allocate resources either to reinvest in the farm or hold for later.
5. Decide whether to buy upgrades or hire new helpers.
6. Repeat the loop.

## Aesthetics

### User Interface

The user interface of Rusty’s Retirement is designed to be intuitive and user-friendly.
![UI](https://cdn.imgchest.com/files/739cx6vjq27.png)

### Art Style

![Art Style](https://cdn.imgchest.com/files/y8xcnkojxx4.png)

The Game height is around 320px, which is a common resolution for pixel art games. This resolution allows for detailed pixel art while maintaining a nostalgic aesthetic. The game’s visuals are charming and contribute to the overall relaxing atmosphere, making it visually appealing to players who enjoy pixel art games.

### Sound Design

{{< youtubeLite id="6FR0zOl6V3Q" label="Soundtrack Rusty" >}}

Chilling and relaxing music. If you have any idea what type of music this is, please let me know. But for me its just chill.

For the SFX, there is not much since the game intent to not distract you while you are doing other tasks. The game has a few sound effects for actions like planting, harvesting, and watering crops, but they are subtle and not intrusive.

## Progression and Replayability

### Building & NPCs

![Building & NPCs](https://cdn.imgchest.com/files/7w6c2vdaoly.png)

You can build various structures and hire NPCs to help automate tasks. Some NPCs has unique abilities that can help you progress faster, or provide unique benefits such as decoration or new resources

### New Crops

![New Crops](https://cdn.imgchest.com/files/yd5cer68lz4.png)

Well, bored of the same crops? You can unlock new crops by progressing through the game and completing certain tasks. Each crop has its own growth time, yield, and resource value, adding variety to your farming experience.

### Stats View

![Stats View](https://cdn.imgchest.com/files/7mmc9rpd8l7.png)

I forgot which NPC that unlock this, but you can view your stats and progress in the game. This feature allows you to track your achievements, resources collected, and overall farm performance. It adds a layer of depth to the game, reflecting the player’s progress and providing a sense of accomplishment.

### Animals

![Animals](https://cdn.imgchest.com/files/739cx6v2m87.png)

They are moving around the farm, produce i think its fertilizer, and can be fed to increase their productivity.

### Bee!🐝

![Bee](https://cdn.imgchest.com/files/7lxcpd8q2e7.png)

They need Berry bushes to produce honey, i love them when they are flying around the farm. They are cute and adds a nice touch to the game’s atmosphere.

### Decoration

![Decoration](https://cdn.imgchest.com/files/4jdcvj5l9g4.png)

Players can customize their farm with various decorative items, adding a personal touch to their environment. This feature enhances the cozy atmosphere of the game and allows for creative expression. Not all of the decorations are just for aesthetics, the sign post can be used to mark what crops are planted in a specific area.

### Start Over (Reset)

![Start Over (Reset)](https://cdn.imgchest.com/files/7w6c2vdj99y.png)

Unlock new Map or change your layout by creating new playthroughs. This feature allows players to reset their farm and start over, providing a fresh experience with new challenges and opportunities. It adds replayability to the game, encouraging players to experiment with different strategies and layouts.

## Unique & Standout Features

### Widget like Interface

![Widget like Interface](https://shared.akamai.steamstatic.com/store_item_assets/steam/apps/2666510/extras/sits-at-bottom-of-screen.gif?t=1743519099)

The game features a unique widget-like interface that allows players to keep the game running in a small window while they engage in other tasks. This design choice makes it easy to play Rusty’s Retirement alongside other activities, enhancing its idle gameplay experience and standout from traditional idle games.

### Idle Gameplay

Since the game is designed to run in a small window, it allows players to engage in other activities while the game progresses. This idle gameplay mechanic is a key feature, enabling players to manage their farm without needing to be constantly active in the game. So it fell on Cozy Genre, which is a sub-genre of idle games that focuses on relaxing and casual gameplay.

### Pixel Art Style

Its Pixel Art with a cozy aesthetic is another standout feature. The game’s visuals are charming and nostalgic, appealing to players who enjoy pixel art games. The art style contributes to the overall relaxing atmosphere of the game, making it visually appealing.

### Grid and free will

The game features a grid-based layout that allows players to place crops and structures freely. This grid system provides a structured yet flexible environment for players to manage their farm, enabling them to optimize their layout for efficiency and aesthetics.

## Summary

This game is nice 8/10, I love the widget-like interface that allows me to play it while doing other tasks. The game is designed to be played in a small window, making it easy to engage in other activities on your computer while managing your farm. The idle gameplay mechanic is a key feature, allowing players to progress without needing to be constantly active in the game. However, there is lack of end game content.

For Future Me: <https://www.imgchest.com/p/a8465mwnwyx>
