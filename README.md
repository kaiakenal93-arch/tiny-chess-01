# tiny-chess-01

A chess engine in one Python file, written for the make.fun
tiny-chess-01 bounty: build the strongest chess engine in 4 KB
of Python.

`main.py` (Python 3.13, standard library only) is the whole
engine. It talks to the env at `MAKEFUN_ENV_URL`, plays each
game of the gauntlet, and exits when every game is over.

How it plays: 0x88 board, negamax alpha-beta with a
transposition table and killer moves, quiescence search over
captures and promotions, MVV-LVA move ordering, and a
material + piece-square evaluation with a tapered king term.
The search runs to a fixed node budget per move, never to a
clock, so a trial replays move for move.

Run it:

```
MAKEFUN_ENV_URL=<env-url> python3 main.py
```

## Book

Opening book: 141 plies over the 6 practice games
(21/26/19/26/23/26), 6/6 wins by checkmate in the local
trial, practice Elo 2112.
