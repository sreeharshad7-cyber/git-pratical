# Exercise: Identify and Resolve a Merge Conflict

## Aim
Identify and resolve a merge conflict caused by two branches changing the same line in `message.txt`.

## 1. Get the existing branches

```bash
git clone https://github.com/sreeharshad7-cyber/git-pratical.git
cd git-pratical
git fetch origin
git switch --track origin/feature-one
git switch --track origin/feature-two
git switch feature-one
```

## 2. Trigger and identify the conflict

```bash
git merge feature-two
git status
```

Git reports a conflict in `message.txt`. The conflict markers look like this:

```text
<<<<<<< HEAD
Message from Feature One
=======
Message from Feature Two
>>>>>>> feature-two
```

`HEAD` is the current `feature-one` branch; the other section comes from `feature-two`.

## 3. Resolve the conflict

Edit `message.txt` and remove the conflict markers. Keep both messages:

```text
Welcome to Git Practical
Message from Feature One
Message from Feature Two
```

Then stage, commit, and push the resolution:

```bash
git add message.txt
git commit -m "Resolve merge conflict"
git push origin feature-one
```

## Expected result
The merge finishes successfully and the file contains both feature messages. The conflict is resolved by choosing the final combined content rather than blindly discarding either branch's change.

## Pull request
The open pull request from `feature-two` into `feature-one` intentionally contains these competing edits. Resolve the conflict locally as described above, push `feature-one`, and then review the pull request.