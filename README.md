# Bitasmbl-Simple-Real-Time-Casino-Game-System-00e805-b9bbb1a779c7

## Description
A minimal real-time casino platform where authenticated players manage wallets, create and join game tables, and play a simple game. Services communicate via ASP.NET Core and SignalR; players interact through a React frontend. Lobby manages tables, enforces rules, and handles payouts by calling the Wallet service.

## Tech Stack
- ASP.NET Core
- Docker
- SQL
- React
- SignalR

## Requirements
- Implement Lobby payout logic so that after receiving the winner from Game1, 95% of the prize pool is credited to the winner via Wallet and 5% remains as margin.
- Validate dynamic rules from games.json when creating a game table (e.g., delayTime within allowed range).
- Use SignalR exclusively for player-driven actions (create/join/approve/cancel and in-game events) without HTTP polling.
- Protect wallet endpoints so only Lobby can perform debit/credit/rollback operations.
- Show real-time lobby updates in the React UI when tables are created, joined, approved, or canceled.

## Installation
bash
git clone https://github.com/MrBitasmblTester/Bitasmbl-Simple-Real-Time-Casino-Game-System-00e805-b9bbb1a779c7.git
cd Bitasmbl-Simple-Real-Time-Casino-Game-System-00e805-b9bbb1a779c7
# Backend
dotnet restore
# Frontend
cd frontend
npm install


## Usage
bash
# Backend
cd backend
dotnet run
# Frontend
cd frontend
npm start


## Implementation Steps
1. Implement Lobby payout logic to distribute 95% of the prize pool to the winner via Wallet, retaining 5% as margin.
2. Load and validate dynamic rules from games.json when creating a game table (including allowed delayTime).
3. Configure SignalR hubs so all player-driven actions and in-game events use SignalR only.
4. Secure Wallet service so only Lobby can access debit, credit, and rollback operations.
5. Wire up React components to SignalR for real-time lobby updates when tables change state.

## API Endpoints
- Lobby ↔ Wallet: debit, credit, rollback (restricted to Lobby).