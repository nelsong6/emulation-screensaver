# emulation-screensaver

A screensaver that plays back recorded start-to-finish game runs in an emulator.

## Idea

- Runs are recorded by playing normally with the emulator's movie recording on.
  Loading a save state while recording rewinds the movie to that point, so retries
  drop out and the result is one clean run from power-on to the credits.
- A save state is kept at each checkpoint. Playback loads the state at every
  segment boundary, so drift can't accumulate, and the screensaver can start at
  any checkpoint instead of the title screen every time.
- Each recording pins its ROM (by hash) and emulator version; a movie only plays
  back on the build that recorded it.
- Runs are grouped by style (a calm full playthrough, a fast one) so the
  screensaver can choose by type.

## Prior art

- [TASVideos](https://tasvideos.org): tool-assisted input movies for consoles.
- [Doom Speed Demo Archive](https://dsdarchive.com): human-played Doom demos
  grouped by run style (UV-Speed, UV-Max, Pacifist, ...).
