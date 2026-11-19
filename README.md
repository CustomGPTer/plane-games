# Plane Games

Plane Games is an Android app with twenty games for two phones or one, made to work with no internet: on a
plane, a train, a beach. Two phones link straight to each other by Bluetooth and Wi-Fi, in flight mode or out
of it, and the app keeps score of who is winning. It has no adverts, no accounts and no paid version.

- Website: https://customgpter.github.io/plane-games/
- Latest app file: https://github.com/CustomGPTer/plane-games/releases/latest
- Privacy: https://customgpter.github.io/plane-games/privacy.html

## Good to know before you start

- **Install it before you fly.** After that it needs no connection.
- **In flight mode, switch Bluetooth back on**, and Wi-Fi too if your phone lets you. Follow the cabin
  crew's instructions.
- **Both phones need the app, and both must be Android.** One phone can send the app to the other with no
  internet, from Invite inside the app.
- **The first link asks for the Nearby devices permission.** On Android 12 and older it also asks for
  Location, and Location must be switched on. The app never reads where you are.
- **Linking uses Google Play services.** A phone without it can still play on one phone, against the
  computer and alone.

## What it does

- Fourteen games for two: 9-ball pool, 8-ball pool, chess, draughts, backgammon, dominoes, battleships,
  Connect 4, reversi, ludo, snakes and ladders, dots and boxes, hangman, and noughts and crosses
- Six games to play alone: solitaire, FreeCell, Spider, minesweeper, sudoku and 2048
- Two linked phones, one phone passed between you, or the computer at five levels
- A game that carries on from the same move after the link drops
- Dice and shuffles made by both phones together, so neither can choose them
- Tallies against each person, the Flight Cup, replays, head starts, and clocks for chess and draughts
- More than one player on a phone, a backup file, and a notice when a newer version is ready

## What it cannot do

There is no online play: the other player has to be within a few seats. It does not link with iPhones, and
it links two phones at a time. It is new; if something does not work on your phone, please open an issue.

## What is in this repository

- The website, at the top level (`index.html` and the pages beside it, with `assets/`). GitHub Pages
  serves it from the `main` branch.
- The `dist` branch holds the released app file and its notes. The Release workflow publishes from it.

## Licence

© 2026 Jonathan Jackson. All rights reserved. The app's own source code is not published.
The work it is built on is credited in `NOTICE.md`. The chess computer (Stockfish.js) and the chess
pieces are free software under the GNU General Public License; their complete source code is in
`third-party-sources/plane-games-third-party-sources.zip`, also published on the website.
