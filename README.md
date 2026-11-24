# CINEPHILE. — 시네필 게임

Unofficial movie bluffing party game for 3–16 players. No npm packages, API keys or accounts required.

## Play together on the same Wi-Fi

1. Install Node.js (version 18 or later) from https://nodejs.org/ if needed.
2. Unzip this folder. Open Terminal (macOS) or PowerShell (Windows) in the folder containing `server.js`.
3. Run `node server.js`.
4. The host opens http://localhost:3000. Friends on the same Wi-Fi open the **Friends on same Wi-Fi** address printed in the terminal (not localhost). If asked, allow Node through the firewall on private networks. Guest Wi-Fi may isolate devices.
5. Host enters a name and creates a room. Friends enter their names and the six-character room code. Start once everyone has joined.

Keep the terminal running. The website updates every second. Everyone should use their own browser tab/device. If you refresh, your session normally resumes in the same tab. No new players after a game begins; avoid leaving during the game because all players must submit. Rooms and scores are held in memory, expire after 12 hours of inactivity, and disappear when the server stops.

## Play from different networks

Run this Node server on an internet-accessible Node.js host with HTTPS, or use a private network/VPN shared with your friends. Start command: `node server.js`; the server listens on the `PORT` environment variable (default 3000). No database is required. Share the hosted site URL and room code. The package is not deployed to a public website. The server is intended for private friend groups, not a large public service; use a trusted host and don't enter sensitive information.

## Shared device / offline

Open `index.html` directly in a browser. Select Pass & play. Enter 3–16 names, one per line. Pass the device to each player privately for the secret answers, one-line reviews, and votes. Talk together in the discussion phase. No server or internet necessary.

## Rules

- Each round reveals a film. Answer honestly whether you've watched it; no impostor is randomly assigned.
- Everyone submits a one-line review as though they've seen the film. Then discuss it aloud (use an external voice call if remote). The game supplies optional questions and a timer.
- Give one secret chip to the person you suspect hasn't watched it. No self-voting. After all votes, the game reveals answers, votes and points.
- Classic mode: each most-voted player receives one suspicion point, whether or not they actually watched the movie. Ties award one point to all tied leaders. Highest cumulative score earns the 시네팔이 title.
- Optional Detective mode: earn one point for voting for an unseen player; unseen players earn one extra point if they escape the most-voted group. Highest score wins.
- Choose Mixed, Korean, Hollywood, Animation, World or a custom list. A film is never repeated during one game. If fewer films exist than requested rounds, the game uses the available films.

## Files

- `index.html`: self-contained website; includes game rules engine and interface.
- `engine.js`: game state and rules, also used by the multiplayer server.
- `server.js`: dependency-free Node HTTP server.

The original game was described in the supplied videos and public episode coverage; the private digital confession, timers, tie handling and Detective mode are adaptations. This is not an official Yoo Byung-jae product.

## Version 2
Each round independently has a 3% chance to draw a fictional film. Its status is revealed only after voting; the player’s private claim is retained separately from the actual fact that nobody saw it. Real posters use IMDb-ID-based MetaHub URLs (internet required; availability depends on the external service). The fictional film has an embedded AI-generated poster, so it works offline. Custom titles can optionally include a poster URL as `Title | https://...`. The single fictional title can repeat if the rare event occurs multiple times; it may appear in any deck.
