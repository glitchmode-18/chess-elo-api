# Chess ELO API

A simple Express.js server that fetches and displays Chess.com rating statistics for a specific player.

## Features

- Fetches real-time ratings from Chess.com API
- Displays ratings for three formats:
  - **Rapid** - Classical rapid games
  - **Blitz** - Fast-paced blitz games
  - **Bullet** - Ultra-fast bullet games

## Installation

1. Clone the repository:
```bash
git clone https://github.com/glitchmode-18/chess-elo-api.git
cd chess-elo-api
```

2. Install dependencies:
```bash
npm install express
```

## Usage

1. Start the server:
```bash
node server.js
```

2. Open your browser and navigate to:
```
http://localhost:3000
```

3. The server will display the player's current ratings in the format:
```
Rapid: [rating] | Blitz: [rating] | Bullet: [rating]
```

## Configuration

To fetch ratings for a different player, update the player username in `server.js`:

```javascript
const response = await fetch("https://api.chess.com/pub/player/YOUR_USERNAME/stats");
```

Replace `YOUR_USERNAME` with the desired Chess.com username.

## API Endpoint

**GET** `/`

Returns the current ratings for rapid, blitz, and bullet formats for the configured player.

### Response
```
Rapid: 1850 | Blitz: 1720 | Bullet: 1650
```

## Error Handling

If the API request fails, the server will return:
```
Error fetching rating
```

## Dependencies

- `express` - Web server framework

## License

MIT