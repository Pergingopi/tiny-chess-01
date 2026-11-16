# tiny-chess-01

A compact chess engine in a single 4 KB Python file (`main.py`).

- 0x88 board, alpha-beta search with quiescence and a transposition table
  (move ordering only), piece-square-table evaluation, iterative deepening
  to a fixed per-opponent node budget (deterministic, no clock).
- Plays the make.fun tiny-chess protocol: reads `$MAKEFUN_ENV_URL`,
  loops `POST /game` / `POST /move` until the game is done.
- `main.py` is a packed build (lzma + base85) of the readable engine;
  the unpacker is the last line. Standard library only.

## Run

```sh
MAKEFUN_ENV_URL=http://127.0.0.1:PORT python3 main.py
```

## License

MIT — see `LICENSE`.
