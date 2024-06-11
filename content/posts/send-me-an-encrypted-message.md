+++
title = 'Send Me an Encrypted Message'
date = 2024-06-11T01:26:37+02:00
draft = false
+++

TLDR:
```
paru -S rage-encryption
rage -ar "ssh-ed25519 AAAAC3NzaC1lZDI1NTE5AAAAIESMjtNwNNyvuKbfn1ev4xnAg4ZZnbd6ApoF1KexJgAY"
# type in, then deliver the message to me however you wish
```

# Obligatory GPG rant
I find GPG to be a deeply annoying cryptosystem. It's technical flaws are laid out well [here](https://www.latacora.com/blog/2019/07/16/the-pgp-problem/), but the main problem with it is that it does not spark joy. GPG keys are unwieldy, expire from time to time and come with an unpleasant piece of software that...
- Features 643 (!) command line options (according to zsh-completions) for about six pieces of core functionality: Encrypt, decrypt, sign and verify information; Generate and manage keys to facilitate that
- Pollutes my `$HOME` directory with [dotfiles](https://hiphish.github.io/blog/2020/08/30/dotfiles-were-a-mistake/), rather than using [appropriate directories for app data](https://specifications.freedesktop.org/basedir-spec/basedir-spec-latest.html).
- Offers about 5 outdated or potentially backdoored algorithms when creating a key using its multi-step process
- Asks me to tie my legal name and an e-mail address to everything I use it for

There are probably many other complaints about the software that I would discover if I interacted with it more than I am forced to by KDE's secret storage, the [Arch Build System](https://wiki.archlinux.org/title/Arch_build_system) and other pieces of software whose authors consider GPG to be "the standard".

# `rage` Against The Machine instead
[`age`](https://age-encryption.org) and its reimplementation [`rage`](https://github.com/str4d/rage) are simple encryption tools that can use short and convenient key formats like SSH keys or their own format, which are short enough for a 140 character tweet while not lacking much functionality compared to the alternative. 

There is a [specification](https://github.com/C2SP/C2SP/blob/main/age.md) that appears to have been designed by knowledgable cryptographers but is still simple enough for a disinterested programmer to reimplement (given implementations of the underlying cryptography). 

With this in mind, you could now: Build some software on top of `age`, replace the GPG key on your site with an SSH key, or run the command above to encrypt a message just for me.

# Or maybe not
While it's fun to think about and discuss these generic encryption tools, I think for most private communication something like [Signal](https://signal.org/) is preferable.
