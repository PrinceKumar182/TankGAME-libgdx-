# 🎮 Tank Star – 2D Physics-Based Tank Battle Game

A cross-platform 2D Player-vs-Player (PvP) artillery tank battle game built using **Java** and the **LibGDX** game engine framework. The game simulates real-time physics-driven projectile trajectories, terrain interaction, fuel-constrained movement, and dynamic health management.

---

## 📌 Product Overview

**Tank Star** delivers a tactical 2D turn-based/real-time artillery duel experience where two players maneuver tanks over custom terrain to launch trajectory-based attacks. 

### Core Gameplay Mechanics:
- **Physics-Driven Ballistics**: Projectile trajectories and impact detection rendered via Scene2D physics integrations.
- **Strategic Fuel Constraints**: Tank movements are governed by a fuel system, forcing players to balance tactical positioning against offensive accuracy.
- **Dynamic Terrain & Level Design**: Tile-based maps engineered using Tiled map editor to influence line-of-sight and projectile paths.
- **In-Game State Management**: Real-time state handling for gameplay pause/resume, health tracking, fuel indicators, and game-over screens.

---

## 🏗️ High-Level Architecture

The game utilizes LibGDX's event-driven architecture and Scene2D screen management model to decouple rendering, input handling, and game state transitions:

```mermaid
flowchart TD
    Launcher[Application Launcher <br/> Desktop / Android] --> Core[LibGDX Game Engine Core]
    
    subgraph Game Runtime
        Core --> ScreenMgr[Scene2D Screen Manager]
        ScreenMgr --> MainMenu[MainMenuScreen]
        ScreenMgr --> GameScreen[GameScreen]
        ScreenMgr --> GameOver[GameOverScreen]
        
        GameScreen --> PhysicsEngine[Physics & Collision Handling]
        GameScreen --> TileMap[Tiled Map Loader & Renderer]
        GameScreen --> UIStage[Scene2D UI Stage<br/>Fuel/Health Indicators]
    end
