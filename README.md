# TapaPalavras API

Backend server for the TapaPalavras word game providing Socket.IO-based real-time multiplayer functionality.

## Features

- Real-time game state management
- WebSocket communication via Socket.IO
- Player management and room functionality
- Game logic implementation

## Tech Stack

- **Runtime**: Node.js
- **Framework**: Express
- **WebSockets**: Socket.IO
- **Language**: TypeScript

## Getting Started

### Prerequisites

- Node.js 16+
- Yarn or npm

### Installation

1. Clone this repository
2. Install dependencies:

```bash
yarn install
# or
npm install
```

3. Create a `.env` file in the root directory:

```
PORT=3001
```

### Development

Start the development server with auto-reload:

```bash
yarn dev
# or
npm run dev
```

The server will start at http://localhost:3001 (or the port specified in your .env file).

### Building for Production

Build the TypeScript files:

```bash
yarn build
# or
npm run build
```

Start the production server:

```bash
yarn start
# or
npm start
```

## Project Structure

- `/src/index.ts`: Main entry point handling Express and Socket.IO setup
- API game logic implemented in the main index.ts file

## API Endpoints

The API primarily uses Socket.IO for real-time communication. Here are the main socket events:

### Client to Server Events

- `join-room`: Join an existing game room
- `create-room`: Create a new game room
- `start-game`: Start the game (host only)
- `select-letter`: Select a letter during gameplay
- `next-player`: Move to the next player

### Server to Client Events

- `room-created`: Notify client of successful room creation
- `room-joined`: Notify client of successful room join
- `game-state`: Send updated game state to all clients
- `game-error`: Notify clients of game errors
- `player-turn`: Notify whose turn it is

## Connecting with the Frontend

Make sure the frontend's environment variables point to this API server's address. See the frontend README for more details.
