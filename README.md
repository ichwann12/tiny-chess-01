# Tiny Chess

A small, fast chess engine in a single Python file. Built for the
make.fun tiny-chess-01 competition (main.py must stay under 4,096 bytes).

## Design

- 0x88 board, alpha-beta search with a transposition table
- Quiescence over captures and promotions (all evasions when in check)
- Null-move pruning and late-move reductions
- MVV-LVA + killer-move ordering, iterative deepening
- Node budget only (no wall clock), so play is fully deterministic
- Material + piece-square tables, bishop pair

## Files

- `main.py` — the entry point (packed; see below)
- `engine.py` — the readable source (not committed)
- `LICENSE` — MIT

`main.py` is produced from `engine.py` with the make.fun kit:

```
node cli/makefun.mjs compress engine.py --out main.py
```

## License

MIT. See `LICENSE`.
