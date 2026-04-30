# User Manual: Vector Hunt

## Game Overview

Vector Hunt is a 2D physics game inspired by Duck Hunt. The player aims and shoots at moving ducks while the game displays real physics data such as velocity, speed, gravity, wind, collision behavior, and orbital force.

The game has two modes:

1. Duck Hunt Mode
2. Orbital Mode

## Starting the Game

Open `index.html` in a web browser such as Chrome, Edge, or Firefox.

No installation is required.

## Interface

### Left Physics Panel

The left panel shows physics data. In Duck Hunt Mode, it shows:

- `vx`
- `vy`
- speed
- angle
- gravity
- wind
- collision type
- final velocity after collision
- momentum value
- physics mode

In Orbital Mode, it shows:

- distance `r`
- gravitational force `F`
- acceleration `a`
- `vx`
- `vy`
- speed
- body mass
- planet mass
- projectile status

### Bottom Control Panel

The bottom panel includes:

- Reset button
- Mode toggle button
- Target Score selector
- Score
- Time
- Misses
- Short How to Play instructions

## Duck Hunt Mode

Duck Hunt Mode is the main game mode.

### How to Play

1. Move the mouse to aim.
2. The yellow vector shows the direction and strength of the shot.
3. Click to shoot.
4. Hit ducks to score points.
5. Reach the selected Target Score before time runs out.

### Target Score

The player can choose:

- 50
- 100
- 150
- 200

Higher target scores increase difficulty.

## Orbital Mode

Orbital Mode is a separate mode designed to demonstrate orbital mechanics.

### How to Play

1. Click the mode button to switch to Orbital Mode.
2. Aim at the robotic space ducks.
3. Click to fire one laser.
4. Only one laser can be active at a time.
5. Wait until the laser hits something or leaves the screen before firing again.
6. The laser curves because of gravitational attraction from the black hole.
7. Reach the selected Target Score before time runs out.

### Orbital Duck Waves

If all robotic ducks are cleared and time remains, a new wave appears.

The number of robotic ducks depends on Target Score:

- 50 points: 3 ducks
- 100 points: 4 ducks
- 150 points: 6 ducks
- 200 points: 8 ducks

## Physics Concepts Used

### Dynamics: F = m*a

Dynamics describes how forces affect motion. The game uses force and acceleration to update object movement. In Orbital Mode, gravitational force is converted into acceleration using:

```text
a = F / m
```

### Vectors, Velocity, and Speed

The game uses vector components:

```text
vx = horizontal velocity
vy = vertical velocity
speed = sqrt(vx^2 + vy^2)
```

The left panel displays these values during gameplay.

### Collisions: Momentum Conservation

When the projectile hits a duck in Duck Hunt Mode, the collision is inelastic. The projectile and duck move together after impact.

The final velocity is based on conservation of momentum:

```text
vf = (m1*v1 + m2*v2) / (m1 + m2)
```

### Orbital Mechanics: F = G(m1*m2)/r^2

Orbital Mode uses Newtonian gravitation:

```text
F = G(m1*m2)/r^2
```

Where:

- `F` is gravitational force
- `G` is the gravity constant used in the game
- `m1` is planet or black hole mass
- `m2` is laser/object mass
- `r` is distance between objects

The force points toward the black hole, causing the laser to curve.

## Winning and Losing

The game ends when:

- The player reaches the selected Target Score
- Time runs out

When the player reaches the target, the game displays:

```text
Target Reached
Final Score: X / Target
```

When time runs out, the game displays:

```text
Time Over
Final Score: X / Target
```

## Reset

The Reset button restarts the current mode. It resets:

- score
- time
- active projectile
- ducks
- shooting state
