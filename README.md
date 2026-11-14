# Tiny Chess Engine

A small but strong chess engine in a single Python file (stdlib only).
The file is an lzma+base85 packed stub: it decompresses to the exact
engine source and execs it, staying under the 4096-byte limit.

- 0x88 board, negamax + alpha-beta + iterative deepening
- Quiescence search, transposition table, killer moves, MVV-LVA ordering
- Null-move pruning, check extensions, repetition detection
- Material + piece-square tables + passed-pawn and bishop-pair bonuses
- Fixed node budget (60,000 nodes/move, ~2.6 s/move); no wall clock

It talks to the make.fun environment over HTTP (`$MAKEFUN_ENV_URL`).

## Run

```sh
MAKEFUN_ENV_URL=http://127.0.0.1:8080 python3 main.py
```

## License

MIT — see LICENSE.
