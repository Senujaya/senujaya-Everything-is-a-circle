# Circle World

**Submitted for the "Everything is a Circle" Game Jam**

*Circle World* is a fast-paced 3D endless circular runner built in Unity 6. Roll around a continuous cosmic ring track, weave between lanes, collect circular pickups, and dodge incoming spherical obstacles to achieve the highest score possible.

---

## Theme Interpretation: "Everything is a Circle"
Every core element of the game revolves around circular geometry and motion:
- **The Track:** A closed, continuous circular ring where the player runs endlessly lap after lap.
- **The Player:** A rolling 3D sphere driven by polar coordinate trigonometry (`Cos`/`Sin`) and world-space rolling torque.
- **Collectibles & Obstacles:** Rows of circular pickups and hazardous enemy spheres dynamically spawned along the ring's arc.

---

## Gameplay & Mechanics
- **Endless High-Score Loop:** Survive as long as possible while collecting pickups (`+1` point each) and completing laps through re-arming checkpoints (`+20` points per lap).
- **Dynamic Spawning & Lap Cleanup:** Collectible rows and enemy spheres spawn ahead of the player along the circular path, while checkpoints automatically clear active enemies on each completed lap.
- **Lane Steering & Track Bounds:** Responsive left/right steering clamped safely within the inner and outer walls of the ring.
- **Smooth Tangent Follow Camera:** A damped third-person camera that tracks the player's forward tangent vector around the curve.
- **Full Game Flow:** Includes Start Menu, Instructions screen, live HUD score counter, looping background music, and a Game Over screen with final score display and instant Retry.

---

## Controls

| Action | Keys / Input |
| :--- | :--- |
| **Steer Left / Right** | `A` / `D` or `Left Arrow` / `Right Arrow` |
| **Jump** | `Spacebar` *(if enabled in build)* |
| **Menu Navigation** | Mouse Click (`Start`, `OK`, `Retry`, `Exit`) |

---

## Project Architecture (`Assets/Scripts`)
- **`PlayerRunner.cs`** — Calculates circular orbital motion, lane clamping, sphere rolling rotation, and gizmo track bounds.
- **`FollowCamera.cs`** — Smoothly positions and rotates the main camera behind the player along the ring's forward tangent.
- **`CollectibleSpawner.cs` & `Collectible.cs`** — Spawns rows of circular pickups ahead of the player and awards points on trigger collision.
- **`EnemySpawner.cs` & `Obstacle.cs`** — Spawns spherical obstacles along the track arc and triggers Game Over on impact.
- **`Checkpoint.cs`** — Awards lap completion points and clears active enemies when passing the checkpoint trigger.
- **`ScoreManager.cs`** — Singleton UI manager tracking and displaying the live score via TextMeshPro.
- **`GameManager.cs`** — Handles Game Over state, freezes player movement, displays the final score, and manages scene restarts.
- **`MenuManager.cs`** — Controls the Start and Instructions UI panels, background music playback, and application exit.

---

## How to Run
1. Download and extract the build `.zip` archive.
2. Keep all extracted files (`Circle-World.exe`, `Circle-World_Data`, `UnityPlayer.dll`, etc.) together in the same directory.
3. Launch **`Circle-World.exe`** to play.

---

## Credits & Third-Party Assets
- **Engine:** Unity 6 (`6000.5.9f1`) — Universal Render Pipeline (URP) & TextMeshPro
- **Environment & Shaders:**
  - *Free Galaxy Background* (Unity Asset Store)
  - *Free Stylized URP Shaders* (Unity Asset Store)
- **UI & Graphics:** Custom UI Buttons & Sprite Sheets
- **Music:** *Inazuma Eleven GO (Anime) - OST 35: Ailes Jumelles* (Inazeli)
