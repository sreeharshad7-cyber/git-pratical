# Exercise: Identify and Resolve a Merge Conflict

## Aim
Create a merge conflict by changing the same line on two branches, identify it, resolve it, and commit the resolution.

## Commands

```bash
git clone https://github.com/sreeharshad7-cyber/git-pratical.git
cd git-pratical

git switch -c feature-one
printf "Welcome to Git Practical\nMessage from Feature One\n" > message.txt
git add message.txt
git commit -m "Change message in feature one"
git push -u origin feature-one

git switch main
git switch -c feature-two
printf "Welcome to Git Practical\nMessage from Feature Two\n" > message.txt
git add message.txt
git commit -m "Change message in feature two"
git push -u origin feature-two

# Switch to feature-one and merge feature-two
git switch feature-one
git merge feature-two
```

## Identify the conflict

```bash
git status
```

The conflicting file is `message.txt`. Git inserts conflict markers similar to:

```text
<<<<<<< HEAD
Message from Feature One
=======
Message from Feature Two
>>>>>>> feature-two
```

## Resolve

Edit `message.txt` so it contains both messages:

```text
Welcome to Git Practical
Message from Feature One
Message from Feature Two
```

Then finish the merge:

```bash
git add message.txt
git commit -m "Resolve merge conflict"
git push origin feature-one
```

## Expected result
The merge completes successfully and `message.txt` contains both feature messages. The conflict is resolved by manually choosing the final combined content.

## Note
This repository contains two branches with conflicting edits to the same line. The merge itself must be performed in Git (locally or through a compatible merge UI) so Git can present and resolve the conflict.