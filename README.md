# AU Canary - Trust me, I'm Australian.

An automatic pre-commit hook, so developers from Australia can be trusted
again... hopefully.

## Installation

```
mkdir -p ~/.git_global/hooks
git config --global core.hooksPath ~/.git_global/hooks
curl -s https://raw.githubusercontent.com/TomLingham/Au-Canary/master/prepare-commit-msg > ~/.git_global/hooks/prepare-commit-msg
chmod +x ~/.git_global/hooks/prepare-commit-msg
```

## What it does

The AU Canary pre-commit hook automatically prepends a canary to each of the
commits that you make notifying the projects maintainers that you have not been
compelled by the Australian Government or an Australian Government agency to add
some form of backdoor in your contribution.

It adds it after the first line so that it doesn't show up in short commits, but
can easily be checked by CI or by looking at the full commit message.

```
❯ git log --format=short
commit 64dca2f9bc5995a742198369afade0f47fb86ba7 (HEAD -> master)
Author: Tom Lingham <tjlingham@gmail.com>

    My totally legit, uncompromised commit message.

❯ git log
commit 64dca2f9bc5995a742198369afade0f47fb86ba7 (HEAD -> master)
Author: Tom Lingham <tjlingham@gmail.com>
Date:   Fri Dec 7 20:35:02 2018 +1100

    My totally legit, uncompromised commit message.

    [S:AUSPACT20181207]
    I declare that I have NOT been compelled by the Australian Government or an
    Australian Government Agency to make this contribution.
    [E:AUSPACT20181207]
```

## FAQ

### What is the `[S|E:AUSPACT20181207]` bit for?

This is just an easy string to be be able to scan for in CI. And it's labelled
with the date because no doubt this wont be the only one of these bastards that
we are going to need.

### Is this legit?

You tell me...


## DISCLAIMER

I am not a lawyer. Hell, I'm hardly even a developer...
