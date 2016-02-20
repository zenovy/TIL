I was trying to find lines specific to the -C command in ssh-keygen today, so I piped the manual page to grep:

```
man ssh-keygen | grep -C
```

This didn't work, because grep thought that -C was an argument. So, I tried some other options:

```
man ssh-keygen | grep "-C" //nope
man ssh-keygen | grep '-C' //still nope
```

Turns out, the dash is quite sacred in Bash. The eventual fix I found was:

```
man ssh-keygen | grep -- -C
```

This works because '--' signifies to bash that no more command line arguments will be specified. Neat, huh?

Although I found out later that this works as well, although the lessons learned aren't as widely applicable as the above:

```
man ssh-keygen | grep \\-C

```
