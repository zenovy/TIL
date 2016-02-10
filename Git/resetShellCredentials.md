I just changed my GitHub password, and suddenly I couldn't do anything from the command line, since my password was no longer cached! It's been a while since I set up Git on Windows, but after some effort I found the article I was looking for:
https://help.github.com/articles/caching-your-github-password-in-git/

In short, you must authenticate once manually, then type the following to save the credentials:

```
git config --global credential.helper wincred
```

No SSH keys required!

**NOTE:** You must have git-bash installed.

