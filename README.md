# Playora

Free games for everyone. Racing, board and card games, word games, puzzles and more.

## Structure
- `index.html` - home screen (categories, music, diary, game launcher)
- `games/` - one HTML file per game
  - `car-race.html` - Car Race (3 tracks, 5 cars)
  - `whot.html` - Whot card game
- `music1.mp3` - background song (plays on the home screen only, never inside games)

## Add a new game
1. Put the game in `games/your-game.html` (it can post `{type:'playora:exit'}` to the parent to go back,
   and `{type:'playora:result', game:'Name', text:'Won!'}` to add an entry to the Diary).
2. In `index.html`, find the game in the `CATS` list and add `f:'games/your-game.html'`.
3. Add the file to `CORE` in `sw.js` and bump the cache name (for example `playora-v2`).

## Domain
`CNAME` still contains the old domain. Replace its single line with your new .com
(for example `playora.com`) before publishing on GitHub Pages.
