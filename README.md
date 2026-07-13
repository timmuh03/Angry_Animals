# Angry Animals

A physics-based 2D browser game built with Godot and GDScript. Launch a parrot across each level, destroy every cup, and try to finish using as few attempts as possible.

## Play the Game

**[Launch Angry Animals](https://angry-animals.vercel.app/)**

The game runs directly in a modern web browser.

## Gameplay

1. Select one of the three available levels.
2. Click and drag the parrot back from its starting position.
3. Release to launch it toward the cups.
4. Destroy every cup to complete the level.
5. Press **Space** to return to the level menu.

Your best score for each level is the lowest number of launch attempts used to complete it.

## Features

- Physics-based drag-and-release launching
- Visual aiming and launch-strength indicator
- Three selectable levels
- Attempt tracking and per-level best scores
- Locally saved score data
- Collision, splash, launch, and completion audio
- Cup-destruction animation and level-completion feedback
- Browser-ready WebAssembly export

## Built With

- **Godot 4.4**
- **GDScript**
- **Godot Web Export** using JavaScript and WebAssembly
- **Vercel** for the live deployment

## Project Structure

```text
Angry_Animals/
├── Autoloads/          # Global signal and score managers
├── LevelButton/        # Level-selection button scene and logic
├── Main/               # Main menu and level selection
├── scenes/
│   ├── Animal/         # Player movement, aiming, and launch logic
│   ├── Cup/            # Cup target and destruction behavior
│   ├── GameUI/         # Level, attempt, and completion display
│   ├── Level/          # Shared level logic and individual stages
│   ├── Scorer/         # Attempt counting and completion checks
│   └── Water/          # Water collision and splash behavior
├── assets/             # Images, fonts, and audio
├── Git_Repo/           # Exported browser build
├── export_presets.cfg  # Godot web-export configuration
└── project.godot       # Godot project configuration
```

## How It Works

The game uses a small state machine to manage the parrot's ready, dragging, and released states. The drag distance is limited and converted into a physics impulse when the player releases the mouse.

Global signals keep gameplay systems separated. Launch attempts, destroyed cups, score updates, and level completion are communicated through an autoloaded signal manager. A separate score manager stores each level's best result in a local JSON file.

## Run Locally

### Prerequisites

Install [Godot 4.4](https://godotengine.org/download/archive/4.4-stable/).

### Setup

```bash
git clone https://github.com/timmuh03/Angry_Animals.git
cd Angry_Animals
```

1. Open Godot.
2. Import the project by selecting `project.godot`.
3. Open the imported project.
4. Press **F6** or use the **Run Project** button.

## Export for the Web

The repository includes a configured Godot **Web** export preset.

1. Open **Project > Export** in Godot.
2. Select the **Web** preset.
3. Export the project to the `Git_Repo/` directory.
4. Make sure the deployment serves `index.html` and the related `.js`, `.wasm`, and `.pck` files together.

## Future Improvements

- Add more levels and obstacle types
- Add a restart-level control
- Improve mobile input support
- Add animated aiming feedback and trajectory previews
- Add a cleaner deployment workflow that separates source files from generated exports

## Author

Created by [Tim Muhlestein](https://github.com/timmuh03).
