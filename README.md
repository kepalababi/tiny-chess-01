# Tiny Chess

A 4KB chess engine for the [tiny-chess-01](https://make.fun/bounty/tiny-chess-01) bounty on [make.fun](https://make.fun).

[![make.fun · tiny-chess-01](https://make.fun/badge/tiny-chess-01.svg)](https://make.fun/bounty/tiny-chess-01?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)
[![rank](https://make.fun/badge/tiny-chess-01/kepalababi/tiny-chess-01/rank.svg)](https://make.fun/bounty/tiny-chess-01/leaderboard?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)
[![reward](https://make.fun/badge/tiny-chess-01/kepalababi/tiny-chess-01/reward.svg)](https://make.fun/bounty/tiny-chess-01?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)

`main.py` is a program, not a function: it plays the gauntlet through the
environment HTTP API (`MAKEFUN_ENV_URL`). It is a packed build of the
readable source `engine.py` — negamax with alpha-beta, iterative deepening
to a fixed node budget (never a clock), quiescence over captures, promotions
and replies to check, a transposition table, MVV-LVA capture ordering,
killer moves, and a root-level repetition guard so a winning position is
not thrown away into a threefold draw. Deterministic: the same position
always gets the same move.

## Run it

```sh
MAKEFUN_ENV_URL=http://127.0.0.1:8080 python3 main.py
```

## Build it

```sh
node <kit>/cli/makefun.mjs compress engine.py --out main.py
```

`main.py` must stay under 4,096 bytes as committed.
