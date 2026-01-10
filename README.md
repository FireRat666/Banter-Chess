# BanterChess

A 3D chess game designed for **Banter**, now rebuilt to be **serverless**. It can be hosted on any static web host (like GitHub Pages) and uses Banter's shared space state for real-time multiplayer synchronization.

## Features
- **3D Chess Board**: A fully interactive 3D chess board rendered directly in your Banter space.
- **Serverless Real-time Multiplayer**: Game state is synced between players using Banter's public space properties, removing the need for a backend server.
- **Pure JavaScript Logic**: Game rules and validation are handled by the robust `chess.js` library.
- **100% Banter Embeddable**: Designed from the ground up to be dropped into any Banter world with a single script tag.

## Usage

There is no server or installation required. You can use this project by hosting it on a static file server or directly from a service like GitHub Pages.

### Banter Integration

To add the chess board to your Banter world, add the following HTML to your space's configuration:

```html
<!-- 
  Add this script tag to your Banter world's HTML.
  Make sure the URL points to the 'embed.js' file on your hosting provider (e.g., GitHub Pages).
-->
<script src="https://your-github-username.github.io/Banter-Chess/js/embed.js"></script>
```

Replace `your-github-username` with your actual GitHub username.

You can have multiple, independent chess games in the same space by adding a unique `instance` name to the script URL.

```html
<!-- Game 1 -->
<script src=".../embed.js?instance=lobby_game"></script>

<!-- Game 2 (in another part of the space) -->
<script src=".../embed.js?instance=fireside_game&boardPosition=10+1+-5"></script>
```

## Project Structure
- `index.html`: The main file that loads the `embed.js` script. This is the file you would point a Banter browser to if you are not using the script embed method.
- `js/embed.js`: The core logic. This script loads all dependencies, creates the 3D board, and handles game state synchronization.
- `models/`: Contains the `.glb` 3D models for the chess pieces.

## Configuration
You can customize the game's appearance and position by appending URL parameters to the `embed.js` script source.

**Example:**
```html
<script src=".../embed.js?boardPosition=0+1+-2&boardScale=0.8&boardRotation=0+45+0"></script>
```

**Parameters:**
- `instance`: A unique ID for the game board. Use this to have multiple separate games in one Banter space. Defaults to the URL of the page.
- `boardPosition`: The `x y z` position of the board in the world. (Default: `0 1.1 -2`)
- `boardRotation`: The `x y z` rotation of the board in degrees. (Default: `0 0 0`)
- `boardScale`: A uniform scale `s` or per-axis `x y z` scale. (Default: `1`)
- `hideUI`: Set to `true` to hide the Reset button.
- `resetPosition`: The `x y z` position of the reset button relative to the board.
- `resetRotation`: The `x y z` rotation of the reset button.
- `resetScale`: The `x y z` scale of the reset button.