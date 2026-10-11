# Playora

Free games for everyone. Racing, board and card games, word games, puzzles and more.

## Structure
- `index.html` - home screen (categories, music, diary, game launcher)
- `games/` - one HTML file per game
  - `car-race.html` - Car Race (5 tracks with changing scenery, 12 cars, two-way road with traffic, auto-accelerate, chase + cockpit camera, rewards by position and time)
  - `whot.html` - Whot card game
- `music1.mp3` - background song (plays on the home screen only, never inside games)

## Add a new game
1. Put the game in `games/your-game.html` (it can post `{type:'playora:exit'}` to the parent to go back,
   and `{type:'playora:result', game:'Name', text:'Won!'}` to add an entry to the Diary).
2. In `index.html`, find the game in the `CATS` list and add `f:'games/your-game.html'`.
3. Add the file to `CORE` in `sw.js` and bump the cache name (for example `playora-v4`; it is now `playora-v3`).

## Domain
`CNAME` still contains the old domain. Replace its single line with your new .com
(for example `playora.com`) before publishing on GitHub Pages.

## Orientation
Car Race is landscape; Whot stays upright (it also has a landscape layout). Games declare this with `o:'landscape'|'portrait'` in `index.html`.
Car Race: games are played sideways. When a game opens, the launcher goes fullscreen and locks landscape where the browser allows it.
Where it does not (for example iPhone Safari), the game is turned 90 degrees so it still fills the screen.
