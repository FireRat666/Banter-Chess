# BanterChess

A multiplayer chess game designed for **BanterVR**, built with **A-Frame** (Frontend) and **Node.js/Socket.io** (Backend).

## Features
- **3D Chess Board**: Implemented using A-Frame primitives for performance.
- **Real-time Multiplayer**: Socket.io synchronizes moves between players instantly.
- **Pure JavaScript Logic**: Game rules validation handles by `chess.js`, decoupled from the view layer.
- **BanterVR Ready**: Compatible with BanterVR's web view integration.

## Prerequisites
- Node.js (v14+ recommended)
- npm

## Installation

1.  Clone the repository.
2.  Install dependencies:
    ```bash
    npm install
    ```

## Usage

1.  Start the server:
    ```bash
    npm run dev
    ```
    (Or `npm start` for production mode)

2.  Open your browser to:
    `http://localhost:3000`

3.  **To Play**:
    - Open two browser tabs/windows to valid multiplayer locally.
    - Click a piece to select it (Green highlight).
    - Click a valid destination square (Blue highlight) to move.
    
## Project Structure
- `server/`: Node.js Express server w/ Socket.io.
- `public/`: Static files served to client.
    - `index.html`: Main A-Frame scene.
    - `js/chess-game.js`: Game logic class.
    - `js/board-components.js`: A-Frame components for interaction.

## BanterVR Integration
To use in BanterVR, host this application (e.g., on Render, Glitch, or a VPS) and use the URL within a BanterVR browser or "Go to URL" trigger.

### Configuration
You can customize the game's visuals by appending parameters to the URL.

```html
<script src="https://banter-chess.onrender.com/js/embed.js?boardPosition=0+1.1+-2&boardScale=1&boardRotation=0+45+0"></script>
```

**Parameters:**
- `boardPosition`: `x y z` (Default: `0 1.1 -2`)
- `boardRotation`: `x y z` (Default: `0 0 0`)
- `boardScale`: `s` or `x y z` (Default: `1`)
- `hideUI`: `true` to hide the Reset button
- `preset`: Skybox preset (e.g. `starry`)

*Old parameters like `dressing` and `fog` have been removed in favor of native Banter environment controls.*
