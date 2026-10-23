# MMO RPG — Godot Client

[Ler em Português](README.md)

Godot 4 client for the [MMO RPG](https://github.com/Luisr-nunes/mmo_rpg) prototype, built to compare the engine against the Unity client on the same server.

## About

The client connects to the WebSocket server from the `mmo_rpg` project, sends movement and gather actions and draws the world from the state it receives. All game logic (positions, resources, d20 rolls, inventory) lives on the server; the client only renders and sends commands.

## Features

- Connects to `ws://localhost:8765` and shows the connection state (connecting, connected, disconnected).
- Movement with WASD or arrow keys.
- Gathers the nearest resource with Space or Enter.
- Shows d20 roll results and the amount of wood in the inventory.
- Renders background, players and trees with its own sprites in `assets/`.

## Tech stack

- Godot 4 (Forward+ renderer)
- GDScript with `WebSocketPeer`
- JSON messages: `init`, `game_state`, `dice_roll` (server) and `move`, `collect` (client)

## Structure

```
mmo_rpg_godot/
├── project.godot   # project configuration
├── Main.tscn       # main scene
├── Main.gd         # networking, player input and drawing
└── assets/         # bg.png, player.png, objects.png
```

## Running

1. Start the server from the main project:

   ```bash
   git clone https://github.com/Luisr-nunes/mmo_rpg.git
   cd mmo_rpg
   pip install websockets
   python server/server.py
   ```

2. Open this project in Godot 4 (Import → `project.godot`) and press F5. The `Main.tscn` scene loads automatically.

## Author

Luís Nunes — [GitHub](https://github.com/Luisr-nunes) · [LinkedIn](https://www.linkedin.com/in/luis-nunes-dev/)
