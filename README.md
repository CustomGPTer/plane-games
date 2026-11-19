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
- `web/`: the games and every screen, written in TypeScript with Preact and built with Vite.
- `android/`: a small Kotlin shell. It shows the bundled games in a web view and gives them the things only
  the phone can do: the Nearby Connections link, storage, vibration, sending the app to another phone,
  scanning a link code, backup files and the update check.
- The `dist` branch holds the released app file and its notes. The Release workflow publishes from it.

## Building

Needs Node 20 or newer, JDK 17 or newer and the Android SDK (platform 35, build-tools 35). Put the SDK path
in `android/local.properties` as `sdk.dir=...`, then:

    cd web && npm install && cd ..
    ./build.sh

The app file lands in `android/app/build/outputs/apk/release/`. Signing reads `android/keystore.properties`
(`storeFile`, `storePassword`, `keyAlias`, `keyPassword`); without that file the build is unsigned. The
signing key is not in this repository.

## Tests

    cd web
    npx vitest run          # the rules of every game, the computer players, backup, cups
    npx vite build
    node tools/local.mjs    # one phone: plays games by taps in headless Chrome
    node tools/e2e.mjs      # two phones: link, play, drop the link, restart, resume
    node tools/b2.mjs       # chess with Stockfish, snakes and ladders, dice over the link
    node tools/b3.mjs       # ludo, backgammon, dominoes, alone and over the link
    node tools/b4.mjs       # the one-player games, battleships, hangman, dots and boxes
    node tools/b5.mjs       # pool: 9-ball and 8-ball by touch, upright, left-handed, two phones
    node tools/b6.mjs       # hints, head starts, clocks, replays, players, backup, the Flight Cup

The play-through scripts need Google Chrome at `/usr/bin/google-chrome`. Run them one at a time. The
two-phone tests use a stand-in radio (two browser tabs) in place of Bluetooth; everything above the radio is
the real code.

## Licence

© 2026 Jonathan Jackson. Published under the GNU General Public License, version 3 or later (see `LICENSE`).
The work it is built on is credited in `NOTICE.md`.
