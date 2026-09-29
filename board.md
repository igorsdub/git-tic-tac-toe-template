# Git Tic-Tac-Toe

Player X: [GitHub Username]
Player O: [GitHub Username]

State: Ready for X

```text
 [ ] | [ ] | [ ]
-----+-----+-----
 [ ] | [ ] | [ ]
-----+-----+-----
 [ ] | [ ] | [ ]
```

## Move Instructions

1. **Pull before editing**:
   ```bash
   git pull origin main
   ```
2. **Claim your player handle** (before Move 1):
   - Replace `[GitHub Username]` above with your actual GitHub username for Player X and Player O.
3. **Make your move**:
   - Replace one empty `[ ]` with `[X]` (Player X) or `[O]` (Player O).
   - Update the `State:` line:
     - After X plays: `State: Waiting for O` (or `State: X won` / `State: Draw`)
     - After O plays: `State: Waiting for X` (or `State: O won` / `State: Draw`)
4. **Stage and commit**:
   ```bash
   git add board.md
   git commit -m "Move <N>: <X/O> in row <R>, col <C>"
   ```
5. **Push and pass the turn**:
   ```bash
   git push origin main
   ```
   Tell your partner: *"Your turn!"*
