# TicTacToe.NET-Tournament

Description
-----------
Web-based tic-tac-toe tournament application built with React for the front-end and ASP.NET Core for the back-end.

## Tech Stack
- ASP.NET Core
- React

## Requirements
- Bracket Management API (Hint: Use RESTful routes and clear naming)
- Turn-Based Game Logic (Hint: Validate moves server-side)
- State Synchronization in React (Hint: Utilize React hooks for live updates)
- Code Quality and Testing (Hint: Follow SOLID principles and add tests)

## Installation
1. Clone the repository:
   bash
   git clone https://github.com/your-org/TicTacToe.NET-Tournament.git
   cd TicTacToe.NET-Tournament
   
2. Server setup (ASP.NET Core):
   bash
   cd server
   dotnet restore
   # Configure environment variables:
   #   ASPNETCORE_ENVIRONMENT=Development
   #   ConnectionStrings__DefaultConnection="Server=...;Database=...;User Id=...;Password=...;"
   
3. Client setup (React):
   bash
   cd ../client
   npm install
   

## Usage
1. Start the ASP.NET Core API:
   bash
   cd server
   dotnet run
   
   The API will be available at `https://localhost:5001` (or `http://localhost:5000`).
2. Start the React development server:
   bash
   cd client
   npm start
   
   The app will open at `http://localhost:3000` and proxy API requests to the ASP.NET Core server.

## Implementation Steps
1. Initialize the ASP.NET Core Web API project under `server/`.
2. Define domain models: `Tournament`, `Bracket`, `Match`, `Move`, `Player`.
3. Implement controllers for bracket management using RESTful routes:
   - GET    `/api/brackets`
   - POST   `/api/brackets`
   - GET    `/api/brackets/{id}`
   - PUT    `/api/brackets/{id}`
   - DELETE `/api/brackets/{id}`
4. Create a game logic service to validate moves, enforce turn order, and update match state.
5. Configure Entity Framework Core, add migrations and update the database.
6. Write unit tests for services and controllers following SOLID principles.
7. Initialize React app under `client/` using Create React App.
8. Build key components:
   - `BracketView` for displaying tournament brackets
   - `GameBoard` for the tic-tac-toe grid
   - `MoveList` to show move history
9. Manage state and side-effects with React hooks (`useState`, `useEffect`, `useContext` if needed).
10. Integrate the front-end with the back-end via `fetch` or `axios`.
11. Implement live updates by polling or WebSocket (optional enhancement).
12. Write React tests using Jest and React Testing Library.
13. (Optional) Configure CI with GitHub Actions to run tests on push.

## API Endpoints
- Brackets
  - GET    `/api/brackets`
  - POST   `/api/brackets`
  - GET    `/api/brackets/{bracketId}`
  - PUT    `/api/brackets/{bracketId}`
  - DELETE `/api/brackets/{bracketId}`
- Matches
  - GET    `/api/matches/{matchId}`
  - POST   `/api/matches/{matchId}/move`