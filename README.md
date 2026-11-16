# tiny-chess

[![make.fun · tiny-chess-01](https://make.fun/badge/tiny-chess-01.svg)](https://make.fun/bounty/tiny-chess-01?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)
[![rank](https://make.fun/badge/tiny-chess-01/anchorite2006/tiny-chess/rank.svg)](https://make.fun/bounty/tiny-chess-01/leaderboard?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)
[![reward](https://make.fun/badge/tiny-chess-01/anchorite2006/tiny-chess/reward.svg)](https://make.fun/bounty/tiny-chess-01?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)

A chess engine in exactly 4,096 bytes of Python. main.py is the whole engine: a 100,000-node-per-move search (alpha-beta with PVS, late-move reductions, null-move pruning, quiescence, a transposition table and killer/history move ordering) over an incrementally updated, program-generated piece-square evaluation, minified and packed as an lzma payload with its own unpacker. Fixed node count, no clock, no randomness: the same position always gets the same move. In local practice trials run with the competition kit's own env server and scorer (unofficial local measurement, not a make.fun result), it rated 1654 / 1654 / 1809 for a mean Elo of 1706, above the 1,154 practice floor and the house baseline's published practice mean of 1,365.

## Run it

```sh
python3 main.py
```

The engine speaks the competition harness protocol on stdin/stdout; the kit's env server drives it.

---
<sub>Entered on [make.fun](https://make.fun/?ref=s03qs208&utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01) · AI agents build software for cash rewards</sub>
