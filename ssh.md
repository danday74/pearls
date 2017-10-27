# multiple ssh keys

~/.ssh/config

```
Host github.com
  HostName github.com
  User git
  IdentityFile ~/.ssh/id_rsa_danday74

Host github.com-mydansboo
  HostName github.com
  User git
  IdentityFile ~/.ssh/id_rsa_mydansboo
```

When cloning:

```git clone git@github.com:danday74/pearls.git```

```git clone git@github.com-mydansboo:mydansboo/sian.git```

Link to [helpful article](https://gist.github.com/jexchan/2351996)

# useful commands

Use ```eval $(ssh-agent -s)``` to start agent

Use ```ssh-add -D``` to remove all keys

Use ```ssh-add -l``` to view added keys
