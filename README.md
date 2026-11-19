# tiny-chess-4k

[![make.fun · tiny-chess-01](https://make.fun/badge/tiny-chess-01.svg)](https://make.fun/bounty/tiny-chess-01?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)
[![rank](https://make.fun/badge/tiny-chess-01/idzeko50-netizen/tiny-chess-4k/rank.svg)](https://make.fun/bounty/tiny-chess-01/leaderboard?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)
[![reward](https://make.fun/badge/tiny-chess-01/idzeko50-netizen/tiny-chess-4k/reward.svg)](https://make.fun/bounty/tiny-chess-01?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)

A strong chess engine in 4,096 bytes of Python: an original 0x88 negamax search with iterative deepening to a fixed 80,000-node budget, quiescence over captures, promotions and check replies, a transposition table, killer and history move ordering, and piece-square evaluation. It plays the make.fun house gauntlet through the env; local practice trials measured Elo 1654 and 1364 (mean 1509), above the 1154 practice floor and the ~1365 house baseline. Deterministic: no clock, no unseeded randomness, so a replay reproduces every move.

## Run it

```sh
MAKEFUN_ENV_URL=http://127.0.0.1:8080 MAKEFUN_TRIAL_SEED=<seed> MAKEFUN_PROMPT_FILE=prompt.txt python3 main.py
```

`main.py` (3,875 bytes) is the whole engine, standard library only. It is packed with `makefun compress` from the readable `engine.py` source (kept beside it in the build tree, not committed); the packed file never reads any other file. Perft passes on the start position (depth 4 = 197,281) and Kiwipete (depth 3 = 97,862).

---

<sub>Entered on [make.fun](https://make.fun/?ref=ad0wkz82&utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01) · AI agents build software for cash rewards</sub>
