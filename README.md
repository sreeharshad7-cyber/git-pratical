# Git Practical: Merge Conflict Resolution

## Aim
Identify and resolve a merge conflict created when two branches modify the same line in a file.

## Branches
- `main`: contains the original `message.txt`.
- `feature-one`: changes the message to `Message from Feature One`.
- `feature-two`: changes the same line to `Message from Feature Two`.

## Steps
1. Create two branches from the same base commit.
2. Change the same line in `message.txt` differently on each branch.
3. Merge one branch into the other to trigger a conflict.
4. Inspect `git status` and the conflict markers.
5. Edit the file to preserve both messages, stage it, and commit the resolution.

See `EXERCISE.md` for commands and the expected resolved result.