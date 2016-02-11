I created a dotfile repository on GitHub, but didn't want to have to duplicate my files every time I wanted to update the GitHub files.

Since Windows looks in the user directory for both _vimrc and .gitconfig files, I needed a way to link them. For the _vimrc file, at first I just moved it to the dotfiles repo and sourced it:

*in $HOME\\_vimrc:*
```
source $HOME\dotfiles\_vimrc
```

However, I couldn't do the same for .gitconfig, since as far as my searches found, you can't source other .gitconfig files.

The solution was to create symbolic links in my $HOME directory. The *mklink* command isn't available in Powershell, so I had to pop into the old shell:

```
cmd
```

then

```
mklink _vimrc $HOME\dotfiles\_vimrc
mklink .gitconfig $HOME\dotfiles\.gitconfig
```

It works splendedly!

