# Mobile Board Game Score Tracker Guidelines

## Project Overview
A mobile-friendly single-page HTML application for tracking scores in various board games. 
It uses `localStorage` for persistence and is designed to run locally in a mobile browser.

## Supported Games
- Wingspan
- 7 Wonders
- Everdell
- Hearts
- Spades
- Carcassonne
- Agricola

## Data Structure
### LocalStorage Keys
- `boardGameScore_currentGame`: Stores the state of the active game (game id, players, scores).
- `boardGameScore_savedPlayers`: Stores an array of player profiles (name, color) for reuse.

### Game Definition Object
When adding a new game, define it with:
- `id`: Unique string
- `name`: Display name
- `categories`: Array of strings
- `boxArt`: URL to a box art image (or placeholder)

### Application State
The `state` object in `index.html` manages the following:
- `currentGame`: The active game state (or `null`).
- `savedPlayers`: Array of up to 10 recently used players.
- `isNegativeMode`: Boolean for score adjustment direction.

## UI & Interaction
### Score Tracking
- **Direct Entry**: Tap any score value to open a numeric input for direct editing.
- **Quick Adjust**: Use the vertical buttons (`1`, `5`, `10`) to modify scores.
- **Toggle Mode**: Use the "+ Add Points" / "- Subtract Points" toggle to change the direction of quick adjustments.

### Player Management
- **Add Players**: Use the "+ Add Player" button or select from "Recent Players".
- **Delete Players**: Remove saved players by clicking the 'x' on their chip.
- **Rename Players**: Edit player names directly in the score sheet headers.

## Development Preferences
- **Mobile First**: Use responsive design (meta viewport, flexible units).
- **Vanilla JS**: No heavy frameworks to ensure it runs easily as a local file.
- **Single File**: Use a single `BoardGameScore.html` for maximum portability as a local file.

## How to Add a New Game
1. Open `BoardGameScore.html`.
2. Find the `GAMES` constant in the script tag.
3. Add a new game object following the existing structure.
4. Update the UI logic if special scoring is required.
