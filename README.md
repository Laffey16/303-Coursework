# Multiplayer Collect-a-thon — 303 Coursework

A small multiplayer Unity game built for a university networking module. Players join a shared server, run around a level, and race to collect 10 pickups before anyone else. Networking is implemented from scratch using **.NET sockets** (TCP for reliable events, UDP for real-time movement) rather than a prebuilt Unity networking library.


## Highlights

- **Custom networking stack** built on raw .NET `System.Net.Sockets` — no Mirror, Netcode, or Photon.
- **TCP + UDP hybrid:** TCP for connection handshake, usernames, and reliable events (e.g. collectable pickups, scoring); UDP for high-frequency player position and input updates.
- **Client-side prediction** for remote players, with a runtime toggle (press `P`) so you can see the difference with it on vs off.
- **Dedicated server architecture** — the server is a standalone build that clients connect to over the network or on localhost.
- Pause menu with adjustable mouse sensitivity.

## How To Use
1. On the host machine, run **`303 Coursework Server.exe`** from the Server build.
2. On each client machine, run **`303 Coursework.exe`**.
3. Enter:
   - The **IP address** of the machine running the server.
   - A **username**.
   - *Leaving both blank will auto-connect to `localhost`.*
4. Once connected, you're in.
5. Race to collect **10 pickups** before any other player.

## Repository Structure

```
303-Coursework/
├── SocketsTest/         # Unity client project
├── Socket Test Server/  # Unity server project (headless / dedicated)
└── README.md
```

## Controls

| Action | Key |
|---|---|
| Move | `W` `A` `S` `D` |
| Jump | `Space` |
| Toggle remote-player prediction | `P` |
| Pause menu / settings | `Escape` |
