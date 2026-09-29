# Git Tic-Tac-Toe Template

Welcome to the **Git Tic-Tac-Toe Workshop**! This repository is the starter template for paired learners playing tic-tac-toe through Git and GitHub.

---

## Getting Started

### 1. Create Your Game Repository (Player X)
1. Click the green **Use this template** button at the top right of this repository page and select **Create a new repository**.
2. Name your repository (e.g. `git-tic-tac-toe`).
3. Set visibility to **Public** so workshop facilitators and the Game Wall can observe your game.
4. Click **Create repository**.

### 2. Invite Your Partner (Player X)
1. In your new repository on GitHub, navigate to **Settings** > **Collaborators** > **Add people**.
2. Enter your partner's GitHub username and send the invitation.

### 3. Accept Invitation & Clone (Player O & Player X)
- **Player O**: Accept the invitation from email or GitHub notifications.
- Both players clone the repository to your local computer:
  ```bash
  git clone https://github.com/<Player-X-Username>/<repo-name>.git
  cd <repo-name>
  ```

### 4. Set Up Handles in `board.md`
Before Move 1, open `board.md` and enter your GitHub usernames in the headers:
```markdown
Player X: @player1-username
Player O: @player2-username
```
Player X can commit and push this setup or include it together with Move 1.

---

## The Sacred Turn Cycle

Every turn follows five simple steps: **Pull -> Edit -> Stage -> Commit -> Push**.

```
┌───────────┐      ┌─────────────┐      ┌─────────────┐      ┌────────────┐      ┌────────────┐
│ 1. PULL   │ ───> │ 2. EDIT     │ ───> │ 3. STAGE    │ ───> │ 4. COMMIT  │ ───> │ 5. PUSH    │
│ git pull  │      │  board.md   │      │ git add ... │      │ git commit │      │  git push  │
└───────────┘      └─────────────┘      └─────────────┘      └────────────┘      └────────────┘
```

1. **Pull the latest move**:
   ```bash
   git pull origin main
   ```
   *Always pull before editing your local board!*

2. **Make your move in `board.md`**:
   - Replace an empty square `[ ]` with your mark (`[X]` or `[O]`).
   - Update the `State:` line to signal whose turn it is next (`State: Waiting for O`, `State: Waiting for X`, `State: X won`, `State: O won`, or `State: Draw`).

3. **Stage your change**:
   ```bash
   git add board.md
   ```

4. **Commit with a descriptive message**:
   ```bash
   git commit -m "Move 1: X in center square"
   ```

5. **Push your move**:
   ```bash
   git push origin main
   ```
   Notify your partner: *"Your turn!"*

---

## Handling Push Conflicts

If Git rejects your push with `[rejected] main -> main (fetch first)`:
1. Don't panic! Your partner pushed a move before you fetched it.
2. Run:
   ```bash
   git pull origin main
   ```
3. Inspect `board.md` to see the current board.
4. If there are no merge conflicts, push your move:
   ```bash
   git push origin main
   ```

---

## Extension: Branch Rematch (Finished Early?)

If you finish your game before workshop time is up, start a rematch on a dedicated branch to preserve your original game history on `main`:

1. **Player X** creates and pushes a new branch:
   ```bash
   git checkout -b rematch
   git push -u origin rematch
   ```

2. **Player O** checks out the rematch branch:
   ```bash
   git fetch origin
   git checkout rematch
   ```

3. Reset `board.md` to an empty grid:
   - Reset grid squares back to `[ ]`.
   - Update `State: Ready for X` (swap roles if Player O wants to go first!).
   - Commit: `git commit -am "Reset board for rematch game"`
   - Push: `git push origin rematch`
4. Play your rematch game on the `rematch` branch!
